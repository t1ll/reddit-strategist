# Reddit voice

The single biggest reason founder posts get called "AI slop" is that they're written in *blog voice* or *LinkedIn voice* — both of which are exactly the smooth, structured, neutral-positive register that ChatGPT defaults to. Reddit's culture has spent the last two years training itself to spot that register and reject it on sight.

Reddit voice is not a style. It is a refusal of style. It is the absence of the moves a marketer or content writer would make. This file lists the moves to NOT make, and the moves that signal "real human posting from their phone after work."

## The compact rule set

If you only remember a handful of rules:

1. **Cut the narrative arc.** No setup → tension → resolution. Reddit posts open with the punchline.
2. **Cut summary statements.** Replace every "we learned X" with the raw specific that taught you X.
3. **Use "I" if you are one person, "we" only if you actually have a team. Founders saying "we" when they mean themselves reads as PR fluff.**
4. **Specifics, always.** Numbers with decimals. Real provider names. Real prompts. Screenshots beat paragraphs.
5. **Vary length. Some sentences should be three words. Others run on, the way a thought actually goes when you're typing it out at the kitchen table and you keep adding clauses.**
6. **No em dashes.** Use commas, periods, parentheses, or just two short sentences.
7. **No rule-of-three.** "Faster, cheaper, better" is the AI fingerprint.
8. **No bold inline-list headers.** "**Speed:** We made it faster" is the most AI-shaped pattern on the internet.
9. **Put the TL;DR at the top, not the bottom.** Reddit reads top-down and bails fast.
10. **Have an actual opinion** — not "this raises questions about X" but "honestly I think X was dumb of me."

## Patterns to delete on sight

These are taken from the humanizer skill but the priorities here are Reddit-specific. The first six are the ones Reddit readers most reliably auto-flag as AI.

### 1. Smooth narrative structure
The story shape "we set out to build X. Then we encountered Y. Then we learned Z. We're now doing W." is the single most AI-shaped move on Reddit. It doesn't matter that you actually wrote it. Reddit has internalized that shape as ChatGPT-shaped.

**Fix:** Open with the most surprising specific from the middle. Don't set up. Don't transition. End abruptly.

**AI-shaped:**
> We launched our AI image platform in late 2024. We knew acquisition would be a challenge, so we offered $1 in free credit to every new user. What we didn't expect was that 71% of all video generations would get flagged as pornographic. Here's the story of what we learned.

**Reddit:**
> 71% of video generations on my platform got flagged as porn within the first week. I gave every new signup $1 free credit and apparently that's exactly enough budget to attract a very specific category of user.

### 2. Rule of three
Three is the AI rhythm. Two or four is human.

**AI-shaped:** "It was faster, cheaper, and easier to scale."
**Reddit:** "It was faster. Also cheaper. Also we accidentally broke our payment provider."

### 3. Bold inline-list headers
This is so distinctive that some readers literally just downvote and move on the moment they see it.

**AI-shaped:**
> - **Speed:** Generation time dropped 40%.
> - **Cost:** Cost per request fell to $0.003.
> - **Reliability:** Failover triggered 0.2% of the time.

