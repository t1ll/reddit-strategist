# Trigger eval

Two test sets:
- `evals.json` — output evals (subjective, never run formally)
- `trigger_eval.json` — 20 trigger queries (10 should-trigger, 10 should-not)

To re-test the description (requires Python + `pip install anthropic`):

```bash
# Park the live skill so it doesn't conflict with the test
mv ~/.claude/skills/reddit-strategist /tmp/reddit-park
mv ~/.claude/commands/reddit-strategist.md /tmp/reddit-park.md

python3 ~/.claude/skills/reddit-strategist/evals/run_eval_patched.py \
  --eval-set ~/.claude/skills/reddit-strategist/evals/trigger_eval.json \
  --skill-path /tmp/reddit-park \
  --model claude-opus-4-7 --runs-per-query 3 --num-workers 4 \
  --description "<new description to test>"

# Restore
mv /tmp/reddit-park ~/.claude/skills/reddit-strategist
mv /tmp/reddit-park.md ~/.claude/commands/reddit-strategist.md
```

The `run_eval_patched.py` is a fix of skill-creator's `run_eval.py` — writes real
skills (`.claude/skills/<name>/SKILL.md`) instead of slash commands so trigger
detection actually works. Without this fix, the official script reports 0%
trigger rate for everything because slash commands don't auto-trigger from
natural-language queries.

## Latest scores

| Date       | Description version              | Positives        | False positives |
|------------|----------------------------------|------------------|-----------------|
| 2026-04-30 | v0 (baseline, 3-line)            | 1/30 (3%)        | 0/30            |
| 2026-04-30 | v1 (pushy "MUST" phrasing)       | 4/30 (13%)       | 0/30            |
| 2026-05-08 | v2 (Use-when + 30-phrase list)   | 4/20 (20%, n=2)  | 0/20            |

Raw v2 results: [`results-2026-05-08.json`](./results-2026-05-08.json).

The 20% ceiling appears to be the "specialized-knowledge under-trigger" pattern: even when
queries explicitly mention `r/SideProject`, `r/buildinpublic`, "Reddit thread," or "post
tanked," Claude often answers from general knowledge instead of consulting the skill.
skill-creator's own docs note that simple-looking queries skip skill consultation regardless
of description-match. Pushing higher likely needs:

1. **The full optimization loop** (`run_loop.py` from skill-creator) — uses the Anthropic
   API to propose descriptions iteratively. Requires `ANTHROPIC_API_KEY`.
2. **Even more imperative phrasing** ("Claude does NOT have reliable Reddit-sub knowledge —
   always consult").
3. **The slash command** (`/reddit-strategist`) as the deterministic fallback.
