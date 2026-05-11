---
description: Post-mortem on a Reddit thread. Pass the thread URL as the argument. Runs phase 5 of reddit-strategist directly — fetches the thread JSON, sorts signal from noise, surfaces the 1-2 golden comments worth following up on.
argument-hint: "<reddit-thread-url>"
---

# Analyze a Reddit thread

The user wants a post-mortem on a Reddit thread, probably one of theirs that flopped or got a weird mix of reactions. Use the `reddit-strategist` skill and jump straight to Phase 5. Read `skills/reddit-strategist/references/analysis.md` for the curl-based fetch workflow and the takeaways framework.

**Thread URL (if provided):** `$ARGUMENTS`

If a URL was provided above: fetch the thread JSON immediately. Don't ask first.

If `$ARGUMENTS` is empty: ask for the URL. Don't try to analyze a thread from memory or a screenshot.

Once the thread is loaded, run the framework honestly:

1. **Separate the three voices.** The median reader (top-voted comments + upvote ratio), the one hostile super-commenter (anyone with 4+ comments), and the 1-2 genuinely useful commenters who shared specific operational intel.
2. **Find the gold.** Even on a thread with a 0.43 upvote ratio, there are usually 1-2 comments worth a DM follow-up. Surface them with names + permalinks.
3. **Diagnose the failure.** Was it the sub, the angle, the voice, the timing, or the substance? Be specific. Don't summarize — diagnose.
4. **Decide engagement.** For each hostile comment, recommend reply or disengage. The default for a known sub-regular dunker is disengage; the exception is a single substantive technical point worth a one-line neutral acknowledgment.

Be direct. Reddit will be honest with the user an hour after they post. Better the skill is honest first.
