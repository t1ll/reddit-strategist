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

What Reddit's actually reacting to is the *shape* of AI prose. Drop the shape without sacrificing the substance and you can post the same story and get a fair read.

Voice is only one piece, though. Picking the wrong sub burns a one-shot story. So does posting and going to bed. So does replying to the wrong commenter. This is the playbook I wish I'd had the first time.

## On AI assistance

This isn't for disguising AI content or impersonating writers. Most people who use AI to draft aren't strong writers. The output reads as AI because AI prose has a shape readers spot in seconds. The rules in here came from reading real published essays and a stack of "this got called slop" examples. They describe how actual prose moves.

Start with your own draft. Even a rough one. The skill sharpens what's there. Ask it to write the whole essay from one line and you get slop back, because there's nothing to sharpen.

## Quickstart

Install (30 seconds, see below). Then in any Claude Code conversation:

1. Type a Reddit-related question. Examples: `"where should I post my $4.2K MRR update?"`, `"does this draft sound AI-written?"`, `"my post tanked, read this thread: <url>"`. The skill auto-triggers.
2. Or force it with `/reddit-strategist`.
3. Run `/reddit-analyze <thread-url>` for a post-mortem on a specific thread.
4. Run `/reddit-slop` on a draft to check the prose against the anti-AI patterns.
5. Run `/write-like` to channel a specific essayist for cross-platform repurposing.

Stop there. You'll know if it's useful.

## See it work

```
You:    where should I post my $4.2K MRR update? built solo, 8 months
        in, target audience is other indie hackers

Skill:  three real options, ranked. r/SideProject is the obvious one
        but it has a 9:1 self-promo rule and your account has no
        organic history, so you'll get filtered. r/buildinpublic is
        warmer but the moderation flag for $-figures in titles trips
        easily. r/microsaas is your best fit if you can lead with the
        operational specifics, not the MRR figure.

        what title did you have in mind?

You:    "$4.2K MRR after 8 months solo — what I'd do differently"

Skill:  reads as AI in two ways. the em-dash. and the hidden rule-of-
        three promise in "what I'd do differently": you'll write three
        things, you'll bold them, Reddit will spot the shape.

        try: "$4.2K MRR solo, and 6 of the 8 months were wasted"

You:    /reddit-slop
        [pastes full draft]

Skill:  3 patterns to fix:
        - paragraph 2 opens with "Furthermore," (AI marker)
        - "**Metric:** $X, **Retention:** Y%" inline-list block
        - closing sentence "what this really comes down to is..."
          (the classic moralizing wrap)

        the substance is solid. want me to rewrite the three?
```

## The five phases

Used à la carte. Pick what you need.

| Phase | When you reach for it | What it does |
|---|---|---|
| 1. Target | "Where should I post this?" | Sub tier list. Sub-specific rules. What each one rewards and punishes. |
| 2. Angle | "How do I frame this for r/X?" | Same story, different cultural fit. |
| 3. Draft | "Help me write it" / "does this read AI?" | Reddit voice rules. The opposite of blog voice. |
| 4. Publish | "I'm about to submit, anything I'm missing?" | Pre-flight checks. Timing. The "I will not promote" gates. |
| 5. Analyze | "My post tanked" / "should I reply?" | Post-mortem framework. Sort signal from one loud hater. Find the 1-2 golden comments. |

Opinionated and direct, not consultant-y. If your draft reads as AI slop, the skill says so and shows you the lines.

## Slash commands

Most of the time you don't need these. The skill auto-triggers on Reddit talk. Use the commands when you want to skip to a specific phase or pair a phase with an argument.

| Command | What it does |
|---|---|
| `/reddit-strategist` | Generic force-invoke. Use when auto-trigger doesn't fire. |
| `/reddit-analyze <url>` | Phase 5 directly. Fetches the thread JSON, runs the post-mortem framework, surfaces the 1-2 comments worth following up on. |
| `/reddit-slop` | Phase 3 only. Paste a draft after the command and the skill names the AI-shaped lines. |
| `/write-like <author>` | Cross-platform repurposing. Channels Paul Graham, patio11, Housel, Tim Urban, or Ben Thompson. `/write-like ask` for a recommendation with elimination reasoning for the other four. |

Auto-trigger phrases the skill catches: `"where should I post X"`, `"help me write the post for r/X"`, `"does this draft sound AI?"`, `"I'm about to hit submit"`, `"my post tanked"`, any `reddit.com` URL.

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

Platform tactics change on the order of weeks. Stale recommendations from training data are worse than no recommendation, so the skill verifies current platform state via WebSearch before locking in a format choice.

If you're repurposing a *flopped* post, the skill runs the post-mortem first. Rewriting without diagnosing why it tanked just relocates the problem.

### Cover images

