---
description: Rewrite a draft in a named essayist's voice for cross-platform repurposing (blog, Substack, HN, LinkedIn long-form, X article). Argument is the author — paul-graham, patio11, housel, tim-urban, ben-thompson — or "ask" to be prompted with an opinionated recommendation. Not for native Reddit posts.
argument-hint: "<author-name | ask>"
---

# Write like X

**Requested author (if any):** `$ARGUMENTS`

The user wants to channel a specific essayist's voice. This is **force-invoke for cross-platform repurposing only** — blog, Substack, HN, LinkedIn long-form, X article. Not for native Reddit posts. PG voice on r/SideProject gets called AI slop within ten minutes; the skill refuses and points back at `references/voice.md` if the destination is Reddit.

Use the `reddit-strategist` skill. Load `skills/reddit-strategist/references/voices.md` for the full author profiles, the apply-order, and the de-slop pass checklist.

## If the user named an author

Recognized arguments (case-insensitive, hyphens or spaces):
- `paul-graham`, `pg` → Paul Graham profile
- `patio11`, `patrick-mckenzie` → Patrick McKenzie profile
- `housel`, `morgan-housel` → Morgan Housel profile
- `tim-urban`, `wait-but-why`, `wbw` → Tim Urban profile
- `ben-thompson`, `stratechery` → Ben Thompson profile

Jump straight to that profile. Don't ask which one.

## If the user said "ask", didn't name an author, or named someone not in the list

Stop and ask, but ask with an opinionated recommendation. Read the substance and destination, pick the one you'd commit to, and explain in one line each why the other four would mishandle this specific draft. Be specific to what's in their text. The full asking template is at the top of `voices.md`.

If they named someone not in the list (e.g. "Naval"), say the profile isn't built yet and offer the closest match from the five.

## Apply order (do not skip)

1. Structural surgery
2. Sentence rhythm
3. Vocabulary swap
4. Tells pass
5. Check the destination against the profile's "when NOT to use this voice" list
6. **De-slop pass** — the voice rules operate at sentence level; AI prose patterns reassert themselves at essay level. The full structural-AI-tells checklist is in voices.md under "The de-slop pass."

## Length floors

If the user's draft is below the floor for the chosen voice, recommend a different voice or format. Don't compress.

- Paul Graham: ≥600 words
- Patrick McKenzie: ≥1200 words
- Morgan Housel: ≥400 words
- Tim Urban: ≥800 words
- Ben Thompson: ≥1500 words

Hand the user the rewritten draft with a one-line note on what changed structurally, not a bullet-list changelog.
