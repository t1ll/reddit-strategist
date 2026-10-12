# Title and post templates

The same underlying truth can be packaged as different angles for different subs. The angle decides the title, opening, structure, and close. Pick the angle first and let the rest follow.

A note on the examples: most of them come from one real story (a free-tier AI API that got hit with NSFW abuse), with a few others mixed in. They illustrate shape, not subject matter. Don't carry the free-credit / NSFW / failover details into other users' posts, and don't invent numbers to fill a template. Every figure in a draft comes from the user; if a slot needs one you don't have, leave a placeholder like `[signups in week 1?]` and ask.

Contents:
- Five core angles
- Title rules
- Structural templates (A: hook-then-specifics, B: tactical breakdown, C: metrics update)
- Participation prompts
- AI-shaped titles to avoid
- Story-angle picker
- Link post vs self-text
- Sample finished posts

## Five core angles

### 1. The "weird specific number" story
**Where it works:** r/SideProject, r/indiehackers, r/microsaas, r/Entrepreneur
**What it is:** a surprising metric is the whole hook, and the post unpacks where it came from.
**Title pattern:** "[Specific weird stat]. [Brief context.]"
**Examples:**
- "71% of free-tier video gens on my AI platform got flagged as porn within a week"
- "We crossed $4K MRR after 11 months. 80% of revenue comes from a feature we almost cut."
- "I lost $1,847 in API costs over a single weekend because of one missing rate limit"

### 2. The tactical breakdown
**Where it works:** r/startups, r/programming, r/devops, r/SaaS
**What it is:** a specific problem and the exact stack, code, or decisions used to solve it. Reads like a postmortem.
**Title pattern:** "How I/we [specific outcome] with [specific approach]"
- "How I cut signup abuse by 80% with a free-tier filter (NeverBounce + domain blacklist + credit ladder)"
- "Our API gateway's automatic failover became an NSFW delivery pipeline. Postmortem."
- "Our CLI's install script silently failed on Alpine for six weeks. Here's why nobody reported it."

### 3. The "I was wrong" / lesson post
**Where it works:** r/indiehackers, r/microsaas, r/startups (cautiously), r/Entrepreneur
**What it is:** self-deprecating and specific: what I thought vs what actually happened. The honesty is what earns the engagement.
**Title pattern:** "I [thought / planned / believed] X. [Specific reality] proved me wrong."
- "I thought free credits would attract devs. Instead they attracted Telegram OF scam rings."
- "Our pricing page was the highest-converting page on the site. We rewrote it and lost 30%."

### 4. The metrics update / build log
**Where it works:** r/buildinpublic, r/scaleinpublic, r/SideProject (occasionally)
**What it is:** numbers, screenshots, brief context. Not a story. Works best on a repeatable cadence (weekly or monthly).
**Title pattern:** "[Project name] [period] update: [headline metric]"
- "lumenfall.ai April update: $4.2K MRR, 71% NSFW abuse rate, here's the dashboard"
- "Week 14 of building in public: shipped two features, churned two customers"

### 5. The technical curiosity / benchmark
**Where it works:** r/programming, r/MachineLearning, r/LocalLLaMA
**What it is:** pure technical content. No business framing. Numbers, methodology, results. The product shows up in passing or in a footer, if at all.
**Title pattern:** a descriptive technical title. No emojis, no clickbait.
- "Benchmarking 12 image-generation providers on cost, latency, and content-filter behavior"
- "What happens when you give 5,000 strangers a $1 OpenAI credit (a study in abuse patterns)"

Since May 2026 r/programming treats AI/LLM content as off-topic unless it's deeply technical implementation content, so an AI-related benchmark or postmortem usually belongs elsewhere; check its current AI policy (see `subreddits.md`).

## Title rules

The title does most of the work. If it's wrong, the body doesn't matter, because nobody clicks.

