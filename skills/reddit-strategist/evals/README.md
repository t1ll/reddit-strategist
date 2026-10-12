# Trigger eval

Two test sets:
- `evals.json` — output evals (subjective, never run formally)
- `trigger_eval.json` — 20 trigger queries (10 should-trigger, 10 should-not)

To re-test the description (requires Python + `pip install anthropic`):

```bash
# Park the live skill so it doesn't conflict with the test
# (if you installed it as a plugin, disable the plugin instead)
mv ~/.claude/skills/reddit-strategist /tmp/reddit-park

python3 ~/.claude/skills/reddit-strategist/evals/run_eval_patched.py \
  --eval-set ~/.claude/skills/reddit-strategist/evals/trigger_eval.json \
  --skill-path /tmp/reddit-park \
  --model claude-opus-5-5 --runs-per-query 3 --num-workers 4 \
  --description "<new description to test>"

# Restore
mv /tmp/reddit-park ~/.claude/skills/reddit-strategist
```

The `run_eval_patched.py` is a fix of skill-creator's `run_eval.py` — writes real
skills (`.claude/skills/<name>/SKILL.md`) instead of slash commands so trigger
detection actually works. Without this fix, the official script reports 0%
trigger rate for everything because slash commands don't auto-trigger from
natural-language queries.

## Old scores (May 2026)

All measured with claude-opus-4-7 against older descriptions. The description was rewritten in v0.6.0 and hasn't been re-tested, so these don't describe the current version.

| Date       | Description version              | Positives        | False positives |
|------------|----------------------------------|------------------|-----------------|
| 2026-04-30 | v0 (baseline, 3-line)            | 1/30 (3%)        | 0/30            |
| 2026-04-30 | v1 (pushy "MUST" phrasing)       | 4/30 (13%)       | 0/30            |
| 2026-05-08 | v2 (Use-when + 30-phrase list)   | 4/20 (20%, n=2)  | 0/20            |

Raw v2 results: [`results-2026-05-08.json`](./results-2026-05-08.json).

Back then the 20% looked like Claude answering Reddit questions from general knowledge instead of consulting the skill, even when a query named a sub. The fallbacks at the time were skill-creator's `run_loop.py` optimization loop (needs `ANTHROPIC_API_KEY`) and invoking the skill directly (`/reddit-strategist:reddit-strategist`, or `/reddit-strategist` for a manual install). The v0.6.0 rewrite dropped the "Claude doesn't reliably know Reddit, always consult" style of phrasing and the keyword dump, since current models follow plain descriptions well and tend to over-trigger on pushy ones.
