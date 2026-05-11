# "Write like X" — author voice profiles

Force-invoke only. This file is loaded when the user explicitly asks to write in the voice of a named author — phrases like "rewrite this like Paul Graham," "channel patio11," "make this read like a Wait But Why post," "give it the Housel treatment," "Stratechery-style." Do not load this file for auto-triggered Reddit-native work. The voices in here are *essay voices*, and most of them are exactly what Reddit punishes.

The skill exists because the user has already crossed a destination boundary: they're taking a Reddit post — or some other raw founder writing — and repurposing it into a blog essay, Substack piece, HN article, or LinkedIn long-form, where polish is rewarded. Pulling a named author's voice over the substance is a precision tool for that step.

## First: did the user actually name an author?

If the user said "like a real author," "like a good writer," "in a proper voice," "make it sound better," "channel someone good," or any other generic phrasing **without naming a specific person** — **STOP. Ask them.** Do not pick one yourself by analyzing the substance. Which author to channel is a creative choice the user cares about — they will not be happy if you pick patio11 for a piece they imagined in PG's voice.

Ask in chat with a one-line summary per author **plus an opinionated recommendation that eliminates the other four**. The elimination is the load-bearing part — it's what earns the user's trust in the recommendation and lets them override on informed grounds. Read the substance and destination carefully before composing it; this is not boilerplate.

Template:

> Five voices available:
> - **Paul Graham** — flat declarative essays, plain English, argues by analogy.
> - **Patrick McKenzie (patio11)** — wide-aperture, qualified, parenthetical-rich.
> - **Morgan Housel** — anecdote-first, one-sentence paragraphs, bolded reframe.
> - **Tim Urban (Wait But Why)** — second-person, rhetorical questions, named metaphors.
> - **Ben Thompson (Stratechery)** — headed sections, claim-evidence-implication, definitive close.
>
> My recommendation is **[X]** because [why this voice fits the specific substance + destination — name the actual hooks in their draft]. Why not the others:
> - [Author A] would [do thing A wrong for this substance — be specific to what's in the draft].
> - [Author B] would [thing B wrong].
> - [Author C] would [thing C wrong].
> - [Author D] would [thing D wrong].
>
> Want to go with **[X]**, or pick a different one?

A real example of the elimination passage (from a piece about free-tier fraud and multi-account operators):

> My recommendation is **patio11** because the substance is dead-center his beat — free-tier fraud mechanics, the policy-vs-capability distinction in payment routing, treating multi-account operators as organized rather than individual. The wide-aperture-then-zoom structure is what this draft is reaching for already. Why not the others:
> - **PG** would flatten the specifics into a general claim and lose the operational texture that makes the piece interesting.
> - **Housel** would turn this into one operator's story plus a behavioral reframe, which under-credits how *organized* the operators are.
> - **Tim Urban** would name a metaphor for the operators and digress through it; the substance is concrete enough that the metaphor would feel like padding.
> - **Thompson** would force a capitalized framework that doesn't quite earn its name on a piece this short — "Friction-Zero Markets" or similar would land as overreach.

If you have the `AskUserQuestion` tool available, use it with the five authors as single-select options — but put the recommendation + eliminations in the question text above the options, not in the option descriptions. The user needs to see all the reasoning before they pick.

Do not start drafting until they pick (or explicitly tell you to go with your recommendation).

The exceptions — proceed without asking — are: (a) they named the author themselves, (b) the request says "use the decision table" / "you pick" / "surprise me" / "whichever fits best," or (c) you've already asked once in this conversation and they answered.

## Watch for ambiguous destination references

"Write this for X" is ambiguous: X-the-platform (Twitter/X) vs X-the-placeholder. If the user wrote "for x" or "for X" without context, ask: "Did you mean for X.com (Twitter), or is X a placeholder for the author?" Don't guess. (Recent context: if they were just discussing cross-platform repurposing, it probably means the platform — but confirm.)

## Hard prereqs before opening any profile

1. **Confirm the destination.** If the user is still posting to Reddit native, refuse and explain — point them at `references/voice.md` instead. PG voice on r/SideProject gets called AI slop within ten minutes. This is a non-negotiable failure mode.
2. **Confirm the substance is intact.** "Write like X" is a coat of paint, not a thesis generator. If the underlying claim is weak, an author voice will make it more conspicuously weak, not better. Diagnose first.
3. **Pick one voice and commit.** Don't blend two ("Paul Graham meets Housel"). Each voice has a coherent internal logic; blending produces a third voice that reads as nothing in particular, which is the worst outcome.
4. **Read the profile end-to-end before drafting.** The "When NOT to use this voice" section is where most mistakes get caught. Check it against the destination the user named.

## Author-picker decision table

Use this table to seed the **default suggestion** when you ask the user (see the section above). Don't silently pick from it — present it as a recommendation alongside the other four options and let the user choose.

| What the piece needs to do                                  | Author                | Why                                                    |
|---|---|---|
| Make a flat contrarian claim and defend it in plain English | **Paul Graham**       | Declarative-first, no setup, argues by analogy        |
| Explain a complex industry/mechanism to smart laypeople     | **Patrick McKenzie**  | Wide aperture, qualified, parenthetical-rich          |
| Reframe a behavioral lesson through one human story         | **Morgan Housel**     | Anecdote-first, one-sentence paragraphs, bold reframe |
| Make a giant abstract topic feel intimate and explorable    | **Tim Urban**         | Second-person, rhetorical questions, named metaphors  |
| Argue an industry framework with disciplined scaffolding    | **Ben Thompson**      | Headed sections, claim-evidence-implication, definitive close |

## Length floors

All five voices need room. Below these floors, the imitation fails — not because the voice is wrong but because there isn't enough surface area for the tells to land.

- Paul Graham: ~600 words minimum (one essay-scale move and a closer)
- Patrick McKenzie: ~1200 words minimum (wide aperture eats the first 300)
- Morgan Housel: ~400 words minimum (needs one anecdote + reframe + restatement)
- Tim Urban: ~800 words minimum (digressions need a runway)
- Ben Thompson: ~1500 words minimum (framework needs three sections to earn its name)

If the user wants something shorter than the floor, recommend a different voice or a different format. Don't compress.

## How to apply a voice to a draft

When rewriting an existing draft (the common case — they're repurposing a Reddit post or a rough essay), don't try to apply all the rules at once. Run in this order:

1. **Structural surgery first.** Reorder paragraphs to fit the voice's opening pattern (PG: flat claim first; Housel: anecdote first; Thompson: news hook first; Urban: rhetorical question or "ok so"; patio11: wide aperture).
2. **Sentence-rhythm pass.** Match the voice's sentence-length distribution. Housel needs one-sentence paragraphs; Thompson needs long hypotactic sentences with semicolons; PG mixes sharp.
3. **Vocabulary swap.** Replace the draft's vocabulary against the "prefers / avoids" lists.
4. **Tells pass.** Insert the signature moves — PG's "the trick is," patio11's parenthetical asides, Housel's "two-things-are-the-same" reframe, Urban's named metaphor, Thompson's "the implication is."
5. **Read the result against "When NOT to use this voice."** If the destination matches any of those anti-contexts, stop and propose a different author.
6. **De-slop pass — non-negotiable.** See the section below. The voice rules above operate at sentence level; AI-shaped *structure* survives them. This pass is what makes the difference between "sounds like the author" and "fools a hostile reader."

Show the user the rewritten draft with a one-line note on what you changed structurally — not a bullet list of every edit. They want the new draft, not a changelog.

## The de-slop pass (Step 6)

The voice rules catch vocabulary, rhythm, and tics. They do not catch the *shape* of the essay — its narrative arc, its closing move, its takeaway architecture. Those are where AI-shaped prose reasserts itself even when every sentence reads convincingly. This pass targets those specifically. Read the rewritten draft top-to-bottom one more time and check for each pattern below.

### Universal structural tells (applies to all five authors)

These are not author-specific — they are the AI prose patterns that survive voice application. The Reddit voice rules in `voice.md` catch them at sentence level; here we catch them at essay level.

- **The "three-takeaways" closer.** A numbered/bolded list of three lessons at the end of the piece ("Three things I would tell anyone before they X:" followed by **Lesson 1…** / **Lesson 2…** / **Lesson 3…**). None of the five authors write this way. Fix: braid the lessons through the body, or end on one of them as a single observation, or drop the list entirely. If you must enumerate, two or four points reads less AI than three.
- **The neat setup → tension → climax → resolution → moral arc.** ChatGPT's default essay shape. If the rewrite can be summarized as "we did X, then problem Y emerged, then we realized Z, then we fixed it, and the deeper lesson is W," the arc is doing the writing instead of the substance. Fix: end mid-thought, drop the resolution, or hit the climax in paragraph two and digress from there.
- **The "what this is really about" / "the real lesson is" closer.** The single most AI-shaped sentence shape in English prose. Every flavor — "The thing this story is really about, though…", "What this comes down to is…", "The deeper question here is…" — is the same move. None of the five authors do this. Fix: delete the sentence. Trust the reader to extract the moral.
- **The both-sides hedge in the conclusion.** "X is right in some ways and wrong in others." / "There's no clear answer here." / "…no matter which side of the trade-off you weight more heavily." Real essayists commit. Fix: pick a side or end on the open question without flattening it.
- **The rule of three.** Three-part lists in body prose, three-part sentence structures ("It was faster, cheaper, and easier"), three negations ("Not X. Not Y. Not Z."). Universal AI rhythm. Fix: drop one to make it two, or add a fourth.
- **The "this is obvious in retrospect" sentence.** Especially when followed by a contrast. Common AI move; rarely earns its keep.
- **Smooth section transitions.** "Furthermore," "Additionally," "What's more," "It's worth noting that…" None of the five authors use these. Fix: just go to the next sentence.
- **Bolded inline-list headers.** "**Speed:** We made it faster. / **Cost:** It got cheaper." This is the most distinctive AI pattern on the internet. None of the five do this in body prose. (Thompson uses *section* headers, which is different — those are H2-level, not inline.) Fix: turn into running prose.

### Per-author structural anti-patterns

These are the specific structural moves *this author* would not make. Check the rewrite against the relevant block for the chosen voice.

- **Paul Graham wouldn't:**
  - End on a moral. PG essays end on a forward-pointing line or a quietly defiant claim — never a recap, never a "what this is really about."
  - Bold his takeaways. PG bolds nothing in body prose.
  - Number his lessons. PG numbers structural moves ("Four steps:…") but not retrospective takeaways.
  - Write a balanced conclusion. He picks a side and ends there.

- **Patrick McKenzie (patio11) wouldn't:**
  - Close with a bolded numbered takeaways list. patio11 essays end on a quiet observation ("And there is the rub.") or simply stop. The "three lessons learned" architecture is exactly the corporate-blog reflex he's allergic to.
  - Resolve cleanly. The arc digresses, hits the load-bearing claim mid-essay, then keeps going. The final paragraph isn't the climax; it's a sidelong observation that gestures at what the essay was really about.
  - Moralize the takeaway. His parenthetical asides do the moralizing — quietly, in passing. The closer is never "the real lesson is X."

- **Morgan Housel wouldn't:**
  - End with a call to action or a structural takeaway list. Every Housel essay closes with a pullback — a quote from someone outside the topic, a cosmic reframe, or a single line that recasts the whole essay. Never a numbered list.
  - Write a balanced conclusion. His closers commit, even when they're aphoristic.

- **Tim Urban wouldn't:**
  - Close with a moralizing thesis sentence. WBW essays usually end with a casual deflation, a parenthetical, or an invitation to keep thinking. Not "and the real lesson is X."
  - Use the rule of three for emphasis. He uses *rhetorical questions* for emphasis. Different rhythm.

- **Ben Thompson wouldn't:**
  - End hedged. Thompson essays close with a definitive, often deliberately heretical claim. "We don't yet know" is fine as an aside; it is not a closer.
  - Number his takeaways at the bottom. The framework *is* the takeaway, and it's named earlier in the piece. A retrospective bulleted summary undoes the architecture.

### After the de-slop pass

Read the rewrite one more time. If you cut a takeaway list, the lessons should be visible *inside* the body of the piece — usually as parentheticals, single-sentence paragraphs, or observations folded into the analytical passages. If they're not visible, the body wasn't doing the work; the takeaway list was. That's a content problem, not a voice problem, and the fix is to strengthen the body, not to put the list back.

If you find yourself making any of the listed structural moves "because it would be a better essay that way" — that's the AI shape talking. The voice rules are not optional cosmetics. They are the difference between a piece that reads as the named author and one that reads as ChatGPT in costume.

## When the user pushes back

If the user says "this doesn't sound like X to me," the failure is almost always one of three things:
- **The opening is still in the original voice.** Most voice signatures live in the first two paragraphs. Rewrite the open first.
- **The substance is too thin for the voice.** PG and Thompson especially need a real argument; if the underlying claim is "we shipped a feature," no voice will save it.
- **The destination is wrong.** Re-check the "When NOT to use" section. If the user is putting Thompson voice on a 200-word LinkedIn post, the voice will fight the format.

Diagnose before re-drafting. Don't just shuffle words.

---

## Paul Graham

**Where this fits:** Personal essays, blog longform, Hacker News submissions, founder/maker think-pieces, Substack. Falls flat in Reddit-native posts, technical reference, news writing, or any context that demands hedged neutrality or institutional voice.

**The voice in one paragraph:** PG sounds like a smart friend thinking out loud in plain English. Short Germanic words, declarative sentences, and an unbroken first-person stance: he states a claim, qualifies it just enough to be honest, and keeps moving. The register is conversational but argumentative — every paragraph is making a point, not setting a scene. Within the first paragraph you usually get a flat assertion, a small reframing of a familiar concept, and a promise that the rest of the essay will untangle it.

**Rules (do these):**
1. Open with a flat declarative claim, no setup. "Actually startups take off because the founders make them take off." First sentence is argued, not announced.
2. Mix sentence lengths sharply. Long explanatory sentence, then a four-word punch. ("They always get things wrong.") Never two long sentences in a row.
3. Use "I" and "you" freely. "I think," "I've noticed," "you'll find," "you have to." Never "we" except for actual group ownership (YC, Viaweb).
4. Define your terms by reframing, not by jargon. ("What was political correctness, exactly? ... An aggressively performative focus on social justice.") Coin a phrase, then immediately gloss it.
5. Argue by analogy from a different domain — painting, sailing, cranking a car engine, Renaissance Florence. The analogy carries the point; don't over-explain it.
6. Voice counterarguments as imagined objections from a generic skeptic, then knock them down in one sentence. "This can't be how the big, famous startups got started, they think. The mistake they make is..."
7. Use parenthetical asides for honest qualifications, not throwaway humor. "(in the narrow sense of ability to solve pre-set problems)"
8. Park digressions in numbered footnotes [1] [2]. Keep the main line clean.
9. End paragraphs on the strong sentence. Don't trail off with a summary; let the assertion land.
10. End essays on a forward-pointing or quietly defiant line, not a recap. ("If you're interested, you're not astray." / "...grab it.")
11. Avoid hedging adverbs (very, really, quite) except for rhetorical compression. Prefer "often," "usually," "rarely" — soft quantifiers that sound like an honest estimate.
12. Number your structure when you have one ("Four steps: choose a field, learn enough to get to the frontier, notice gaps, explore promising ones.") but never use bolded bullet lists in body prose. Headers, yes; bulleted product-marketing lists, no.

**Tells / signatures (the distinctive tics):**
- "The trick is..." / "The way to think about it is..." / "The question to ask is not X but Y." Clausal pivots that reframe the problem.
- "Actually, ..." or "In fact, ..." opening a paragraph to overturn the reader's prior belief.
- "It's not that X. It's that Y." Negation-then-replacement as a one-line argument.
- Throwaway concession in parens: "(as they were then called)", "(usually the CEO)" — small honesty markers that cost nothing.
- The single italicized word for emphasis: "they don't *believe* us," "no one was getting *reported* for it."
- Soft self-citation: "I've seen it happen." / "I remember noticing that at the time." — uses experience as evidence without "as I argued in my last essay" puffery.

**Vocabulary preferences:**
- Prefers: short Germanic words ("get," "make," "do," "find," "guess," "trick," "fix"), "thing/things," "good," "bad," "right," "wrong," "weird," "ok," "stuff," "kind of," "sort of," "actually," "in fact," "usually," "often," "rarely," "the trick is," "the question is."
- Avoids: corporate/promotional vocab (leverage, optimize, robust, scalable, journey, unlock, empower), Latinate hedges (utilize, facilitate, demonstrate, endeavor), academic register (heretofore, paradigm, framework), excited modifiers (incredible, amazing, game-changing), rule-of-three list adjectives ("fast, simple, and powerful").

**Before/after transformations (3 examples):**

*Example 1 — founder writing about a launch*
Generic version:
> We're thrilled to announce the launch of our new analytics platform. After months of hard work, we've built something we believe will revolutionize how teams understand their data.

PG version:
> We launched the analytics tool today. The interesting thing we learned building it is that most teams don't actually want more data — they want fewer numbers, but the right ones. That sounds obvious in retrospect. It wasn't obvious when we started.

*Example 2 — engineer writing about a side project*
Generic version:
> I've been exploring the fascinating intersection of LLMs and developer tooling. There are many exciting opportunities to leverage AI to enhance productivity.

PG version:
> I've been writing a small tool that uses an LLM to read my code. It's not very good yet. But it's already useful in one narrow way: it catches the kind of mistake you only see when you read your own code out loud a week later. I didn't expect that to be the part that worked.

*Example 3 — writer reflecting on a career change*
Generic version:
> Leaving my corporate job was the best decision I ever made. It taught me invaluable lessons about resilience and pursuing your passion.

PG version:
> I quit the job in March. The thing nobody tells you about quitting is that the first month feels like a vacation and the second month feels like you've made a terrible mistake. Both feelings are wrong. You don't really know anything about the decision for about a year.

**When NOT to use this voice:**
- Reddit-native posts. Reddit punishes the essayist register; it reads as smug or AI.
- Customer-facing marketing pages. PG's flat assertions sound undercooked in a hero section.
- Technical reference docs or changelogs. The "I think" / "the trick is" stance is wrong for normative documentation.
- News reporting or anything requiring institutional neutrality. PG's voice is unmistakably one person with opinions.

*Corpus read: How to Do Great Work; Do Things That Don't Scale; Writing, Briefly; The Origins of Wokeness; How to Think for Yourself; What I've Learned from Users; Maker's Schedule, Manager's Schedule; Cities and Ambition; Hackers and Painters; Beating the Averages; Founder Mode; Heresy; Superlinear Returns; A Project of One's Own.*

---

## Patrick McKenzie (patio11)

**Where this fits:** Long-form B2B essays, fintech/regulatory explainers, Substack-style deep dives, analyst pieces aimed at sophisticated professionals who appreciate qualification and precision. Works for newsletters, internal memos to executives, expert-witness-shaped writing. Falls flat on Reddit (too polished, too long), social media threads (cadence breaks), terse marketing copy (he refuses to compress), and anything requiring punchy hooks.

**The voice in one paragraph:** A patio11 essay reads like a well-credentialed insider patiently explaining how the machine actually works to a smart friend who lacks the domain knowledge. The register is formal-but-warm: long, carefully nested sentences carrying technical claims, broken up by short declarative thuds for emphasis, and laced with parenthetical asides that hedge, qualify, or wink. It opens at a wide aperture (a news item, a personal anecdote, a thought experiment) before zooming into the structural argument, and it routinely names its own epistemic limits before making strong claims.

**Rules (do these):**
1. Open with a wide aperture, not the thesis. Lead with a news item, anecdote, or thought experiment ("Imagine something a wee bit outside your comfort zone"; "A friend of mine, who works in finance, asked me…"; "The New York Times recently ran a piece on…"). Get to the structural claim in paragraph 3-5.
2. Vary sentence length aggressively. Long, comma-laden, parenthetical-stuffed sentences should be punctured by short declarative thuds ("Lying to a bank is a crime." "Read on for the long version." "It is bundles all the way down.").
3. Use parentheticals every 4-6 sentences for context, qualification, or a wry aside — never for the load-bearing claim. ("A useful jargon word to know: if you have plastic with your bank's name on it, that makes the bank the *issuer*."; "the geeks dreamed up next").
4. Pre-disclose your epistemic stance. State what you know less well and why ("This issue will be more U.S.-centric than I like"; "for reasons which are slightly too complicated to get into in this piece"; "I'm not a lawyer. I am not your lawyer.").
5. Use "one" and the second-person "you" interchangeably; prefer "one" when describing a class of actors and "you" when implicating the reader.
6. Italicize for surgical emphasis on a single word, not for sarcasm. Bold whole sentences only for the load-bearing thesis line.
7. Introduce technical terms in apposition with a plain-English gloss, then use the jargon thereafter. ("electronic access devices — the magnetic-stripe cards, and keyfobs, and *whatever the geeks dreamed up next*").
8. Stack short paragraphs at the start to ratchet up rhetorical pressure (the "A claim which will be more surprising:… Another:… Still another:…" move).
9. Hedge confidently. Use "I'd expect," "in broad outlines," "can't opine intelligently on them without doing more reading," and similar — they signal competence, not weakness.
10. Use rule-of-three sparingly and only for parallel structure ("you can't say X. Every institution factually does X. The successful way to phrase it is different."). Do not use it for cosmetic cadence.
11. Reach for a vivid analogy when explaining structure — Mandelbrot set, mouse droppings, ledger as object permanence — but only once or twice per essay; do not sprinkle them.
12. End sections with a quiet punchline rather than a summary. ("And there is the rub.")

**Tells / signatures (the distinctive tics):**
- "I have written about X previously" / "When we discussed Y" as a hyperlink scaffold to prior work.
- Stripe disclaimer reflex: "I'm going to talk fairly confidently about [industry] in a moment, and will repeat my usual disclaimer that I work at Stripe."
- "Insiders" / "professionals" / "the industry" as in-group nouns; he positions himself as translating from this group rather than performing membership.
- The "It doesn't matter what you think while you're doing it" construction — flat repetition of a rule for rhetorical weight.
- Mock-formal escalation: "Confound your cultural relativism!", "Phew. Pass me the Shakespeare."
- "e.g." used as a sentence-internal aside ("on e.g. a particular entrepreneur's personal rewards card").

**Vocabulary preferences:**
- Prefers: "one," "professionals," "decisionmaking authority," "in broad outlines," "structurally," "the industry," "auto-catalyzing," "compliance-grade" technical terms paired with plain-English glosses, "non-trivial," "voluminous evidence," "the rub."
- Avoids: marketing/promotional vocab ("game-changer," "leverage," "unlock"), gratuitous slang, brand-dropping for credibility, exclamation points (mostly), buzzword stacks, and emoji.

**Before/after transformations (3 examples):**

*Example 1 — founder explaining their pricing model*
Generic version:
> We charge per seat because it scales with the value you get. As your team grows, you pay more, which feels fair to most customers.

patio11 version:
> We price per seat, which is the default mental model for B2B SaaS and which (not coincidentally) is the model procurement departments are best equipped to underwrite. The fairness argument — value grows with headcount — is real but secondary. The actual reason is more boring: per-seat pricing is the only model your buyer's finance team already has a budget line for.

*Example 2 — explaining interchange fees to a non-fintech audience*
Generic version:
> Every time you swipe a credit card, the merchant pays a fee. Most of that fee goes to the bank that issued your card, which is how they fund rewards programs.

patio11 version:
> Consider the humble credit card swipe. The merchant pays a fee, typically 1.5-3%, and the lion's share of that fee flows to the issuer — that is, the bank whose name is on the plastic. (Networks and acquirers get smaller cuts; we'll set them aside.) This is how the issuer funds your rewards program, and it is why the rewards program exists: rewards are not, structurally, a gift. They are a rebate of interchange the issuer would otherwise keep.

*Example 3 — B2B SaaS founder describing why their support is slow*
Generic version:
> Our support team is small, so response times can be longer than we'd like. We're hiring to fix this.

patio11 version:
> Support, in any company at our stage, is a series of triage decisions made under a budget constraint that customers neither see nor consent to. We staff to the median ticket and hope the tail is short. (It is, mostly. The exceptions are extremely visible to the people inside them, which is exactly what makes them feel like an indictment of the whole function.) We are hiring, but the honest answer is that "faster support" is a phrase that hides a pricing decision.

**When NOT to use this voice:**
- Reddit-native posts (the parentheticals and length read as performative; mods and commenters will flag it as AI-polished).
- Twitter/X threads or any platform where the unit of consumption is one paragraph — patio11 needs runway.
- Landing pages, ad copy, sales emails, any context with a hard word limit or a single-CTA goal.
- Hostile or adversarial writing (the warmth and qualification undercut the punch); patio11 is bad at being mean.

*Corpus read: Salary Negotiation for Engineers; Don't Call Yourself a Programmer; Falsehoods Programmers Believe About Names; Identity Theft, Credit Reports, and You; How Discount Brokerages Make Money; Tether: The Story So Far; Seeing Like a Bank; How Credit Cards Make Money; Deposit Insurance; Notes on a non-profit indicted for bank fraud; One Regulation E, Two Very Different Regimes; Fraud Investigation is Believing Your Lying Eyes.*

---

## Morgan Housel

**Where this fits:** Behavioral-finance essays, decision-making pieces, founder-reflection posts about money/risk/luck/time, long-form Substack essays that need to feel wise rather than instructive, LinkedIn thought-pieces. Falls flat in: technical deep-dives, product launches, anything that requires sustained step-by-step argument, Reddit-native posts, sales copy, or pieces where the reader needs to *do* something specific by the end.

**The voice in one paragraph:** A Housel essay reads like a quiet person leaning across a table to tell you a story about a dead millionaire secretary, then pulling back to a single bolded sentence that reframes everything. The rhythm is built on radical paragraph-length variation — long story paragraphs alternating with one-sentence paragraphs that act like breath marks. He almost never asserts a claim before he's told you a story; the structure is anecdote → universal claim → restatement of the anecdote. The tone is calm, slightly wistful, allergic to jargon, and built around the discovery that two opposite-looking things are actually the same thing.

**Rules (do these):**
1. Use one-sentence paragraphs liberally. About one in three paragraphs in a Housel essay is a single sentence. They function as punctuation between longer story paragraphs, not as filler.
2. Open with a specific, named human and a small concrete fact about their life ("Grace Groner was orphaned at age 12. She never married. She never had kids. She never drove a car."). Never open with a thesis.
3. Tell the story first. Drop the abstract claim only after the reader has the picture. The structure is: anecdote → universal claim → restatement of the anecdote.
4. Bold the thesis sentences when they finally arrive. Use bold sparingly — only the line that reframes everything.
5. Use the "two things are the same" move constantly: "Luck and risk are two sides of the same coin." "Calm plants the seeds of crazy." "Getting rich and staying rich are different skills." Find the opposite that's secretly identical.
6. Stack short declarative sentences in a deliberate cadence when building toward a conclusion. "If markets never crashed they wouldn't be risky. / If they weren't risky they would get expensive. / When they're expensive they crash."
7. Lists should be numbered and each item should be a complete, headline-sized claim in bold, followed by a story or example. Not bullet fragments.
8. End on a wide-angle pullback — a quote from someone unexpected (Nixon, Dostoyevsky, a Scottish proverb), a cosmic reframe ("the only species out of 8.7 million on this planet that can read"), or a single sentence that recasts the whole essay. Never a call to action.
9. Use historical anecdotes as proof, not as decoration. The 1945 GI Bill, the 1929 crash, Walt Disney's pre-Snow White bankruptcy, a 1903 William Dawson book — specific dates, specific numbers, specific names.
10. Generalize from one person to all people, fast: "I have seen investors justify…" → "But self-interest is a freight train of persuasion." Move from the specific case to the universal claim within two sentences.
11. Use rhetorical questions in clusters of three or four, each a one-line paragraph: "And then what? / What were they going to do next? / Where were they going to work?"
12. Translate every number into a feeling or a comparison. "21,000 venture financings" gets followed by "65% lost money." "Monster Beverage stock rose 211,000%" is immediately paired with "But it lost more than half its value on five separate occasions."

**Tells / signatures (the distinctive tics):**
- The em-dash aside that sneaks in a second clause: "By all accounts, a lovely lady. But she lived a humble and quiet life."
- "Same as ever," "always been like that, always will be," "history is just one damn thing after another" — the phrase that closes the loop on universality.
- The bolded reframe sentence that contradicts the obvious read of the story: **"It's to point out that there is no other field where these stories are even possible."**
- Italicized phrases mid-paragraph for emphasis, almost always for a colloquial idea: *"this is obvious"*, *"I did this. I bought this. With my own money."*
- Letters to his son as a device for delivering tender moralizing without preaching directly.
- The "rule of thumb" sentence used as scaffolding: "Rule of thumb: Anything that is huge, profitable, famous, or influential is the result of a tail event."
- Closing on a quote from someone wildly outside the topic (Krishnamurti, Nixon, Dostoyevsky, Montesquieu, a Scottish proverb).

**Vocabulary preferences:**
- Prefers: plain Anglo-Saxon words; "interesting" as a marker word; "luck and risk"; "behavior"; "ordinary"; "humble"; "stuff"; "messy"; "paranoid"; "the gap between X and Y"; "tail"; "compounding"; concrete dollar figures and percentages.
- Avoids: financial jargon without translation, "leverage" as a verb, "ecosystem," "synergy," promotional language, hedged corporate phrasing, complex syntax, three-clause sentences when one will do, anything that sounds like a CFA exam answer.

**Before/after transformations (3 examples):**

*Example 1 — founder reflecting on a hiring mistake*
Generic version:
> Last year I made a critical hiring mistake. I hired a senior engineer based on his impressive credentials without spending enough time understanding his working style. It cost us six months and significant team morale. The lesson is that you need to weight cultural fit equally with technical ability.

Housel version:
> Daniel had a Stanford CS degree, eight years at Stripe, and a recommendation from someone I trusted completely. He lasted four months.
>
> I didn't hire him for what he could do. I hired him for what he had done.
>
> Those are different things, and it took me six months and two resignations to figure that out.
>
> **The best predictor of how someone will work with you is not their résumé. It's the texture of how they answer a question they don't know the answer to.** Daniel's résumé was flawless. The texture was wrong. I missed it because I wasn't looking.
>
> Every hiring mistake I've ever made looks like this in hindsight. The signal was there. I just wasn't reading the right frequency.

*Example 2 — bootstrapped founder writing about why they didn't raise*
Generic version:
> We considered raising a Series A but ultimately decided to stay bootstrapped. Outside capital would have accelerated growth but at the cost of optionality. We wanted to build a company we'd be proud of in ten years, not a company that hit a milestone in eighteen months.

Housel version:
> In 2019 I had two offers on the table for a Series A. I turned them both down. People thought I was crazy.
>
> Five years later I think I was right. But not for the reasons I gave at the time.
>
> I told everyone it was about optionality. About control. About building something durable. All of that was true. None of that was the real reason.
>
> The real reason is that I didn't trust myself with the money. I had watched three friends raise large rounds and within eighteen months they were running companies they no longer recognized. The capital didn't change their strategy. It changed their *taste* for what counted as a problem worth solving.
>
> **Money doesn't just buy things. It rearranges what you find interesting.** That's the part nobody warns you about, and it's the part that matters most.

*Example 3 — Substack short about a hobby that became serious*
Generic version:
> I started running during the pandemic as a way to manage stress. Three years later I ran my first marathon. The experience taught me that consistency matters more than intensity and that small daily habits compound into significant change.

Housel version:
> I started running in April 2020 because I couldn't stop pacing the apartment. The first mile took me eleven minutes and I had to walk twice.
>
> Three years later I ran a marathon. I am not a good runner. I am, by any honest measure, a slow and ordinary middle-aged man with a hobby.
>
> But here is the part that surprises me.
>
> The marathon was not the hard thing. The hard thing was the 873 days between the first mile and the marathon, during which absolutely nothing felt like progress. There was no day I could point to and say, *this is when it clicked*. There was just the next morning, and the next one.
>
> **Compounding is invisible until it isn't.** I knew this from a spreadsheet. I did not know it from my legs.

**When NOT to use this voice:**
- Reddit-native posts. Housel's bolded-thesis-and-historical-quote architecture screams "essay" and "polish," which is exactly the AI-slop / corporate-blogger trigger that gets posts buried on r/startups or r/SaaS.
- Technical writing or product documentation. The story-first structure delays the information the reader actually needs.
- Sustained argumentative pieces (a policy white paper, a strategy memo). Housel's voice works through accumulation of aphorism, not through building a case. It cannot defend a position against pushback.
- Sales copy, launch posts, or anything where the reader needs a specific next action. The voice ends in reflection, not in CTA — every Housel essay closes with a quote or a pullback, never with "click here."
- Short-form social (tweets, captions). The voice needs room to breathe — at least 400 words to set up the anecdote → claim → restatement structure. Compressed, it just reads as a fortune cookie.

*Corpus read: The Psychology of Money; A Few Laws of Getting Rich; Useful Hacks; How This All Happened; Tails, You Win; Ideas That Changed My Life; The Art and Science of Spending Money; The Laws of Investing; Risk is How Much Time You Need; Getting Rich vs. Staying Rich; Little Rules About Big Things.*

---

## Tim Urban (Wait But Why)

**Where this fits:** Long-form accessible explainers where you're taking something huge, technical, or existential (AI, mortality, careers, genealogy) and making the reader actually feel it. Substack deep-dives, blog posts for the technically curious general audience, "I'm going to make this giant topic feel small" essays. Falls flat in: anything under 800 words, Reddit-native posts (too writerly, too many asides), formal business writing, terse product copy, hard news.

**The voice in one paragraph:** A Wait But Why essay reads like a smart friend thinking out loud at you, mid-sentence, on a couch. The defining moves: constant second-person ("you"), rhetorical questions that he then answers himself, parenthetical and footnote asides that argue with the main text, a willingness to swear casually ("fuck it," "a fuckton of dumplings"), and extended named metaphors (the Instant Gratification Monkey, the Social Survival Mammoth, the Yearning Octopus) that become structural scaffolding for the whole piece. He name-checks his own confusion, deflates his own drama, and treats the reader as co-explorer rather than audience.

**Rules (do these):**
1. Address the reader as "you" constantly. Implicate them in the topic ("I don't know you, but I can almost guarantee that you don't ask your grandparents enough questions").
2. Pose a rhetorical question, then answer it in the next sentence. Use questions as structural pivots, not as ornaments.
3. Open with either a self-deprecating personal anecdote, a flat admission of human limitation ("Humans are good at a lot of things, but X is not one of them"), or a casual "Ok so" / "Welcome to Part 2 of the..." entry.
4. Coin a named metaphor and ride it for the whole essay. Capitalize it. Refer back to it like it's a character (the Fog, the Dark Playground, the Cook, the Mammoth).
5. Make abstract scale concrete with one absurd domestic analogy. A whole life fits in a tablespoon. Modern humans = 1 second of Earth's day.
6. Break the fourth wall. Admit the post took too long, that you got distracted googling, that you flip-flopped, that you're not sure you're qualified.
7. Use parenthetical asides as a running second voice. (Often a joke.) (Sometimes a clarification.) (Sometimes just "Dammit.")
8. Mix elevated content with very casual register: "nahhhhh," "kind of," "totally," "huh," "Pretty Kool-Aid worthy."
9. Promise length upfront and apologize for it ("It's been a long one, I know") — then keep going anyway.
10. Use footnotes that argue with, undercut, or extend the main text — never just citations.
11. Repeat phrases for rhythm and emphasis. Build a callback economy.
12. When something is weird, say "this is going to sound weird" before saying it.

**Tells / signatures (the distinctive tics):**
- Italicized stretched-out words for tonal effect: *nahhhhh*, *unnormal*, *really*.
- Phrases like "the thing is," "ok so," "kind of a weird thing for us to do," "I have problems."
- Hand-drawn stick-figure aesthetic carried into the prose — described diagrams, "imagine a chart where..."
- Self-aware acknowledgment of the essay's own scale: "I want to pause here to remind you that every single thing I'm going to say is real."
- Naming and capitalizing inner mental forces (the Panic Monster, the Authentic Voice, the Yearning Octopus).
- Profanity used sparingly but punctually — not as edge, as exhale.

**Vocabulary preferences:**
- Prefers: "weird," "kind of," "actually," "ok so," "the thing is," "totally," "super," "huh," "shit," "stuff," "a lot," "really really," "nahhhh," "creature," "mess," "deep dive," "unpack."
- Avoids: academic register, jargon-without-translation, promotional vocab ("revolutionize," "leverage," "best-in-class"), corporate hedging, em-dash-only sentence rhythm, the bolded-list reflex, anything ending in "-ize."

**Before/after transformations (3 examples):**

*Example 1 — founder explaining why they changed direction*
Generic version:
> After extensive customer research, we realized our initial hypothesis was incorrect. We've decided to pivot the product toward a different segment based on what we learned.

Tim Urban version:
> Ok so here's the thing. For about eight months I was completely sure I knew who this product was for. Like, *sure*-sure. Then we actually talked to those people and it turned out almost none of them wanted it. Huh. Weird feeling, being that wrong about something you've been confident about for that long. (It's a feeling I'm getting used to.) So we're building something different now. I'll tell you who for in a second.

*Example 2 — explaining compound interest*
Generic version:
> Compound interest is when the returns on your investment also earn returns. Over long time horizons, this exponential growth becomes substantial.

Tim Urban version:
> Imagine a tiny money-creature that, every year, makes a baby money-creature exactly its size. Now imagine those babies also make babies. You see where this is going. The weird part — and this is where my brain breaks every time — is that for the first twenty years it barely looks like anything is happening. Then around year thirty the whole thing goes vertical and you stare at the chart like, wait, that's me?

*Example 3 — describing a deadline you missed*
Generic version:
> The project took longer than expected due to unforeseen complexity. We apologize for the delay.

Tim Urban version:
> I said this would take two weeks. It took eleven. In my defense, every single thing I thought would be easy turned out to be a trapdoor into a longer, weirder thing. (At one point I spent a full afternoon learning how PDF fonts work. Why. Why did I do that.) Anyway. Here it is.

**When NOT to use this voice:**
- Reddit-native posts. It reads as "writer voice" — too constructed, too many asides, too long. Reddit wants flatter.
- Cold emails, terse memos, anything under ~500 words. The voice needs room to digress; without room it just reads twitchy.
- Formal business contexts — board updates, investor docs, contracts, support replies. The casualness reads as unserious.
- Anywhere the reader is impatient or hostile. WBW voice assumes a generous reader willing to hang out. A reader who isn't hanging out will bounce on the second parenthetical.

*Corpus read: The Tail End, How to Pick a Career (That Actually Fits You), Why Procrastinators Procrastinate, Religion for the Nonreligious, The AI Revolution Parts 1+2, Putting Time in Perspective, Your Family Past Present Future, The Cook and the Chef, Your Life in Weeks, Taming the Mammoth.*

---

## Ben Thompson (Stratechery)

**Where this fits:** Strategic analysis of platforms, business models, and industry dynamics; long-form newsletter essays; explainer pieces that introduce a named framework; B2B positioning posts that argue from first principles; investor memos and Substack deep-dives where readers expect 1,500-3,000 words of disciplined reasoning. Falls flat in: anything short, anything emotional, anything where the reader has not opted in to a thesis-driven essay.

**The voice in one paragraph:** A Stratechery piece is recognizable from the first paragraph: it opens with a news hook or historical analogy, names a framework (often a capitalized noun phrase: Aggregation Theory, the Bill Gates Line, the Moat Map), then advances through bolded H2 sections, each making exactly one analytical move. Sentences are long and hypotactic, built with semicolons, em-dashes, and embedded clauses. Thompson does not narrate; he argues. Every paragraph follows a claim-evidence-implication rhythm, and the piece ends not with a wrap-up but with a definitive — sometimes deliberately heretical — claim the framework has earned.

**Rules (do these):**
1. Open with a concrete hook: a news event, a quotation, or a historical parallel (autos in 1920, Gates dismissing Facebook Platform, Christensen's iPhone prediction). Never open with the thesis directly.
2. Name your framework in capitalized noun form on first use ("Aggregation Theory," "the Moat Map," "Super-Aggregators"), then refer back to it as a proper noun throughout.
3. Structure the piece in bolded H2 section headers. Each section advances exactly one move: definition, mechanism, case study, counter-case, implication.
4. Define terms before using them. Distinguish near-synonyms explicitly ("platforms versus aggregators," "low-end disruption versus new-market disruption").
5. Use the claim-evidence-implication paragraph. State the claim, ground it in a specific company or historical example, end with "the result is" or "the implication is" before moving on.
6. Write long sentences. Use semicolons, em-dashes, and "to wit" / "that is to say" / "to be clear" as clausal pivots. Hypotaxis over parataxis.
7. Build lists of named companies as evidence ladders: Google did X, Facebook did Y, Amazon did Z, Netflix did W. Three to five is the canonical count.
8. Link to your prior posts as load-bearing scaffolding — treat earlier Stratechery essays as established premises the reader either knows or can look up.
9. Handle counterargument head-on with a named opponent (Christensen, Yelp, Zuckerberg). Steelman it in a paragraph, then dismantle it on framework grounds.
10. Close with a definitive claim, not a hedge. End on the framework's strongest prediction ("nearly every industry will belatedly discover…", "Christensen is going to go 0 for 3").
11. Use "the" possessively when naming a phenomenon: "the result," "the problem," "the implication," "the point." Definite-article framing makes claims feel deduced rather than asserted.
12. Stay in the analyst's third person. The first person appears sparingly, mostly to flag uncertainty or hometown anecdote.

**Tells / signatures (the distinctive tics):**
- Opens with a news hook or historical analogy, then pivots with "What's actually going on here is…" or "This pattern is not new."
- Capitalizes coined concepts on first use, then drops the capitalization once they're load-bearing.
- "The result is…" and "The implication is…" as section- or paragraph-closing pivots.
- Three- or four-bullet evidence ladders of named companies, each one sentence, parallel-structured.
- Frequent self-citation: "As I wrote in [linked prior essay]…"
- Em-dash insertions for definitional asides — like this — inside otherwise hypotactic sentences.
- Deliberately heretical closing claim against received industry wisdom.

**Vocabulary preferences:**
- Prefers: *aggregation, aggregator, incumbent, modularize, integrate, commoditize, leverage, moat, disintermediate, virtuous cycle, marginal cost, supplier, distribution, demand, scaffolding, to wit, that is to say, to be clear, the result is, the implication is, fundamentally, structurally*
- Avoids: casual register, slang, "guys," exclamation points, undefined jargon, emoji, hedges like "maybe" or "kind of," sweeping claims without a named framework behind them, rule-of-three rhetorical flourishes for their own sake.

**Before/after transformations (3 examples):**

*Example 1 — founder explaining go-to-market*
Generic version:
> We focus on bottoms-up adoption. Individual developers find us, love the product, and bring it into their companies. That's a much more efficient way to grow than top-down sales.

Thompson version:
> The company's distribution strategy inverts the traditional enterprise model. Where incumbent vendors capture buyers and impose tools on users, this approach captures users — individual developers — and lets demand propagate upward. The result is a structural advantage on customer acquisition cost: the buyer arrives pre-sold by the very people who will use the product, collapsing the sales cycle from quarters to days.

*Example 2 — competitive positioning against a giant*
Generic version:
> Salesforce is huge but their UX is terrible. We're building something modern and developers love it. We think we can win.

Thompson version:
> Salesforce occupies the classic incumbent position: it owns the buyer relationship, and the buyer is not the user. That gap — between who pays and who suffers — is precisely the wedge a modular competitor exploits. To be clear, the incumbent will not lose on features; it will lose on the willingness of users to route around procurement entirely, which is the same dynamic that has played out in every category where consumerization has reached the enterprise.

*Example 3 — an AI coding tool's industry implication*
Generic version:
> AI is going to change how software gets built. Developers will be way more productive and companies that adapt will win.

Thompson version:
> The interesting question is not whether AI raises developer productivity — it plainly does — but where the value accrues. Three candidates present themselves: the model providers, the IDE incumbents who own the surface, and a new class of agentic aggregators that own the workflow. The implication of Aggregation Theory is that the workflow layer wins, because it sits closest to the user and can commoditize both model and editor underneath it. The model providers, in this telling, are the suppliers; and suppliers, in aggregation markets, are the ones who lose pricing power.

**When NOT to use this voice:**
- Reddit-native posts, especially in r/startups, r/SideProject, r/indiehackers — the framework-named, headed-section style reads as corporate and gets called AI slop instantly.
- Personal reflection, build-in-public updates, or anything where vulnerability and informality are the point.
- Short-form: tweets, LinkedIn posts, Slack messages, cold email — Thompson's voice needs 800 words minimum to earn its scaffolding.
- Customer-facing copy, onboarding, error states, marketing landing pages — anywhere the reader has not opted into a thesis-driven essay.

*Corpus read: Aggregation Theory; The Bill Gates Line; The Moat Map; Defining Aggregators; What Clayton Christensen Got Wrong; The End of the Beginning; Peak Google; Manifestos and Monopolies; The Local News Business Model; What Is a Tech Company?*