**Do:**
- Front-load the surprising specific (the weird number, the failure, the contradiction) in the first several words.
- Keep it under ~90 characters when you can. Reddit allows 300, but mobile feeds truncate long titles.
- Match the sub's title conventions. r/programming titles are descriptive and dry. r/SideProject titles can be more playful. r/buildinpublic titles often start with the project name.
- Write in the user's own register. Lowercase or casual titles work in some subs, but only if that's how the user writes; forced casualness reads as fake.

**Avoid:**
- Leading with "How [I/we] did X" unless the sub likes it (r/programming sort of does, r/SideProject is lukewarm).
- Clickbait ("You won't believe what happened when..."). Reddit downvotes it on sight.
- A question you immediately answer in the body. "Should you give free credits to AI users?" reads as engagement bait.
- Emojis, outside of certain hobby subs.
- Title Case. "How I Built My SaaS" reads SEO-ish; sentence case reads like a person.
- "We" when it's one person. Readers call it out. Ask the user if you don't know.

## Structural templates

These are skeletons. The lengths are budgets; shorter is usually better.

### Template A: hook-then-specifics (story-friendly subs)

Length: roughly 250-450 words.

```
[One-sentence hook: the weirdest specific in the whole story. Lead with it.]

[Setup, kept short (about three sentences). Who you are, what the project is,
why this happened. If the setup keeps growing, the hook is probably wrong.]

[The specifics. A few short paragraphs of what actually happened, with the
concrete details the user gave you: numbers, prompts, error messages,
screenshots. This is where the post earns its length.]

[What you changed or learned. One short paragraph with the actual change and
why. Skip it if the specifics already make it obvious.]

[Optional: one narrow question only this OP could ask, e.g. "anyone else on
Replicate seeing the same filter gaps?"]
```

### Template B: tactical breakdown (technical and founder subs)

Length: roughly 400-800 words. Numbers and structure, no fluff.

```
[One-sentence problem statement, concrete.]

[Context in a few sentences: stack, scale, time period, business context as
needed.]

[What you did, as plain prose or a clean numbered list (no bolded headers).
Use as many items as there really were, and let them be uneven: some need a
sentence, some need a paragraph with the reason and the result. For example:

1. Blocked disposable email domains at signup. Caught about a third of it.
2. Same-domain credit ladder. Took longer to explain to support than to build,
   but it closed the gmail-alias loophole that #1 couldn't touch.]

[Outcome: the measured result with the user's actual number, e.g. "abuse
rate dropped from 71% to 4% over 14 days."]

[Caveats: what this didn't fix and what you still don't know. Readers reward
honesty about limits.]

[Optional: link to a deeper writeup if the sub allows it.]
```

### Template C: metrics update (build-in-public subs)

Length: roughly 150-300 words. Mostly numbers and screenshots.

```
[Project name + period, e.g. "lumenfall.ai - April 2026 update"]

[Headline metric, one sentence.]

[Numbers: a handful of data points (MRR, users, churn, infra cost, feature
adoption), each with a short label.]

[What shipped this period: a few short bullets naming specific features, not
"product improvements."]

[What's next: a couple of specific bullets.]

[One open question or ask: "If anyone has seen [specific pattern], curious
what you did."]
```

## Participation prompts

Comments are where the useful intel comes from, and early comment activity seems to help a post's reach. A post that ends with a specific question usually gets more comments than one that ends with a summary. Put the prompt at the end of the body, or as a first comment from OP right after posting.

Prompts that tend to draw real answers:

- **"Have you seen this?"** "Anyone else seeing the same Telegram-coordinated abuse pattern? Curious what tripwires worked for you."
- **Inviting the contradiction.** "I'm pretty sure I'm wrong about [specific thing]. What would you have done differently here?"
- **Methodology.** "If you had a $1 free-tier budget and a small team, what would your stack look like?"
- **Shared pain.** "What's the dumbest abuse pattern you've had to fight in your free tier?"

What falls flat:

- Generic "thoughts?" or "let me know what you think." Low effort, reads as a marketer fishing for engagement.
- "Has anyone else done this?" with no specific anchor. Too broad to answer.
- Several questions in a row. People answer the one that catches their eye, so pick one.

