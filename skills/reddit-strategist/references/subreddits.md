# Subreddit guide for founders, indie hackers, and devs

An opinionated map of the subs that come up most when a founder asks "where should I post this?" It isn't exhaustive. The point is to keep users out of the small graveyards and pointed at the few subs where a real audience reads.

Categories are by what each sub rewards, not by topic. The same product can fit three categories with three different angles.

**Freshness note (last reviewed 2026-10):** sub culture and rules drift. Reddit no longer shows subscriber counts publicly (subs now show weekly visitors and contributions), so sizes below are relative, not numbers. For the 1-3 subs you actually recommend, check the live sidebar, rules, and pinned mod posts before the user submits, or ask the user to. The live rules win over anything in this file.

## Tier A: large, real audience, worth real effort

| Sub | Size | Rewards | Punishes | Tone |
|---|---|---|---|---|
| r/SideProject | very large | Genuine sharing of side projects, screenshots, real numbers, story-friendly | Pure ad copy, pretending it's not your project, "we" when it's just you | Casual, builder-friendly, pretty welcoming |
| r/programming | huge | Deep technical posts, postmortems, novel patterns, benchmarks | Career advice, listicles, content marketing, LLM-generated text, and most AI/LLM topics (see note below) | Sharp, expert, no-nonsense |
| r/MachineLearning | huge | Papers, novel results, real benchmarks, implementation details | Productized AI thinkpieces, prompt tricks, anything wrappery | Academic, dunks on AI hype |
| r/LocalLLaMA | very large | Hands-on results with open models, cost/latency comparisons, fine-tuning, hardware | Closed-API content, marketing, self-promo (its main moderation focus) | Technical, generous to good content |
| r/devops | large | War stories with details, postmortems, tooling comparisons | Vendor pitches, surface-level advice | Pragmatic, tooling-obsessed |

**How to think about Tier A:** each is selective in a different direction. r/SideProject is socially welcoming but expects a real builder, not a content marketer. The technical subs are strict about content but reward depth. One honest Tier A post with real specifics does more than fifty Tier C posts.

