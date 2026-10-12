---
description: "AI-writing check on a Reddit draft (phase 3 of reddit-strategist): quotes the lines that read as AI, most damaging first. No rewrite unless you ask. Paste the draft after the command or have it in the conversation."
argument-hint: "[draft text]"
---

# AI-writing check on a Reddit draft

The user has a draft and wants to know whether it reads as AI before posting. Use the `reddit-strategist` skill, phase 3 only, and review the draft against its `references/voice.md` (at `${CLAUDE_PLUGIN_ROOT}/skills/reddit-strategist/references/voice.md`).

**Draft (if provided):** $ARGUMENTS

If there's no draft above or earlier in the conversation, ask for it.

Report only the tells that actually appear. Quote each offending line, name the pattern, and order them by how much damage they do. These usually matter most:

1. Contrastive reframes: "It's not X, it's Y", "not X, not Y, just Z", "the question isn't whether… but…"
2. Hook and closer templates: "Here's the thing", "That's it. That's the post.", "the real lesson is", an engagement-bait question at the end
3. The neat setup, tension, resolution and moral arc, or a closing list of takeaways
4. Formatting from a chat window: bolded inline headers, markdown headings, title case, emoji bullets
5. Runs of short dramatic fragments
6. Performative sincerity and stock words: "honestly", "genuinely", "quietly", promotional or older AI vocabulary
7. Uniform rhythm, invented-looking specifics, three items used for cadence rather than content

`voice.md` has the full list and the reasoning. Weigh clusters over single hits. A single em dash, a transition word or clean grammar is weak evidence on its own, and flagging text just because it's polished is the most common false positive. Say how many strong tells you found and whether together they'd draw "is this AI" comments.

Don't soften the verdict. When you suggest fixes, don't recommend typos, forced lowercase, added slang or swearing, or made-up details; if a section needs a specific, ask the user for the real one.

Ask before rewriting. The user may have written some of those lines on purpose and wants to choose what to change.

If the draft is clean, say so plainly, and name the biggest remaining risk if there is one (for example, no concrete detail in the first two lines, or a shape that matches every other launch post in the sub).
