```
\ | /
──*──     reddit · strategist
/ | \     a Claude Code skill for posting fearlessly
```

A skill for posting to Reddit without it tanking. Or getting called AI slop. Or burning a one-shot story.

## Why this exists

Posting on Reddit is scary.

You have something genuinely worth saying. Real story, real numbers. Doesn't matter. The smallest sign of "AI" in your prose, and you take a hard beating. Took help from an LLM to draft an honest update? One too-clean conclusion, one em-dash where you'd never have used one, and the top comment becomes some variant of *"this is so much writing dude. And obviously it's AI so even you didn't write it."*

I built this because that fear is paralyzing, and most of what causes it is fixable.

Reddit's allergy isn't really to AI. It's to the *shape* of AI prose. Drop the shape without sacrificing the substance and you can post the same story and get a fair read.

Voice is only one piece, though. Picking the wrong sub burns a one-shot story. So does posting and going to bed. So does replying to the wrong commenter. This is the playbook I wish I'd had the first time.

## What it does

Five phases, used à la carte:

1. **Target.** Pick the right subreddit. Each one is its own culture.
2. **Angle.** Reframe the same underlying story for the sub you picked.
3. **Draft.** Rewrite in Reddit voice. The opposite of blog voice, the opposite of AI voice.
4. **Publish.** Pre-flight the post so it doesn't get quietly removed by a rules bot or buried by bad timing.
5. **Analyze.** Read the thread honestly. Separate signal from one loud hater, find the one or two comments worth following up on.

It's opinionated and direct, not consultant-y. If your draft reads as AI slop, the skill will tell you and show you the lines.

## When to invoke it

You don't have to invoke it explicitly. The description is tuned so Claude pulls it in automatically when you mention Reddit, a subreddit, or symptoms like "my post tanked" or "people called it AI slop." You can also force-load it via the `/reddit-strategist` slash command.

Typical entry points:

| You say… | Skill jumps to… |
|---|---|
| "Where should I post my $4.2K MRR update?" | Phase 1 (Target) |
| "Help me write the post for r/SideProject" | Phases 2-3 (Angle + Draft) |
| "Does this draft sound AI-written?" | Phase 3 (Voice review) |
| "I'm about to hit submit, anything I'm missing?" | Phase 4 (Pre-flight) |
| "My post tanked, read this thread and tell me why" | Phase 5 (Analyze) |
| "Should I reply to this hostile commenter?" | Phase 5 (Engage) |

## Cross-platform repurposing (force-invoke)

The skill auto-triggers only on Reddit work, but the voice rules carry. AI-detection allergies on X/Twitter and the dev side of LinkedIn look a lot like Reddit's, just less aggressive.

When you've got a Reddit post you want to recycle elsewhere, force-invoke the skill explicitly:

```
"this Reddit post tanked, rework it as an X article"
"convert this to a HN-friendly version"
"salvage this for LinkedIn, what changes?"
"turn my r/buildinpublic update into a Substack post"
```

The skill applies the voice principles, then makes platform-specific calls. Per-platform notes for X, LinkedIn, Hacker News, and Substack/blog live in `references/cross-platform.md`.

Before locking in any format choice, the skill verifies current platform state via WebSearch. Platform tactics change on the order of weeks, and confident-sounding stale recommendations from older training data are the worst possible outcome here.

If you're repurposing a *flopped* post, the skill runs the post-mortem first. Rewriting without diagnosing why it tanked just relocates the problem.

### Cover images

Articles, blog posts, Substack, and LinkedIn carousel slide 1 all need cover images. The skill generates a copy-pasteable image prompt tuned for editorial covers (no faux-3D AI render aesthetic, no floating geometric shapes, single dominant color plus accent, title text overlay).

Recommended image models:

- **GPT Image 2** (OpenAI): best at text rendering, handles overlaid titles in 5+ languages with high first-pass accuracy.
- **Nano Banana Pro** (Google Gemini 3 Pro Image): up to 4K resolution, strong consistency for series-of-posts use cases.

If you don't already have access to either, the skill suggests **lumenfall.ai** (unified API for AI media gen, OpenAI-compatible) or **fal.ai** (serverless image gen with broad model coverage) as execution paths.

## Installation

### Option A: install as a Claude Code plugin (recommended)

```bash
/plugin marketplace add t1ll/reddit-strategist
/plugin install reddit-strategist@t1ll
```

The repo doubles as a marketplace named `t1ll`, so once it's added you'll see `from t1ll` next to the plugin in `/plugin list`.

### Option B: drop it into `~/.claude/skills/` manually

```bash
git clone https://github.com/t1ll/reddit-strategist.git ~/.claude/skills/reddit-strategist
```

Restart Claude Code. The skill auto-triggers on Reddit-related queries, or you can invoke it explicitly with the `Skill` tool or `/reddit-strategist`.

### Option C: symlink for local development

If you want to edit the skill and have changes pick up immediately:

```bash
git clone https://github.com/t1ll/reddit-strategist.git ~/Sites/reddit-strategist
ln -s ~/Sites/reddit-strategist/skills/reddit-strategist ~/.claude/skills/reddit-strategist
```

## Repository layout

```
.
├── README.md
├── LICENSE
├── .claude-plugin/
│   ├── plugin.json              # plugin manifest
│   └── marketplace.json         # repo as a single-plugin marketplace
└── skills/
    └── reddit-strategist/
        ├── SKILL.md             # 5 phases + principles
        ├── references/
        │   ├── subreddits.md    # tier list of dev/founder subs
        │   ├── templates.md     # angle and title formulas
        │   ├── voice.md         # anti-AI-slop voice rules (most important)
        │   ├── engagement.md    # publish-time + in-thread playbook
        │   ├── analysis.md      # post-mortem workflow
        │   └── cross-platform.md # X/LinkedIn/HN/Substack notes + cover image prompts
        └── evals/
            ├── trigger_eval.json
            ├── results-2026-05-08.json
            ├── run_eval_patched.py
            └── README.md
```

The skill uses progressive disclosure. `SKILL.md` is loaded when triggered. References are pulled in on demand for the phase you're working on.

## Testing the description

The skill description determines whether Claude auto-invokes it. Current trigger rate (2026-05-08): 20% on positives, 0% false positives. To re-test:

```bash
cd skills/reddit-strategist/evals
python3 run_eval_patched.py \
  --eval-set trigger_eval.json \
  --skill-path .. \
  --model claude-opus-4-7 \
  --runs-per-query 3 \
  --num-workers 4
```

See `skills/reddit-strategist/evals/README.md` for the full history, the parking workflow needed if you have the skill installed live, and the path forward to higher trigger rates.

## Contributing

PRs welcome, especially for:

- New subs in `references/subreddits.md` with tier and reasoning.
- Counter-examples where the voice rules failed.
- Better post-mortem patterns.
- Cross-platform repurposing notes that turned out wrong (or right).

Keep the tone direct. This skill earns trust by being honest about what won't work, not by being polite.

## License

MIT. See [LICENSE](LICENSE).