Articles, blog posts, Substack, and LinkedIn carousel slide 1 all need cover images. The skill generates a copy-pasteable image prompt tuned for editorial covers (no faux-3D AI render aesthetic, no floating geometric shapes, single dominant color plus accent, title text overlay).

Recommended image models:

- **GPT Image 2** (OpenAI): best at text rendering. Overlaid titles in 5+ languages with high first-pass accuracy.
- **Nano Banana Pro** (Google Gemini 3 Pro Image): up to 4K resolution, strong consistency across a series.

If you don't already have access to either, the skill suggests **lumenfall.ai** (unified API for AI media gen, OpenAI-compatible) or **fal.ai** (serverless image gen with broad model coverage).

## Write like X (force-invoke)

When you're repurposing a Reddit post into longer-form work elsewhere, you sometimes want to channel a specific writer instead of just "not-AI." The skill ships with voice profiles for five essayists, each distilled from reading 10+ of their published articles:

- **Paul Graham**: declarative-first essays in plain English. Argues by analogy. For HN-shaped think-pieces.
- **Patrick McKenzie (patio11)**: wide-aperture explainers, parenthetical-rich, qualified. For long-form B2B and fintech.
- **Morgan Housel**: anecdote-first, one-sentence paragraphs, bolded reframe. For behavioral and decision-making pieces.
- **Tim Urban (Wait But Why)**: second-person, rhetorical-question-driven, named metaphors. For making giant topics intimate.
- **Ben Thompson (Stratechery)**: claim-evidence-implication essays with named frameworks. For industry strategy.

Each profile is ~500 words: voice summary, concrete rules, distinctive tics, three before/after rewrites, and a "when NOT to use" list. There's also a structural de-slop pass at the end because AI-shaped narrative architecture survives sentence-level voice rules and has to be caught separately.

Trigger phrases:

```
"rewrite this as a Paul Graham essay"
"channel patio11, turn this into a Bits about Money piece"
"give it the Housel treatment"
"make this read like a Wait But Why post"
"convert to Stratechery-style with a named framework"
```

Or use the slash command directly: `/write-like patio11`.

Two guardrails the skill enforces:

1. **Not for Reddit-native posts.** All five are essay voices. PG on r/SideProject gets called AI slop in ten minutes. The skill refuses and points you back at the Reddit voice rules.
2. **Length floors.** PG ≥600w, patio11 ≥1200w, Housel ≥400w, Urban ≥800w, Thompson ≥1500w. Below the floor, the tells don't land. The skill recommends a different voice or format rather than compressing.

If you don't name an author, the skill asks. The recommendation comes with one-line elimination reasoning for each of the other four, so you can override knowing exactly what you're trading off.

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
├── commands/
│   ├── reddit-analyze.md        # /reddit-analyze <url>
│   ├── reddit-slop.md           # /reddit-slop
│   └── write-like.md            # /write-like <author>
└── skills/
    └── reddit-strategist/
        ├── SKILL.md             # 5 phases + principles
        ├── references/
        │   ├── subreddits.md    # tier list of dev/founder subs
        │   ├── templates.md     # angle and title formulas
        │   ├── voice.md         # anti-AI-slop voice rules (most important)
        │   ├── engagement.md    # publish-time + in-thread playbook
        │   ├── analysis.md      # post-mortem workflow
        │   ├── cross-platform.md # X/LinkedIn/HN/Substack notes + cover image prompts
        │   └── voices.md        # "write like X" author profiles
        └── evals/
            ├── trigger_eval.json
            ├── results-2026-05-08.json
            ├── run_eval_patched.py
            └── README.md
```

The skill uses progressive disclosure. `SKILL.md` is loaded when triggered. References pull in on demand for the phase you're working on.

## Troubleshooting

**Skill not auto-triggering?** Force it with `/reddit-strategist`, or mention "Reddit," a subreddit, or a `reddit.com` URL.

**Want to update the installed plugin?** `/plugin update reddit-strategist@t1ll`

**Editing locally and changes not picking up?** If you symlinked the skill (Option C above), open a new Claude Code session. `SKILL.md` frontmatter is read at session start; body content and `references/*.md` are pulled on demand and don't need a restart.

**Skill triggering for the wrong thing?** The description deliberately doesn't catch LinkedIn, X/Twitter, Hacker News, or other non-Reddit channels. If you want it engaged for cross-platform work, force-invoke with `/reddit-strategist` or say "repurpose this Reddit post for X."

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

See `skills/reddit-strategist/evals/README.md` for the full history, the parking workflow you need if the skill is installed live, and the path to higher trigger rates.

## Contributing

PRs welcome, especially for:

- New subs in `references/subreddits.md` with tier and reasoning.
- Counter-examples where the voice rules failed.
- Better post-mortem patterns.
- Cross-platform repurposing notes that turned out wrong (or right).

Keep the tone direct. This skill earns trust by being honest about what won't work, not by being polite.

## License

MIT. See [LICENSE](LICENSE).
