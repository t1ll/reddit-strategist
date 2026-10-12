# Reddit voice

Founder posts get called "AI slop" mostly because they're written in blog or LinkedIn register: smooth, structured, evenly paced, neutral-positive. That's the register chat models default to, and Reddit readers have learned to spot it, often within the first two lines. The specific tells shift as models change (this file reflects what readers flag as of late 2026); the underlying allergy doesn't.

The goal isn't to dodge detection. Readers flag AI text because it's generic: real details smoothed into safe, tidy prose. So the fix lives in the substance (real specifics from the user, an actual opinion, stopping when the point is made) much more than in the surface. Typos, slang and invented hesitations don't help. Fake roughness is its own tell now, and people who use LLMs every day spot it fast.

## Contents

- Ground rule: specifics come from the user
- What Reddit voice sounds like
- Tells, ranked by how strongly readers react (tier 1, tier 2, tier 3)
- Over-correcting into fake casual
- What reads as human
- The cluster test
- The one-screen test
- Length budget
- When the draft fails

## Ground rule: specifics come from the user

Specifics are what make a post read as human, which is exactly why it's tempting to make them up. Every number, timestamp, provider name, prompt, quote and anecdote in a draft has to come from the user. If the draft needs one you don't have, ask, or leave a visible placeholder like `[exact $ burned?]` or `[which provider?]` and list the open placeholders under the draft.

Round numbers are fine if that's what the user knows. Fake precision ("$847.30" from nowhere) is worse than no number: someone always asks for the source, and "made it up" is far worse than "didn't include one."

The same applies to everything in "What reads as human" below. Edits, named antagonists, time markers and swearing work when they're true and the user's own, never as decoration.

## What Reddit voice sounds like

A good Reddit post reads like a person typing on their phone after work. They lead with the most interesting thing, say what they think, give details only they would know, and stop. Samples 1 and 2 in `templates.md` are full examples of the target.

1. **Open with the point.** The most surprising specific goes first, not a setup. Reddit reads top-down and bails fast. If a long post doesn't carry its point in the first two lines, a TL;DR at the top helps.
2. **Raw specifics over summary statements.** Replace "we learned X" with the detail that taught you X.
3. **"I" for one person, "we" for an actual team.** A solo founder writing "we" reads as PR. If you don't know which the user is, ask.
4. **Have an opinion.** Not "this raises questions about X" but "I think X was a dumb call on my part."
5. **Let rhythm follow the thought.** Some sentences are short and some run on because the thought did. Don't manufacture fragments to hit a quota; a run of three-word sentences is a tell too.
6. **Format like a post, not a doc.** Paragraphs. A plain list only when the content really is a list.
7. **End when you're done.** The last line is a specific or a real question, not a summary.

## Tells, ranked by how strongly readers react

The ranking is a judgment from watching threads, not a measurement. Every item is a signal: a human post with one or two of them is normal, and what gets a post flagged is a cluster (see the cluster test). Several examples below come from one founder's free-credit abuse story; it's an illustration, so don't carry its details into other users' posts.

### Tier 1: often enough on its own to draw "is this AI?"

**Contrastive reframes.** "It's not X, it's Y." "This isn't A — it's B." "Not X, not Y, just Z." "Y rather than X." "The question isn't whether…, it's…" The writer invents a belief nobody held so they can knock it down. It's currently the pattern people quote most often when they call something AI.

Fix: say Y. If someone really does believe X, name who.

- AI-shaped: "This isn't a logging problem. It's an observability problem."
- Reddit: "Our logs were fine. What burned the week was that nobody could tell which services a request had gone through."

Once in a long essay, aimed at a belief readers actually hold, it's fine (Paul Graham does it; see `voices.md`). Repeated, or in a native Reddit post, it's a tell.

**Hook and closer templates.** Openers like "Here's the thing", "Here's what nobody tells you about X", "I'll be honest:", "Let that sink in." The reveal: "The real lesson / the real reason is…" Closers like "Full stop." and "And that changes everything." Engagement-bait questions tacked on the end: "Curious how others handle this?", "What would you do?", "Thoughts?"

