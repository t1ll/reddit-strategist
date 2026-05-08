# Title and post templates

The same underlying truth can be packaged as different angles for different subs. The angle determines the title, opening, structure, and closing. Pick the angle first; let the title and structure follow.

## Five core angles

### 1. The "weird specific number" story
**Where it works:** r/SideProject, r/indiehackers, r/microsaas, r/Entrepreneur
**What it is:** A surprising metric is the entire hook. The post unpacks where it came from.
**Title pattern:** "[Specific weird stat]. [Brief context.]"
**Examples:**
- "71% of free-tier video gens on my AI platform got flagged as porn within a week"
- "We crossed $4K MRR after 11 months. 80% of revenue comes from a feature we almost cut."
- "I lost $1,847 in API costs over a single weekend because of one missing rate limit"

### 2. The tactical breakdown
**Where it works:** r/startups, r/programming, r/devops, r/SaaS
**What it is:** A specific problem and the exact stack/code/decisions you used to solve it. Reads like a postmortem.
**Title pattern:** "How I/we [specific outcome] with [specific approach]"
- "How I cut signup abuse by 80% with a 3-layer free-tier filter (NeverBounce + domain blacklist + credit ladder)"
- "Our API gateway's automatic failover became an NSFW delivery pipeline. Postmortem."
- "Three months of provider-routing data: latency vs. cost across 12 image-gen APIs"

### 3. The "I was wrong" / lesson post
**Where it works:** r/indiehackers, r/microsaas, r/startups (cautiously), r/Entrepreneur
**What it is:** Self-deprecating, specific, what-I-thought-vs-what-actually-happened. Vulnerability is the trade for engagement.
**Title pattern:** "I [thought / planned / believed] X. [Specific reality] proved me wrong."
- "I thought free credits would attract devs. Instead they attracted Telegram OF scam rings."
- "Our pricing page was the highest-converting page on the site. We rewrote it and lost 30%."

### 4. The metrics update / build log
**Where it works:** r/buildinpublic, r/scaleinpublic, r/SideProject (occasionally)
**What it is:** Numbers + screenshots + brief context. NOT a story. Repeatable cadence (weekly/monthly).
**Title pattern:** "[Project name] [period] update: [headline metric]"
- "lumenfall.ai April update: $4.2K MRR, 71% NSFW abuse rate, here's the dashboard"
- "Week 14 of building in public: shipped 3 features, churned 2 customers, here's why"

### 5. The technical curiosity / benchmark
**Where it works:** r/programming, r/MachineLearning, r/LocalLLaMA, HN
**What it is:** Pure technical content. No business framing. Numbers, methodology, results. Your product is mentioned in passing or in a footer.
**Title pattern:** Descriptive technical title. No emojis, no clickbait.
- "Benchmarking 12 image-generation providers on cost, latency, and content-filter behavior"
- "What happens when you give 5,000 strangers a $1 OpenAI credit (a study in abuse patterns)"

## Title rules

A Reddit title does ~80% of the work. If the title is wrong, the body doesn't matter — nobody clicks.

**Do:**
- Front-load the surprising specific. The weird number, the failure, the contradiction. Within the first 7 words.
- Keep it under ~90 chars when possible (mobile cuts it off around there).
- Use lowercase mid-sentence sometimes ("ok so this is wild" can work but is risky).
- Match the sub's title conventions. r/programming titles are descriptive and dry. r/SideProject titles can be more playful. r/buildinpublic titles often start with the project name and a period.

**Don't:**
- Start with a "How [I/we] did X" pattern unless your audience explicitly likes that (r/programming sort of does, r/SideProject is meh on it).
- Use clickbait ("You won't believe what happened when..."). Reddit downvotes on sight.
- Use a question that you immediately answer in the body. "Should you give free credits to AI users?" reads as engagement-bait.
- Use emojis in titles. They mostly read as cringe outside of certain hobby subs.
- Cap-case the title. "How I Built My SaaS" reads more SEO-y than "how i built my saas" (or sentence case "How I built my SaaS").
- Use "we" if it's just you. Reddit will call it out.

## Structural templates

These are skeletons. Fill in your own specifics. The lengths are budgets — go shorter if you can.

