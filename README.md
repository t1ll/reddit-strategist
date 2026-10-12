```
\ | /
──*──     reddit · strategist
/ | \     a Claude Code skill for posting on Reddit
```

This is for founders and devs who post on Reddit. It helps you pick the sub, write the post so it doesn't get called AI slop, check the rules before you hit submit, and read the thread afterward without overreacting to the loudest commenter.

Posting there makes me nervous. You can have a real story with real numbers, and if an LLM helped with the draft, one too-tidy conclusion is enough for the top comment to be "this is so much writing dude. And obviously it's AI so even you didn't write it." Most of what people react to is the shape of the writing (the neat arc, the bolded headers, the moral at the end), and you can drop that and keep the story. The other half is picking the right sub and knowing who not to reply to.

It won't disguise generated text, and it won't make things up for you. If the draft needs a number you didn't give it, you get a placeholder like `[exact $ burned?]` and a question. Start from your own rough draft. If you ask it to write the whole post from one line, the result reads like that's what happened.

## Quickstart

Install the plugin from inside Claude Code:

```
/plugin marketplace add t1ll/reddit-strategist
/plugin install reddit-strategist@t1ll
```

Then:

1. Talk about Reddit like you normally would. "Where should I post my MRR update?", "does this sound AI-written?", or paste a thread link and say it tanked. The skill picks it up.
2. Paste a draft after `/reddit-strategist:reddit-slop` if you only want the AI-writing check.
3. Run `/reddit-strategist:reddit-analyze <thread-url>` after a post goes badly.

## See it work

```
You:    where should I post my $4.2K MRR update? solo, 8 months in,
        mostly for other indie hackers

Skill:  I'd start with r/SideProject. It's big and fine with
        milestone posts, but lead with what you built and what
        went wrong, not the MRR figure. r/microsaas is a decent
        second sub a few days later if you reframe it around the
        business side. Check both sidebars first, the self-promo
        rules move around.

        What title are you thinking?

You:    "$4.2K MRR after 8 months solo — what I'd do differently"

Skill:  The dash is fine. "What I'd do differently" is the problem:
        people expect a bolded list of lessons and scroll past.
        If most of the 8 months went into one wrong bet, put that
        in the title. Which months were wasted, and on what?

You:    /reddit-strategist:reddit-slop
        [pastes draft]

Skill:  Worst first:
        - "It's not about the MRR, it's about what it taught me."
          Contrastive reframe. This is the line people will quote.
        - The closing "3 takeaways" block with bold headers.

        Minor: "Furthermore," at the start of paragraph 2. Weak on
        its own, but it adds to the pile.

        The part about the pricing change is good, I'd leave it
        alone. Want me to redo the first two?
```

## What it covers

You don't need to go through these in order. Ask for whichever one you're stuck on.

| Phase | You'd ask | What you get |
|---|---|---|
| Target | "Where should I post this?" | A recommended sub (or two), what each one rewards and punishes |
| Angle | "How do I frame this for r/X?" | The same story reshaped for that sub's taste |
| Draft | "Help me write it" / "does this read as AI?" | Reddit voice rules, the AI tells in your draft quoted back to you |
| Publish | "I'm about to post, anything I'm missing?" | Rule and flair checks, timing, AutoMod gates |
| Analyze | "My post tanked" / "should I reply?" | Median reader vs. hostile regular, the one or two comments worth following up |

It's blunt on purpose. If the draft reads as AI or the sub is wrong, it says so and quotes the lines.

## Commands

Installed as a plugin, the commands are namespaced. Most of the time you won't need them.

| Command | What it does |
|---|---|
| `/reddit-strategist:reddit-analyze <url>` | Post-mortem on a thread. Reddit has blocked most anonymous fetching since mid-2026, so it'll often ask you to paste the thread or save the page |
| `/reddit-strategist:reddit-slop [draft]` | Quotes the lines that read as AI, worst first. No rewrite unless you ask |
| `/reddit-strategist:write-like <author>` | Rewrites a draft in one of five essayists' voices for a blog, Substack, LinkedIn or X. `ask` gets you a recommendation |

## Other platforms