Fix: cut them. If the user wants discussion, ask a narrow question only they could ask: "Anyone else on Replicate seeing the same filter gaps on the fallback path?"

**Bold inline headers and doc formatting.** "**Speed:** We made it faster" is the most recognizable AI formatting habit, and some readers downvote on sight. Same family: markdown section headers in a self-post, Title Case Headers, emoji bullets, bolded key phrases mid-paragraph, curly quotes pasted from a chat window.

AI-shaped:
> - **Speed:** Generation time dropped 40%.
> - **Cost:** Cost per request fell to $0.003.
> - **Reliability:** Failover triggered 0.2% of the time.

Reddit:
> Generation time is down about 40%. Cost is $0.003/req on average. Failover kicked in on about 0.2% of requests, which I was happy with until I realized the fallback path was the one letting porn through.

**The tidy story arc.** "We set out to build X. Then we hit Y. Then we learned Z. Now we're doing W." Setup, tension, resolution, moral: it's the default chat-model story shape, and readers recognize it even when a human wrote it.

Fix: open with the most surprising specific from the middle, skip the setup and the transitions, stop when the story's told.

AI-shaped:
> We launched our AI image platform in late 2024. We knew acquisition would be a challenge, so we offered $1 in free credit to every new user. What we didn't expect was that 71% of all video generations would get flagged as pornographic. Here's the story of what we learned.

Reddit:
> 71% of video generations on my platform got flagged as porn within the first week. I gave every new signup $1 free credit and apparently that's exactly enough budget to attract a very specific category of user.

**Closing summaries and takeaway lists.** "To sum up, the three key takeaways are…" Reddit posts don't have conclusions, and a bolded three-lesson list at the bottom is the worst version. Fix: stop. If a lesson matters, it should already be visible in the body.

**Specifics that look invented.** Suspiciously tidy numbers, quotes that all sound alike, generic names ("a founder named Sarah"), sources nobody can find. Readers ask for receipts. See the ground rule.

### Tier 2: strong in combination

**Cosmetic triads.** Three adjectives or three parallel clauses used for cadence: "faster, cheaper, and easier to scale." The tell is the rhythm, not the number three. List as many things as there actually are. Rounding to two or four to dodge it just builds a different formula.

- AI-shaped: "It was faster, cheaper, and easier to scale."
- Reddit: "It got faster, which I expected. What I didn't expect was breaking our payment provider in the process."

**Staccato fragment drama.** Runs of very short sentences or parallel fragments for effect ("No funding. No team. Just vibes." / "Engineers build. Managers ship."), and paragraphs that end on a punchy fragment ("Simple enough for X, without the cost of Y."). One short sentence is fine; a pattern of them is a tell.

**Performative sincerity and model-era vocabulary.** "Honestly," "genuinely," "truly," "the honest answer is." Figurative "quietly" ("quietly breaks everything") and "load-bearing." Mannered metaphors dressing up a plain claim. Helper phrasing ("can help you," "is especially helpful") and superlatives ("the most powerful"). The older list (delve, tapestry, landscape, pivotal, underscore, showcase, crucial, align with) mostly marks 2023-25 models. Still worth cutting, but its absence proves nothing.

**Promotional vocabulary.** "Seamless," "robust," "powerful," "elegant," "intuitive," "cutting-edge," "leverage," "harness," "unlock," "empower," "delight," "world-class," "best-in-class," "game-changer," "groundbreaking," "transformative." If the sentence still works with the adjective deleted, it was promotional.

**Sycophantic replies.** "Thanks for the great question!" "That's an excellent point and I want to address it…" In comments, just answer. "Yeah, you're right" is a complete reply.

**Weasel attribution.** "Some would argue," "Many founders find," "It's commonly understood that…" State your own opinion or point to a specific person or thread.

- AI-shaped: "Many founders argue that free trials attract the wrong audience."
- Reddit: "Someone on this sub said free trials attract the worst users. For me at least, they were right."