### Template A: The hook-then-specifics post (story-friendly subs)

Length: ~250-450 words.

```
[ONE-SENTENCE HOOK. The weirdest specific from the entire story. Lead with it.]

[ONE PARAGRAPH OF SETUP. ~3 sentences max. Who you are (briefly), what the
project is (briefly), why this happened. Do not exceed 3 sentences. If you
need more, you have not picked the right hook.]

[THE SPECIFICS. 2-3 short paragraphs of what actually happened, with concrete
details: real numbers, real prompts, real error messages, screenshots if you
can. This is where the post earns its length.]

[WHAT YOU CHANGED OR WHAT YOU LEARNED. 1 short paragraph. Not "key takeaways"
— just the actual change you made and why. Skip if obvious from the specifics.]

[OPTIONAL: One self-aware sentence at the end. "Yeah, in retrospect..." or
"would love to hear if anyone else saw this pattern."]
```

### Template B: The tactical breakdown (technical/founder subs)

Length: ~400-800 words. Numbers, structure, and zero fluff.

```
[ONE-SENTENCE PROBLEM STATEMENT. Concrete and specific.]

[CONTEXT: 2-3 sentences. Stack, scale, time period, business context as needed.]

[WHAT WE DID. List or numbered points. Each item should be a specific decision
with a specific reason. Avoid bolded headers; use plain prose or a clean
numbered list.]

1. [Specific change.] [Why we made it.] [What it did.]
2. [Same shape.]
3. [Same shape.]

[NUMBERS / OUTCOME. The actual measured result with the actual number.
"Abuse rate dropped from 71% to 4% over 14 days." Not vague.]

[CAVEATS. What this didn't fix, what we still don't know. Reddit rewards honesty
about limitations.]

[OPTIONAL: link to deeper writeup if relevant.]
```

### Template C: The metrics update (build-in-public subs)

Length: ~150-300 words. Mostly numbers and screenshots.

```
[Project name + period. e.g., "lumenfall.ai - April 2026 update"]

[Headline metric. One sentence.]

[Numbers section. 4-7 specific data points. MRR, users, churn, infra cost,
specific feature adoption. Just numbers and a short label each.]

[What shipped this period. 2-4 short bullets. Specific features, not vague
"product improvements."]

[What's next. 2-3 bullets. Be specific.]

[One open question or ask. "If anyone has seen [specific pattern], curious
what you did."]
```

## Participation prompts (engineer the comments)

Comments carry roughly twice the ranking momentum of upvotes on Reddit. The post that ends with a deliberate, specific question almost always gets more comments than the post that ends with a summary. Build the prompt into the close of the post body or as a standalone "Edit:" reply you post yourself a few minutes after submitting.

Patterns that reliably draw comments:

- **The "have you seen this?" prompt.** "Anyone else seeing the same Telegram-coordinated abuse pattern? Curious what tripwires worked for you."
- **The contradiction-invite prompt.** "I'm pretty sure I'm wrong about [specific thing] — what would you have done differently here?"
- **The methodology prompt.** "If you had a $1 free-tier budget and a small team, what would your stack look like?"
- **The shared-pain prompt.** "What's the dumbest abuse pattern you've had to fight in your free tier?"

What does NOT work:

- Generic "thoughts?" or "let me know what you think" — too low-effort, reads as content-marketer asking for engagement.
- "Has anyone else done this?" with no specific anchor — too broad to answer.
- Multiple questions in a row — pick one. People will only answer the one that catches their eye.

## Reverse: the AI-shaped title to avoid

These title patterns will get you flagged as content marketing on most major subs:

- "How [we] [verbed] [outcome]: [colon-separated framing]"
- "X lessons from [time period] of [activity]"
- "The [adjective] [noun] of [thing]"
- "Why [contrarian claim]" (overused; subs are sick of it)
- "[Number] things [audience] should know about [topic]"
- "Building in public: [generic update]"
- "From [starting point] to [ending point]" (the most blog-shaped of all blog patterns)

## Story-angle picker

Given a single underlying story, here's how to pick which of the five angles to use for which sub:

| Underlying story | Best angle | Best sub |
|---|---|---|
| New launch, decent metrics | Story (#1) or Build log (#4) | r/SideProject (story) or r/buildinpublic (log) |
| You hit unexpected abuse / fraud / weird users | Weird stat (#1) or I was wrong (#3) | r/SideProject, r/microsaas, r/indiehackers |
| You built a specific technical solution | Tactical breakdown (#2) | r/programming, r/devops, r/startups |
| You measured something across a category | Technical curiosity (#5) | r/programming, r/MachineLearning, r/LocalLLaMA |
| You changed strategy and it failed/succeeded | I was wrong (#3) | r/indiehackers, r/microsaas |
| Specific cost/billing/infrastructure war | Tactical breakdown (#2) | r/devops, r/aws, r/programming |
| Funny screenshot or absurd customer interaction | Weird stat (#1) (the screenshot IS the post) | r/SideProject, r/ProgrammerHumor (if appropriate) |

If a story doesn't naturally fit any of these angles, it probably isn't ready for Reddit. Reddit doesn't reward "we built a thing" without a hook. Find the hook (or write a different kind of post).

## When to use a link post vs self-text post

**Link post (just the URL, no body):**
- The destination is genuinely strong on its own (a blog post that reads well, a tool that's worth a click)
- You want HN-style "here's the thing, click if you want"
- The sub culture leans toward link posts (r/programming, r/MachineLearning often do)

**Self-text post (the post body IS the content):**
- You want the discussion to happen on Reddit, not your blog
- The story is short enough to fit comfortably in 400-800 words
- The sub culture leans toward self-posts (r/startups, r/SideProject, r/indiehackers, r/microsaas)

**Hybrid: short self-text + link to deeper writeup:**
- You have a genuinely strong long-form blog post
- A 200-word teaser + "full writeup at [link]" works on r/programming and r/SideProject
- Be careful: if the teaser feels like a teaser, Reddit will downvote and accuse you of just driving traffic

## Sample finished posts

### Sample 1: r/SideProject (story angle)

> 71% of free-tier video gens on my AI platform got flagged as porn in week 1
>
> Solo founder. Launched lumenfall a few weeks ago. Gave every new signup $1 in free credit because every other AI API gives you $5+ and I figured a buck was enough to play with image gen.
>
> First week: more video generations than I expected. Looked at the logs because the bill was higher than projected. 71% of video calls had hit a content filter somewhere in the pipeline.
>
> Looked at the prompts. Yeah. Specific anatomy. A lot of "[name from K-pop group]" prompts. One person had submitted variations of the same prompt 40+ times trying to find the path that didn't get blocked.
>
> Worse: my failover logic was retrying flagged prompts on a different provider. Which had laxer filters. So sometimes the filter triggered, sometimes it didn't, depending on which provider got the retry. Effectively the system was shopping the request until something generated.
>
> Killed failover for flagged content. Added a pre-generation moderation pass. Tightened the email-domain blacklist. Abuse rate is around 4% now.
>
> Kept the free dollar. Just watching more carefully.

### Sample 2: r/programming (tactical breakdown angle)

> Anti-abuse stack for a free-tier AI image API: what worked, what didn't
>
> Built a free $1 credit on signup. Got hit with a sustained NSFW abuse pattern (71% of video gens flagged in week 1). Stack ended up being:
>
> 1. Email domain blacklist for known disposable providers (NeverBounce + a hand-curated blocklist of the top 40 throwaway domains). Caught roughly 30% of abusers at signup.
>
> 2. Same-domain credit ladder: first signup from a domain gets $1, second gets $0.50, third gets $0, regardless of email uniqueness. Caught the gmail-pattern abusers.
>
> 3. Pre-generation moderation pass on every video prompt before it hits a provider. Currently using a small open model fine-tuned on the flagged-prompt corpus from week 1. ~$0.0002 per check. Catches ~95% of obvious abuse.
>
> 4. Killed automatic provider failover for any prompt that triggered any filter at any layer. This was the single biggest fix — the failover was effectively shopping requests across providers until something generated.
>
> What didn't work: hCaptcha at signup. Determined abusers solved it. Phone verification works but converts at like 50% of legitimate users so it's a non-starter for free tier.
>
> Open questions: anyone else dealt with this in the same space? Specifically curious about the org behind the most-repeated prompts — they look organized.