**r/programming and AI content:** in April 2026 r/programming ran a trial ban on LLM-related posts. In late May 2026 the mods replaced it with an AI policy (see the sub's `ai-policy` wiki page) that treats AI and LLM content as off-topic, except deeply technical implementation content. It also removes LLM-generated content. So an AI-product postmortem or an AI tool review will usually be removed there; check the current policy, and default to r/LocalLLaMA, r/devops, or r/webdev for the same material.

**r/LocalLLaMA** rewrote its rules around April 2026, with self-promotion as the main abuse area and more removals handled by AutoMod. Read Rule 4 (or whatever the self-promo rule is now) before posting anything that mentions your product.

## Tier B: medium audience, useful for specific angles

| Sub | Size | Rewards | Punishes | Tone |
|---|---|---|---|---|
| r/indiehackers | medium | Lessons-learned posts, revenue/metrics shares, journey content | Plain self-promo, vague advice posts | Founder-y, mostly supportive |
| r/microsaas | medium | Lean-business framing, profitability stories, niche product wins | Ad copy, vague "I built a SaaS" posts | Business-focused, less starry-eyed than indiehackers |
| r/buildinpublic | small to medium | Ongoing transparency: metrics updates, build logs, weekly recaps | One-shot story posts, narratives, "I'm new here" posts | Update-driven, expects regularity |
| r/scaleinpublic | small | Same as buildinpublic but later-stage metrics | Same | Same |
| r/startups | very large | Tactical breakdowns with numbers, lessons-learned with specifics | "We built a SaaS" posts, story posts without numbers, anything smelling of marketing | Strict moderation, low tolerance for story posts |
| r/SaaS | large | Tactical SaaS-specific content, vendor comparisons | Generic startup content, listicles | Mixed, often spammy |
| r/ExperiencedDevs | medium | Career-context posts, postmortems with realistic stakes | Junior-level content, anything performative | Senior-engineer voice |

**How to think about Tier B:** these have a shape preference. r/buildinpublic doesn't want a story; it wants a metrics update with screenshots. r/microsaas wants the business angle, not the technical one. r/startups, in our experience, punishes the "story of how we discovered X" format and rewards "here's the exact filter stack we built."

**r/startups specifics:** the sub uses an "I will not promote" convention. It has been required text in the post at times and more recently shows up as a flair or title disclaimer; promotion itself is confined to a recurring pinned thread (its name and cadence change; recently a Feedback-Friday-style thread). Flair is mandatory. Check the current sidebar and any AutoMod message before posting, because the exact requirement has changed more than once.

## Tier C: skip unless you have a niche-fit reason

These are mostly small, low-activity (check weekly visitors and contributions in the sub header), and dominated by founders posting at each other. Posting in them is rarely worth the time, and posting the same thing across many of them in a short window looks like spam.

- r/SaasDevelopers
- r/saasbuild
- r/AppIdeas (this is for getting ideas, not promoting)
- r/IMadeThis
- r/ProductHunters (PH-launch-prep specific)
- r/startups_promotion
- r/StartupSoloFounder
- r/ShowMeYourSaaS
- r/indie_startups
- r/startupaccelerator
- r/IndieAppCircle
- r/TechStartups (mostly news aggregation, low founder traffic)

There are exceptions. If a small sub has the exact audience for the product (say r/ChatGPTPromptGenius for a prompt tool), the small-sub rule reverses. The test is whether the sub has organic readers beyond founders posting at each other.

## Adjacent subs that are gold for the right angle

If the story has a technical, weird, or domain-specific angle:

| Sub | What fits | Examples |
|---|---|---|
| r/LocalLLaMA | Open-model results, cost/latency, fine-tuning lessons | "Benchmarked 12 image providers for cost/latency" |
| r/programming | Technical postmortems, novel patterns (check current AI-content rules first) | "Our automatic failover became an NSFW pipeline (postmortem)" |
| r/webdev | Frontend/backend war stories | Same content, different framing |
| r/aws / r/googlecloud / r/Azure | Cloud-specific war stories | Cost overruns, weird billing, infra postmortems |
| r/cscareerquestions | Career trajectory content (founders sometimes fit) | "Quit FAANG to start a $X ARR business, here's the math" |
| r/Entrepreneur | General business audience | Same content, less technical, more business |

Hacker News and Lobste.rs aren't Reddit; see `cross-platform.md` if the user wants to go there. Note that HN bans AI-generated or AI-edited text, which changes how much this skill can draft for it.

## Picking 1-3 subs for a single story

Most users come in asking "where should I post this story." The usual answer:

1. **Pick one Tier A sub for the strongest version of the angle,** the one where the story fits most naturally: a story for r/SideProject, a technical postmortem for r/programming, a model benchmark for r/LocalLLaMA. Post there first.
2. **Wait 48-72 hours** and watch the reception. It tells you whether to continue.
3. **If it landed, pick one Tier B sub** with a genuinely different framing of the same material. Not a repost with swapped nouns. A story post can become a tactical breakdown for r/startups, or a metrics update for r/buildinpublic.
4. **If it tanked or got hostile, don't repost it.** A story that got a hostile reception is mostly used up, because the old thread is searchable and some readers will remember it. Move on to a different story, or wait weeks and come back with a substantially different framing.

## Posting rhythm (rules of thumb, not Reddit mechanics)

- **Leave at least a day between posting the same story to two subs,** and preferably the 48-72 hours above. Same-day crossposting of near-identical promo is one of the clearer spam signals for filters and mods.
- **Avoid a third lookalike version in the same week.** Several near-identical posts in a short window is how accounts get filtered or reported.
- **Aim for roughly one substantive new post a week per account.** More than that and the account starts to look like a promo channel.
- **Comment on other people's posts in the sub before posting your own.** A few thoughtful comments give the account history in the sub, which mods and some AutoMod/reputation filters look at.
- **Rewrite per sub, don't swap the nouns.** Readers increasingly recognize the same post skeleton reused across subs. If a story got dunked on under one title, a near-identical title elsewhere a week later tends to get the same reaction from anyone who saw both.

## Subs that don't take project posts

These are large, attractive-looking subs where founders sometimes try to post. Promotional posts get removed, and repeat attempts put the account at risk. Treat them as read-only for this skill's purposes and steer the user elsewhere.

- **r/AskReddit**: Q&A only. Self-promotion of any kind is removed.
- **r/todayilearned**: citation-required factual posts. No personal projects.
- **r/pics, r/videos, r/gifs**: image/video content unrelated to your work.
- **News subs** (r/news, r/worldnews, r/technology when linking your own writing): allergic to promo.
- **r/Showerthoughts, r/explainlikeimfive, r/NoStupidQuestions**: discussion-only formats.

If something genuinely fits one of these as content (a truly novel technical screenshot in a niche image sub, say), the bar is much higher and the framing has to be entirely non-promotional, with no product link in the post or a top-level comment.

## Self-promotion: what the rules actually say

Reddit's sitewide rule is deliberately vague: participate authentically in communities you actually care about, follow each community's rules, and don't spam. There's no sitewide ratio.

The "9:1" or "90/10" rule (no more than one in ten of your posts or comments promotional) comes from Reddit's older self-promotion guidance, which Reddit no longer presents as a sitewide rule. Some subs still cite it or a variant in their own rules, and some mods use it as a yardstick. Treat it as a decent gut check, not a law. What matters in practice is the account's history in that sub and the sub's own rules.

Accounts that post nothing but their own work tend to get filtered by AutoMod or reputation filters, removed by mods, and in repeat cases suspended. The fix isn't to post less, it's to comment more: 10-15 minutes of genuine comments in the target sub before submitting is some of the best prep time available.

Removals can also come from automated tools now. Besides regex AutoMod rules, Reddit has been rolling out Rules Hub (announced August 2026), an LLM-based tool that mods can set to report or auto-remove posts that break a sub rule, so a post can be pulled for "self-promotion" or "low effort" without a human reading it. If a post vanished, look for an AutoMod or removal message first.

## When to skip Reddit entirely

Some content doesn't work on Reddit however well it's written:

- **Pure announcements.** "We launched X" with no story or specifics is dead on arrival outside r/SideProject, and marginal there. X, LinkedIn, or the user's own blog fit better.
- **Customer-testimonial posts.** "Here's how Acme uses our product" is content marketing and readers recognize it immediately.
- **Anything that needs a lot of product context to understand.** Reddit readers won't read the About page. If paragraph one has to be "let me explain what we do," the platform is wrong.
- **Screenshots that look like sales decks.** The post gets downvoted before anyone reads the words.
