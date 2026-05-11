---
description: AI-slop check on a Reddit draft. Paste the draft after the command (or have it in the active conversation). Phase 3 of reddit-strategist, voice review only — names the specific AI-shaped lines, no full rewrite unless you ask.
---

# AI-slop check on a Reddit draft

The user has a draft and wants to know whether it reads as AI before they post. Use the `reddit-strategist` skill, Phase 3 only. Read `skills/reddit-strategist/references/voice.md` for the full pattern catalog.

Run the draft against every pattern in voice.md, top to bottom. The high-priority offenders Reddit readers flag in seconds:

1. The "It's not X, it's Y" / negation-then-replacement chiasmus
2. Em-dashes (especially two or more)
3. Rule-of-three lists and parallel constructions
4. Bolded inline-list headers ("**Speed:** We made it faster")
5. Smooth transitions: Furthermore, Moreover, Additionally, What's more
6. Promotional vocabulary: leverage, unlock, robust, seamless, vibrant
7. The "what this is really about" / "the real lesson is" moralizing closer
8. Three-takeaway numbered list at the end
9. Neat setup → tension → resolution → moral narrative arc

Be specific. Name the exact lines that trigger each pattern. Don't soften the criticism. If the post reads as AI slop, say so and quote the offending sentences back.

After naming the patterns, ask whether the user wants you to rewrite the offending parts. Don't rewrite unprompted — they may have written some of those lines deliberately and want to decide which to fix.

If the draft is clean: say so, also specifically. "I ran it against the full pattern list and found nothing in here that'll flag." Don't hedge.
