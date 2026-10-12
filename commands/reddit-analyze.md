---
description: Post-mortem on a Reddit thread (phase 5 of reddit-strategist). Pass the thread URL, or paste the thread. Separates the median reader from hostile regulars, surfaces the one or two comments worth following up on, and says whether to reply.
argument-hint: "<reddit-thread-url>"
---

# Analyze a Reddit thread

The user wants a post-mortem on a Reddit thread, usually one of theirs that flopped or got a mixed reaction. Use the `reddit-strategist` skill and go straight to phase 5. Follow its `references/analysis.md` (at `${CLAUDE_PLUGIN_ROOT}/skills/reddit-strategist/references/analysis.md`) for getting the thread and for the takeaways framework.

**Thread URL (if provided):** `$ARGUMENTS`

If there's a URL, try to get the thread right away the way `analysis.md` describes. Reddit blocks most unauthenticated fetching as of mid-2026, so if that fails, ask the user to paste the thread text, share a saved copy of the page, or send a screenshot, and work from whatever they have.

If there's no URL, ask for one, or for the pasted thread.

Then work through the framework in `analysis.md`: separate the median reader from the hostile regulars and the genuinely useful commenters, find the comments worth a follow-up (with names and permalinks where you have them), name what actually went wrong (sub, angle, voice, timing or substance), and recommend reply or disengage for each comment that needs a decision.

Be direct about what didn't work. That's what the user came for.