If you want to turn a Reddit post into an X article, a LinkedIn post or a blog post, just say so ("rework this Reddit post for LinkedIn"). It checks current platform formats with a web search first, since those change every few months. If the post flopped, it does the post-mortem before rewriting, because a bad angle doesn't get better on another platform.

Hacker News is different. HN's guidelines ban AI-generated and AI-edited text, so for HN it gives you feedback and structure and you write the words yourself.

It can also write a prompt for a cover image. The notes on that are in `references/cross-platform.md`.

## Write like X

For essays outside Reddit, there are voice profiles for Paul Graham, Patrick McKenzie (patio11), Morgan Housel, Tim Urban and Ben Thompson. Each has rules, habits and before/after rewrites, plus a final pass that catches the AI-shaped structure that sentence-level rules miss.

```
"rewrite this as a Paul Graham essay"
"give it the Housel treatment"
"make this read like Stratechery"
```

These are essay voices, and they tend to backfire as native Reddit posts. It'll tell you that and still do it if you insist. It also won't invent anecdotes or quotes to make a voice fit, so Housel in particular needs a real story from you.

## Installation

The plugin route above is the easiest. It gives you the skill and the three commands, and updates with `/plugin update reddit-strategist@t1ll`.

If you only want the skill, without the commands, clone the repo wherever you keep code and symlink the skill folder into `~/.claude/skills`. Edits then show up without reinstalling, which is also how I work on it:

```bash
git clone https://github.com/t1ll/reddit-strategist.git ~/Sites/reddit-strategist
ln -s ~/Sites/reddit-strategist/skills/reddit-strategist ~/.claude/skills/reddit-strategist
```

## Repository layout

```
.
├── .claude-plugin/
│   ├── plugin.json
│   └── marketplace.json        # the repo is also the t1ll marketplace
├── commands/
│   ├── reddit-analyze.md
│   ├── reddit-slop.md
│   └── write-like.md
└── skills/reddit-strategist/
    ├── SKILL.md                # routing table and principles
    ├── references/
    │   ├── subreddits.md       # dev/founder subs, what each one wants
    │   ├── templates.md        # angles, titles, sample posts
    │   ├── voice.md            # Reddit voice and AI tells
    │   ├── engagement.md       # pre-flight and in-thread replies
    │   ├── analysis.md         # thread fetching and post-mortems
    │   ├── cross-platform.md   # X, LinkedIn, HN, blogs, cover images
    │   └── voices.md           # the five author profiles
    └── evals/
```

`SKILL.md` loads when the skill triggers. The reference files are only read for the phase you're in.

## Troubleshooting

If the skill doesn't trigger, mention Reddit, a sub like r/SideProject, or paste a reddit.com link. You can also call it directly with `/reddit-strategist:reddit-strategist` (or `/reddit-strategist` if you installed it by hand).

If it triggers when you didn't want it, that's probably cross-platform talk. It's meant to stay out of X/LinkedIn/HN work unless you're repurposing a Reddit post or asking for one of the author voices.

If thread analysis can't fetch a link, that's Reddit blocking it, not the skill. Open the thread in your browser, add `.json` to the URL and save it, or paste the text.

If you symlinked it and your edits don't show up: the `SKILL.md` frontmatter is read when a session starts, so open a new one. The body and the reference files are read when needed.

## Testing the description

The description decides whether Claude picks the skill up on its own. In October 2026 I ran the 20 queries in `trigger_eval.json` against the installed v0.6.0 plugin with claude-opus-5-5, one run each. All 10 Reddit queries triggered the skill and none of the 10 others did (LinkedIn, X, Hacker News, cold email, a CSP bug with an embedded Reddit iframe, and so on).

`run_eval_patched.py` is still in `evals/`, but don't trust it right now. On the same day it reported 2 of 30 positive runs. It tests a renamed stub copy of the skill instead of the installed one, and I haven't worked out why the current Claude Code doesn't pick that copy up. `evals/README.md` has the details and the older numbers.

## Contributing

PRs are welcome. I'd most like:

- subs I'm missing in `references/subreddits.md`, with why they belong in that tier
- posts where you followed the voice rules and still got called AI
- platform notes in `cross-platform.md` that are out of date

Keep the tone direct. The skill is only useful if it tells people what won't work.

## License

MIT. See [LICENSE](LICENSE).