**Reddit:**
> Generation time is down ~40% (don't have the exact number in front of me, somewhere around there). Cost is $0.003/req on average. Failover hit on something like 0.2% of requests, which I was happy with until I realized the fallback path was the one letting porn through.

### 4. Em dashes
Reddit em-dash use is real but rare. Two em dashes in one post will get you an "is this AI" comment.

**Fix:** Replace with comma, period, or parens. If you'd write "X — and this is the interesting part — Y," just split into two sentences.

### 5. Promotional vocabulary
Words that flag as marketing copy on Reddit (you'd be amazed how universally these get sniffed out): "vibrant," "robust," "seamless," "powerful," "elegant," "intuitive," "cutting-edge," "leveraging," "harness," "unlock," "empower," "delight," "world-class," "best-in-class," "game-changer," "groundbreaking," "transformative."

If a sentence still works after you delete the adjective, the adjective was promotional.

### 6. Smooth transitions
"Furthermore," "Additionally," "Moreover," "What's more," "On top of that," "It's worth noting that," "It's also important to consider..." All AI markers. Reddit prose just goes to the next sentence.

**AI-shaped:** "Furthermore, the failover logic was retrying on a different provider. Additionally, that provider had laxer NSFW filters."
**Reddit:** "The failover was retrying on a different provider. Which had laxer NSFW filters. Yeah."

### 7. Generic opinions / weasel attribution
"Some would argue," "Industry observers note," "Many founders find," "It's commonly understood that..." — none of these belong on Reddit. Either you have an opinion or you cite a specific person.

**AI-shaped:** "Many founders argue that free trials attract the wrong audience."
**Reddit:** "I keep seeing this quote from someone on this sub that free trials attract the worst users. They're right."

### 8. Sycophantic / customer-service tone
"Thanks for the great question!" "I appreciate the thoughtful comment!" "That's an excellent point and I want to address it..." — when replying to comments, drop all of this.

**Fix:** Just answer the comment. "Yeah you're right" is a complete reply.

### 9. Closing summaries / "key takeaways"
"To sum up, the three key takeaways are..." Reddit posts don't have conclusions. The post ends when you stop typing.

**Fix:** Just stop. The last sentence should be a specific, not a summary.

### 10. Hedging about the post itself
"Hopefully this is helpful." "Apologies for the long post." "Maybe this is the wrong sub." Strip all of it. Reddit reads it as either weasel or AI sycophancy.

(One exception: if you literally are in the wrong sub, leading with "probably the wrong sub but" can sometimes disarm. Use sparingly.)

### 11. Hedging phrases (the AI tic)
Specific hedging constructions are now near-perfect AI fingerprints because LLMs default to them constantly. Cut all of these:

- "it's worth noting that..."
- "it's important to remember that..."
- "while this may vary..."
- "to some extent"
- "in many cases"
- "generally speaking"
- "broadly speaking"
- "as a general rule"
- "could potentially..."
- "may or may not..."
- "tends to..."

Pick a side. If you're not sure, say "I'm not sure but I think..." — Reddit prefers explicit uncertainty over generic hedging.

### 12. Nominalization (verbs disguised as nouns)
LLMs over-produce abstract noun phrases where humans use plain verbs. "The implementation of the filter" → "I added the filter." "The optimization of the pipeline" → "I made the pipeline faster." "There was a discussion about pricing" → "We argued about pricing." This is one of the most reliable AI tells; humans almost never write this way casually.

Watch for `-tion`, `-ment`, `-ance`, `-ity` suffixes piling up in a sentence. If you see two in a row, rewrite the sentence around verbs.

### 13. Hallucinated specifics
A specific is only useful if it's real. AI prose often manufactures plausible-sounding details (fake percentages, plausible-sounding fake quotes, fake source names) because the *shape* of a specific helps the prose. On Reddit this gets called out instantly — someone always asks for the source, and "made it up" is worse than "didn't include one." Either cite a real thing or don't make a numbered claim.

If you want to gesture at a number you remember vaguely, say so: "somewhere around 80%, don't have the exact figure in front of me." That construction is a strong human signal in itself.

## Patterns to USE (the ones that signal human)

### Specifics that no AI would generate
- Real timestamps. "Around 2:30am Tuesday" beats "late at night."
- Real provider names. "Replicate's safety filter" beats "our model provider's content filter."
- Real prompts you saw. "One user's prompt was literally just 'big titty anime girl beach' typed into the description field" reads as human in a way that "we saw concerning prompts" never will.
- Real dollar amounts with decimals. "$847.30 burned in the first 4 days" beats "we burned through hundreds of dollars."
- Self-mockery about a specific bad decision. "Yeah we should've turned off failover for flagged content from day one. We did not."

### Lowercase opens (occasionally)
On Reddit, opening with a lowercase fragment ("ok so this is wild") is a recognizable native marker. Use sparingly — every-post is itself a tic.

### Mid-post asides in parens
"(don't ask)" "(yes I know)" "(this is dumb)" — Reddit loves parenthetical asides. AI prose almost never produces them. They're cheap human signal.

### "Edit:" additions
After posting, adding "Edit: clarifying X because a few people asked" reads as native. Build this into the writing flow — even leaving an "edit: yeah I'm an idiot, fixing the typo" is reassuringly human.

### Acknowledged uncertainty
"I think this is right but honestly not sure" is more believable than a confident claim. AI prose is rarely uncertain in this way.

### Profanity (sub-dependent)
On most dev/founder subs (r/programming, r/SideProject, r/indiehackers, r/SaaS, r/microsaas), one well-placed "fuck" or "shit" reads as native. Don't overdo it. On r/startups it's a coin flip — that sub is more buttoned-up.

### Specifically named villains
"I'm pretty sure one Telegram group has an entire workflow built around platforms like ours" reads as human. AI rarely produces this kind of specific antagonist.

### Cultural and temporal anchoring
References to recent events, current dates, or niche cultural knowledge are things LLMs are bad at — their training data is stale, and they avoid time-bound claims. A post that mentions "this happened last Tuesday" or "right after the OpenAI outage" or "during the May Sora hype" reads as freshly-human in a way that's hard to fake. Don't force it, but if your story has temporal markers, keep them in.

## The cluster sniff test

The biggest insight from AI-detection research: no single tell proves a post is AI-written. Plenty of human posts have one or two AI-shaped patterns. What flags a post as slop is *clusters* of patterns. A post with rule-of-three sentences AND bolded inline-list headers AND smooth transitions AND hedging phrases AND no specifics will trip every reader's detector even if a human wrote it.

Self-check before posting: read your draft and tally how many of these are present:

- [ ] Smooth narrative arc (setup → tension → resolution)
- [ ] Rule-of-three constructions
- [ ] Bolded inline-list headers
- [ ] Em dashes
- [ ] Smooth transitions ("furthermore," "additionally," "moreover")
- [ ] Hedging phrases ("it's worth noting," "to some extent")
- [ ] Promotional adjectives ("seamless," "robust," "powerful")
- [ ] Nominalization piles ("the implementation of the optimization")
- [ ] No real-numbered specifics
- [ ] No personal opinion or stance
- [ ] No emotional tone (neutral-positive only)
- [ ] Closing summary or "key takeaways"

If you check 4 or more, the draft will read as AI even if you typed every word yourself. Rewrite. The fix is rarely fix-the-sentence; it's *throw out the structure*.

## Length budget

## The one-screen test

Before posting, do this. Open the draft. Imagine you're scrolling Reddit at 11pm half-paying-attention. Read your post in that mode.

- If you can stop reading after the first 200 words and have already gotten the point, you're good.
- If the post requires reading the second paragraph to understand the first, you've buried the lede.
- If any paragraph reads "balanced" (one sentence stating a thing, one sentence elaborating, one sentence wrapping it up), rewrite it.
- If the structure is parallel (paragraph 1 is X, paragraph 2 is Y, paragraph 3 is Z, all the same shape), rewrite at least one to be a different shape.

## Length budget

This is sub-dependent and there's a per-sub guide in `subreddits.md`, but as a default:

- **Story-friendly subs** (r/SideProject, r/indiehackers, r/microsaas): 200-500 words self-text. Anything past 600 starts losing readers and gaining "TL;DR??" comments.
- **Tactical subs** (r/programming, r/devops, r/MachineLearning): can go longer (800-1500) but only if every paragraph delivers a specific. Pad detection is brutal here.
- **Update subs** (r/buildinpublic, r/scaleinpublic): 100-300 words plus screenshots/numbers. Story-shaped posts get downvoted here.
- **r/startups**: 250-400 words, tactical. The sub has gotten increasingly hostile to story posts in 2024-2026. They want lessons-with-numbers, not narratives.
- **HN**: link post + ~150 word optional context. Don't write the post into the HN box.

## When the draft fails the voice check

If a draft has multiple AI tells:

1. Don't try to fix sentence-by-sentence. The shape is wrong.
2. Throw the draft out and start over with this prompt to yourself: *"What's the single most surprising specific I'd tell a friend at the bar about this?"* Open with that. Then write the next thing you'd say. Then the next. Stop when you'd stop in the conversation.
3. Read it aloud. If any sentence sounds like it could be on a corporate "About" page, kill it.
4. Show it to one other person. Ask them: "Does this sound like ChatGPT wrote it?" Believe their answer.
