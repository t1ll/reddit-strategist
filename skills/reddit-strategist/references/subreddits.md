# Subreddit guide for founders, indie hackers, and devs

This is a curated, opinionated map of the subs that come up most often when a founder asks "where should I post this?" It is not exhaustive — it is designed to keep you out of the small graveyards and pointed at the few subs where a real audience actually reads.

The categories are by what each sub *rewards*, not by topic. The same product can fit in three different categories with three different angles.

## Tier A: large, real audience, worth real effort

| Sub | Members | Rewards | Punishes | Tone |
|---|---|---|---|---|
| r/SideProject | 300K+ | Genuine sharing of side projects, screenshots, real numbers, story-friendly | Pure ad copy, pretending it's not your project, "we" when it's just you | Casual, builder-friendly, pretty welcoming |
| r/programming | huge | Deep technical posts, postmortems, novel patterns, benchmarks | Career advice, listicles, anything that smells of "content marketing" | Sharp, expert, no-nonsense |
| r/MachineLearning | huge | Papers, novel results, real benchmarks, model implementation details | Productized AI thinkpieces, ChatGPT prompt tricks, anything wrappery | Academic, dunks on AI hype |
| r/LocalLLaMA | very large | Hands-on results with open models, cost/latency comparisons, fine-tuning, hardware | Closed-API content, marketing | Technical, generous to good content |
| r/devops | large | War stories with details, postmortems, tooling comparisons | Vendor pitches, surface-level advice | Pragmatic, tooling-obsessed |

**How to think about Tier A:** Each is selective in a different direction. r/SideProject is socially welcoming but expects you to be a real builder, not a content marketer. The technical subs are content-strict but reward depth. If you have an honest story or specific technical detail to share, one Tier A post does more than fifty Tier C posts.

## Tier B: medium audience, useful for specific angles

| Sub | Members | Rewards | Punishes | Tone |
|---|---|---|---|---|
| r/indiehackers | 20K+ | Lessons-learned posts, revenue/metrics shares, journey content | Plain self-promo, vague advice posts | Founder-y, mostly supportive |
| r/microsaas | 40K+ | Lean-business framing, profitability stories, niche product wins | Ad copy, vague "I built a SaaS" posts | Business-focused, less starry-eyed than indiehackers |
| r/buildinpublic | 60K+ | Ongoing transparency: metrics updates, build logs, weekly recaps | One-shot story posts, narratives, "I'm new here" posts | Update-driven, expects regularity |
| r/scaleinpublic | small | Same as buildinpublic but later-stage metrics | Same | Same |
| r/startups | very large | Tactical breakdowns with numbers, lessons-learned with specifics | "We built a SaaS" posts, story posts without numbers, anything smelling of marketing | Has gotten meaningfully more hostile to story posts in 2024-2026 |
| r/SaaS | large | Tactical SaaS-specific content, vendor comparisons | Generic startup content, listicles | Mixed, often spammy |
| r/ExperiencedDevs | medium | Career-context posts, postmortems with realistic stakes | Junior-level content, anything performative | Senior-engineer voice |

**How to think about Tier B:** These have a *shape* preference. r/buildinpublic doesn't want a story — it wants a metrics update with screenshots. r/microsaas wants the business angle, not the technical angle. r/startups in 2024-2026 specifically punishes the "story of how we discovered X" format and rewards "here's the exact filter stack we built."

**Critical rule for r/startups specifically:** the literal phrase "I will not promote" is required at the bottom of the post body. There is also a "Read The Rules" gate bot — you have to click an acknowledgement link in the sub's interface before your first post, or it auto-removes silently.

## Tier C: skip unless you have a niche-fit reason

These are mostly small (under 10K), low-engagement, and dominated by founders posting at each other. Posting in them is rarely worth the time and risks Reddit's spam filter clustering your posts.

- r/SaasDevelopers
- r/saasbuild
- r/AppIdeas (this is for *getting* ideas, not promoting)
- r/IMadeThis
- r/ProductHunters (PH-launch-prep specific)
- r/startups_promotion
- r/StartupSoloFounder
- r/ShowMeYourSaaS
- r/indie_startups
- r/startupaccelerator
- r/IndieAppCircle
- r/TechStartups (mostly news aggregation, low founder traffic)

There are exceptions — if you happen to know a specific small sub has the exact audience for your product (e.g., r/ChatGPTPromptGenius for a prompt tool), the small-sub rule reverses. The criterion is *does this sub have an organic readership beyond founders posting at each other.*

## Adjacent subs that are gold for the right angle

If your story has a technical, weird, or domain-specific angle:

| Sub | What fits | Examples |
|---|---|---|
| r/LocalLLaMA | Open-model results, cost/latency, fine-tuning lessons | "Benchmarked 12 image providers for cost/latency" |
| r/programming | Technical postmortems, novel patterns | "Our automatic failover became an NSFW pipeline (postmortem)" |
| r/webdev | Frontend/backend war stories | Same content, different framing |
| r/aws / r/googlecloud / r/Azure | Cloud-specific war stories | Cost overruns, weird billing, infra postmortems |
| r/cscareerquestions | Career trajectory content (founders sometimes fit) | "Quit FAANG to start a $X ARR business — here's the math" |
| r/Entrepreneur | General business audience | Same content, less technical, more business |
| r/Frugal_Jerk-ish niches | Sometimes wildly receptive to the right framing | (research before posting) |

**Hacker News (not Reddit):** Different beast. HN rewards link posts to original content (your blog, your repo) with a tight, descriptive title. Don't paste the post into the HN box. The title does most of the work. The peak window is 8-9am ET on weekdays. HN audience is more skeptical of consumer-AI content and more receptive to genuine technical depth.

**Lobste.rs (not Reddit):** Smaller, technical, invite-only. If you have an invite, treat it like a sharper HN. Same rules.

## Picking 1-3 subs for a single story

Most users come in asking "where should I post this story." The honest answer is usually:

1. **Pick one Tier A sub for the strongest version of the angle.** The one where the story most naturally fits — story for r/SideProject, technical postmortem for r/programming, model benchmark for r/LocalLLaMA. Post there first.
2. **Wait 48-72 hours.** Watch what happens. The reception will tell you whether to continue.
3. **If it landed, pick one Tier B sub** with a *different* framing of the same underlying material. Not a repost — a genuinely different angle. A story-shaped post can become a tactical breakdown for r/startups, or a metrics-update for r/buildinpublic.
4. **If it tanked or got hostile, do not repost.** The story is single-use once it's gotten a hostile reception. Move on to a different story (or wait weeks before reusing the same one with significantly different framing).

## Posting rhythm rules

- **Never post the same story to two subs within 24 hours.** Reddit's spam filter clusters by URL and title.
- **Never post a third version within a week.** Three lookalike posts = shadowban risk.
- **A single user account should post a substantive new post no more than ~once a week.** Beyond that, your karma and the subs' algorithms start working against you.
- **Comment on other people's posts in the sub before posting your own.** A few thoughtful comments give your account history in the sub and reduce the chance of an auto-removal. Mods look at this.
- **Title and post body that match a previously hostile thread will get matched** by some sub-specific bots. If you got dunked on for a story under one title, a near-identical title to a different sub a week later will get the same downvote pile-on if the same readers see both.

## Subs that are explicitly anti-promotion (do NOT post your project here)

These are large, attractive-looking subs where founders sometimes try to post — and where *any* promotional post will be removed and the account often shadowbanned. The rules in these subs are not negotiable. Treat them as read-only for this skill.

- **r/AskReddit** — Q&A only. Self-promotion of any kind = instant removal.
- **r/todayilearned** — Citation-required factual posts. No personal projects.
- **r/pics, r/videos, r/gifs** — Image/video content unrelated to your work.
- **News subs** (r/news, r/worldnews, r/technology when posting links to your own writing): allergic to promo.
- **r/Showerthoughts, r/explainlikeimfive, r/NoStupidQuestions** — discussion-only formats.

If your project genuinely fits one of these as content (e.g., a *truly novel* technical screenshot might fit a niche image sub), the bar is much higher and the framing must be 100% non-promotional, with no link to your product anywhere in the post or first-level comment.

## The 9:1 / 90-10 self-promotion rule

Reddit's unwritten norm — and explicitly written into many subs' rules — is that no more than 1 in 10 of your posts/comments should be self-promotional. Accounts that post nothing but their own work get filtered, downvoted, and eventually shadowbanned. The fix is not "post less" — it is "comment more." Spend 10-15 minutes commenting genuinely on other people's posts in the target sub before submitting your own. This is one of the highest-leverage 15 minutes available.

## When to skip Reddit entirely

Some content does not work on Reddit no matter how well-crafted:

- **Pure announcements.** "We launched X" with no story or specifics is dead on arrival outside of r/SideProject (and even there it's marginal). Use X/LinkedIn/your own blog instead.
- **Customer testimonial-shaped posts.** "Here's how Acme uses our product" is content marketing and Reddit smells it instantly.
- **Anything that requires extensive product context to understand.** Reddit users won't read your About page. If the post requires "let me explain what we do first" as paragraph one, the platform is wrong.
- **Anything with screenshots that look like sales decks.** The post will get downvoted before anyone reads the words.