**Reflexive hedging.** The tell is stacked or didactic hedging ("it's worth noting that," "it's important to remember," "could potentially," "while this may vary," "may or may not"), not ordinary qualifiers. People actually use "usually" and "tends to" more than models do, so one honest qualifier is fine. Replace a generic hedge with a stance, or with uncertainty that names its gap: "I haven't checked whether Fal has the same problem."

**Hedging about the post itself.** "Hopefully this is helpful." "Apologies for the long post." "Maybe this is the wrong sub." It reads as filler. (If the user really isn't sure about the sub, "probably the wrong sub, but" can disarm once.)

**Uniform rhythm.** Every paragraph two or three sentences, every sentence 15-20 words, each paragraph built claim, elaboration, wrap-up. Let length follow content: a one-line paragraph where the thought is one line, a long one where it needs room.

**The reused template.** Readers judge the account, not just the post. The same skeleton posted across subs with the nouns swapped, a soft product mention ("X helped me a lot"), and an author who never replies in the comments all read as a marketer or a bot. When the user posts to more than one sub, rewrite for each one.

### Tier 3: weak on their own

**Em dashes.** Readers still associate em dashes with ChatGPT, even though current models rarely produce them. One in an otherwise human post isn't a tell. Two or more formulaic ones (spaced, used for a dramatic pause or a reveal) still draw "is this AI" comments. When drafting, prefer a comma, colon, parentheses or a new sentence. When editing the user's own text, leave a deliberate dash alone unless it's part of a cluster. And don't swing the other way into nothing but commas and periods; uniformly plain punctuation is starting to read as machine-made too.

**Transitions.** "Furthermore," "Additionally," "Moreover," "What's more." Weak alone, but they make prose smoother than Reddit is. Usually the next sentence can just start.

- AI-shaped: "Furthermore, the failover logic was retrying on a different provider. Additionally, that provider had laxer NSFW filters."
- Reddit: "The failover was retrying on a different provider, and that provider had much looser NSFW filters."

**Nominalization.** "The implementation of the filter" for "I added the filter." "There was a discussion about pricing" for "We argued about pricing." Common in AI and corporate prose. When -tion, -ment and -ity nouns start piling up, rewrite around verbs.

**Polish by itself.** Clean grammar, formal words, a neutral tone. These cause most false accusations against human writers. Don't call a draft AI-shaped just because it's tidy.

## Over-correcting into fake casual

The newest tells come from drafts trying too hard not to sound like AI. Readers who use LLMs daily recognize the kit, and when you de-slop a draft it's easy to land right in it.

- **Performative lowercase.** A whole post in lowercase from someone who normally writes in sentence case, or "ok so" bolted onto every opener. Match the user's own habits.
- **Fake candor.** "ngl," "not gonna lie," "I'll be real with you," reflexive "honestly," confessions that exist to sound relatable.
- **"That's it, that's the post."** And its cousins: "Anyway. Yeah." / "Make of that what you will." Stock closers now.
- **Forced fragments.** "Which had laxer filters. Yeah." Sounds rough, reads as formula.
- **Sprinkled slang and swearing.** "lol," "lmao," one dutiful "fuck." Only if the user writes that way.
- **Canned asides.** "(don't ask)," "(yes I know)," "(this is dumb)" as filler rather than an actual reaction.
- **Manufactured vagueness.** "Don't have the exact number in front of me" when the user gave you the number.
- **Pre-written edits and fake typos.** An "Edit: fixing the typo" drafted before the post exists, or deliberate misspellings. Leave both out.

Natural is the goal, not rough. A plain, clean post with real specifics reads more human than a messy one with invented texture.

## What reads as human

All of this has to come from the user. If they didn't give it to you, ask.

- **Real specifics.** "Replicate's safety filter," not "our model provider's content filter." Actual prompts: one user's prompt being literally "big titty anime girl beach" lands in a way "we saw concerning prompts" never will. Real amounts and real times, as precise as the user knows them.
- **Self-mockery about a specific decision.** "Yeah, we should've turned off failover for flagged content from day one. We did not."
- **Real uncertainty, stated once.** "I think this is right, but I haven't checked whether Fal has the same gap" beats a confident claim.
- **Asides that carry something.** A parenthetical with real information or a real reaction is fine. A canned one isn't (see above).
- **Named antagonists, if they're real.** "Pretty sure one Telegram group has a whole workflow built around platforms like ours," if the user can stand behind it.
- **Time markers the user gave you.** "The day after the outage" beats "recently." Keep them; don't invent them.
- **Swearing, if the user swears.** On most dev and founder subs (r/SideProject, r/indiehackers, r/SaaS, r/microsaas) one well-placed "fuck" reads fine. r/startups is more buttoned-up. Don't add it as a signal.
- **Edits after posting.** "Edit: clarifying X since a few people asked" reads native. The user adds it later, about something that actually happened.

## The cluster test

No single tell proves anything; readers react to clusters. Check the draft for:

- [ ] Contrastive reframes ("not X, it's Y")
- [ ] Hook or closer templates, or an engagement-bait closing question
- [ ] Bold inline headers, markdown headers, title case or emoji formatting
- [ ] Tidy setup, tension, resolution, moral arc
- [ ] Closing summary or takeaway list
- [ ] Cosmetic triads
- [ ] Staccato fragment runs
- [ ] "Honestly," "genuinely," "quietly" and other model-era words
- [ ] Promotional adjectives
- [ ] Stacked or didactic hedges
- [ ] Uniform sentence and paragraph length
- [ ] Fake-casual moves (performative lowercase, fake candor, "that's the post")
- [ ] Formulaic em dashes (two or more)
- [ ] No real specifics, no opinion, neutral-positive tone throughout

Weak alone, so count them only as part of a cluster: a single em dash, transitions, formal words, clean grammar.

How to read the result: one or two hits need a light edit, and deliberate choices the user made can stay. Four or more and the draft will read as AI even if the user typed every word; the structure is usually the problem, so rebuild instead of patching (see the last section). Also flag a draft that trips nothing but reads uniformly smooth with no real specifics, since that's generic in a way the checklist misses.

When reporting, quote the offending lines, most damaging first. The user needs to know which lines to fix, not how many boxes got ticked.

## The one-screen test

Picture someone scrolling Reddit at 11pm, half paying attention, and read the post that way.

- If they've got the point within the first screen, good.
- If the first paragraph only makes sense after the second, the lede is buried.
- If a paragraph reads "balanced" (statement, elaboration, wrap-up), rewrite it.
- If every paragraph has the same shape, break at least one.

## Length budget

These are defaults. `subreddits.md` has per-sub notes, and the target sub's top posts from the past month are the best guide.

- **Story-friendly subs** (r/SideProject, r/indiehackers, r/microsaas): 200-500 words of self-text. Past about 600 you start getting "TL;DR??" comments.
- **Tactical subs** (r/programming, r/devops, r/MachineLearning): 800-1500 works if every paragraph carries a specific; readers there are quick to call out padding. r/programming treats AI/LLM topics as off-topic unless deeply technical and removes AI-generated content, so check its current AI policy before sending anything AI-adjacent there.
- **Update subs** (r/buildinpublic, r/scaleinpublic): 100-300 words plus screenshots or numbers. Story-shaped posts do badly here.
- **r/startups**: 250-400 words, tactical. Regulars there have been visibly impatient with story posts; lessons with numbers do better than narrative.
- **Hacker News**: usually a link post with the text field empty and the backstory as a top comment. HN's guidelines ban generated and AI-edited text, so anything posted there should be written by the user. Give feedback on their draft rather than writing it. Details in `cross-platform.md`.

## When the draft fails

If several tells cluster:

1. Rewriting sentence by sentence rarely works, because the shape is the problem.
2. Start over from one question: what's the most surprising specific the user would tell a friend about this? Open with that, write the next thing they'd say, and stop where the conversation would stop. Use only material the user gave you.
3. Read it aloud. Any sentence that could sit on a corporate About page goes.
4. Suggest the user show it to one other person and ask, "Does this sound like ChatGPT wrote it?" Their answer beats any checklist.