## AI-shaped titles to avoid

These patterns read as content marketing on most major subs:

- "How [we] [verbed] [outcome]: [colon-separated framing]"
- "X lessons from [time period] of [activity]"
- "The [adjective] [noun] of [thing]"
- "Why [contrarian claim]" (overused; subs are tired of it)
- "[Number] things [audience] should know about [topic]"
- "Building in public: [generic update]"
- "From [starting point] to [ending point]" (the most blog-shaped title there is)

## Story-angle picker

Given one underlying story, which angle for which sub:

| Underlying story | Best angle | Best sub |
|---|---|---|
| New launch, decent metrics | Story (#1) or build log (#4) | r/SideProject (story) or r/buildinpublic (log) |
| Unexpected abuse, fraud, or weird users | Weird stat (#1) or I was wrong (#3) | r/SideProject, r/microsaas, r/indiehackers |
| A specific technical solution | Tactical breakdown (#2) | r/programming, r/devops, r/startups |
| Something measured across a category | Technical curiosity (#5) | r/programming, r/MachineLearning, r/LocalLLaMA |
| A strategy change that failed or worked | I was wrong (#3) | r/indiehackers, r/microsaas |
| A cost, billing, or infrastructure war | Tactical breakdown (#2) | r/devops, r/aws, r/programming |
| A funny screenshot or absurd customer interaction | Weird stat (#1), where the screenshot is the post | r/SideProject, r/ProgrammerHumor (if appropriate) |

If a story doesn't fit any of these, it probably isn't ready for Reddit. Reddit doesn't reward "we built a thing" without a hook. Find the hook, or write a different kind of post.

## Link post vs self-text

**Link post (URL, no body):**
- The destination is strong on its own (a blog post that reads well, a tool worth a click).
- The sub leans toward link posts (r/programming and r/MachineLearning often do).

**Self-text (the body is the content):**
- The user wants the discussion on Reddit, not on their blog.
- The story fits comfortably in 400-800 words.
- The sub leans toward self-posts (r/startups, r/SideProject, r/indiehackers, r/microsaas).

**Hybrid: short self-text plus a link to a deeper writeup:**
- The user has a genuinely strong long-form post.
- A ~200-word summary plus "full writeup at [link]" can work on r/programming and r/SideProject, rules permitting.
- If the summary reads like a teaser, readers will call it traffic-driving and downvote. Make the Reddit part useful on its own.

## Sample finished posts

These two are the target voice for the whole skill: specific, plain, a little rough because the facts are rough, no arc, no recap. Both use the user's real numbers; the shape transfers, the details don't.

### Sample 1: r/SideProject (story angle)

> 71% of free-tier video gens on my AI platform got flagged as porn in week 1
>
> Solo founder. Launched lumenfall a few weeks ago. Gave every new signup $1 in free credit because every other AI API gives you $5+ and I figured a buck was enough to play with image gen.
>
> First week: more video generations than I expected. Looked at the logs because the bill was higher than projected. 71% of video calls had hit a content filter somewhere in the pipeline.
>
> Looked at the prompts. Yeah. Specific anatomy. A lot of "[name from K-pop group]" prompts. One person had submitted variations of the same prompt 40+ times trying to find the path that didn't get blocked.
>
> Worse: my failover logic was retrying flagged prompts on a different provider, and that provider had looser filters. So sometimes the filter triggered and sometimes it didn't, depending on which provider got the retry. Effectively the system was shopping the request around until something generated.
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
> 4. Killed automatic provider failover for any prompt that triggered any filter at any layer. This was the fix that mattered most, because the failover was effectively shopping requests across providers until something generated.
>
> What didn't work: hCaptcha at signup. Determined abusers solved it. Phone verification works but converts at like 50% of legitimate users so it's a non-starter for free tier.
>
> Open questions: anyone else dealt with this in the same space? Specifically curious about the org behind the most-repeated prompts, they look organized.
