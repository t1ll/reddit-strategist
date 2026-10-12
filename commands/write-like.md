---
description: Rewrite a draft in a named essayist's voice for a blog, Substack, LinkedIn article or X article. Argument is the author (paul-graham, patio11, housel, tim-urban, ben-thompson) or "ask" for a recommendation. Not meant for native Reddit posts.
argument-hint: "<author-name | ask>"
---

# Write like X

**Requested author (if any):** `$ARGUMENTS`

Use the `reddit-strategist` skill and follow its `references/voices.md` (at `${CLAUDE_PLUGIN_ROOT}/skills/reddit-strategist/references/voices.md`). It has the author profiles, length guidance, apply order and the final check for AI patterns.

Recognized arguments (case-insensitive, hyphens or spaces):
- `paul-graham`, `pg`: Paul Graham
- `patio11`, `patrick-mckenzie`: Patrick McKenzie
- `housel`, `morgan-housel`: Morgan Housel
- `tim-urban`, `wait-but-why`, `wbw`: Tim Urban
- `ben-thompson`, `stratechery`: Ben Thompson

If the argument names one of these, go straight to that profile.

If it's "ask" or empty, ask which author before drafting, with your recommendation and a line on why each alternative fits this draft worse, as `voices.md` describes.

If it names someone else, say there's no profile for them yet and offer the closest of the five.

If the destination is a Reddit post, say that essay voices tend to read as AI there and suggest the Reddit voice in `voice.md` instead. If they still want it, go ahead. For Hacker News, note that its guidelines ban AI-generated and AI-edited text, so offer feedback on the user's own draft rather than a rewrite.

Use only material the user gave you. If the voice calls for an anecdote, quote or number that isn't there, ask for it.

Hand back the draft with a one-line note on what changed structurally.
