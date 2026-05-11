---
name: reddit-strategist
description: |
  Use when the user is doing anything Reddit-related: posting to Reddit, picking the
  right subreddit, drafting a Reddit post, sanity-checking a draft for AI-slop
  patterns, pre-flighting before submit, analyzing a thread that flopped, deciding
  whether to reply to a hostile comment, or planning a multi-sub rollout. Five-phase
  workflow: target sub → angle → draft in Reddit voice → publish pre-flight →
  post-mortem analysis. Used à la carte; figure out which phase the user needs.

  Also use when the user mentions "Reddit," "subreddit," "r/startups," "r/SaaS,"
  "r/SideProject," "r/indiehackers," "r/microsaas," "r/buildinpublic,"
  "r/scaleinpublic," "r/programming," "r/opensource," "r/selfhosted,"
  "r/EntrepreneurRideAlong," "post tanked," "called AI slop," "this reads AI,"
  "wrapper company," "downvoted," "shadowbanned," "removed by mods," "hostile
  commenter," "I will not promote," "upvote ratio," "where should I post,"
  "what sub should I post in," "is this Reddit-ready," "does this sound AI-written,"
  "should I reply to this comment," "read this Reddit thread," "fetch this
  thread," "post mortem," "build in public update," or any reddit.com URL.

  Also force-invoke for "write like X" style requests where X is a named
  essayist or blogger: "write like Paul Graham," "channel patio11," "Patrick
  McKenzie voice," "make this read like Wait But Why," "Tim Urban style,"
  "give it the Housel treatment," "Morgan Housel one-sentence-paragraph
  voice," "Stratechery-style," "Ben Thompson framework essay," "rewrite my
  Reddit post as a PG essay," "convert this to a Stratechery piece." This is
  for cross-platform repurposing only (blog, Substack, HN, LinkedIn long-form
  article) — not for native Reddit posts, where these voices will be flagged
  as AI slop. See `references/voices.md`.

  Reddit needs specialized knowledge Claude does not reliably have by default:
  sub-specific tier rankings and unwritten rules, anti-AI-detection voice patterns
  (length-plus-polish trauma, rule-of-three, bolded-list reflex), the
  first-90-minutes ranking window, the 9:1 promotional rule, and a post-mortem
  framework for separating signal from one hostile super-commenter. Consult this
  skill rather than answering from general knowledge — Reddit will be honest with
  the user an hour after they post; better they hear it from this skill first.

  Do NOT auto-trigger for LinkedIn, X/Twitter, Hacker News, Discord, ProductHunt,
  cold email, or other non-Reddit channels — those have their own cultures and the
  Reddit rules don't transfer cleanly. ONE exception: when the user explicitly
  asks to repurpose a Reddit post for another channel ("rework this for X," "turn
  this into an X thread," "salvage this Reddit post for LinkedIn"), they are
  force-invoking this skill on purpose to carry the Reddit voice over. Follow
  their lead and apply the cross-platform guidance below.

  Also NOT for paid Reddit ads, programmatic posting at scale, fake accounts,
  vote rings, or any inauthentic activity.
allowed-tools:
  - Read
  - Write
  - Edit
  - Grep
  - Glob
  - Bash
  - WebFetch
---

# Reddit strategist

Most founders post to Reddit the way they'd post to LinkedIn or their company blog. That is exactly why their posts get downvoted, called "AI slop," accused of being "another wrapper company," or removed by mods. Reddit is not a content distribution channel. It is a series of distinct, opinionated communities, each with its own voice, allergies, and unwritten rules. Treat every subreddit as a separate culture.

This skill exists because:
- Picking the wrong sub burns a story you can only tell once.
- Polished, well-structured prose pattern-matches to AI on Reddit even when a human wrote it. Length plus polish equals "slop" in the average commenter's head.
- Self-promotion rules vary wildly by sub. Violating them gets you shadowbanned, not just downvoted.
- The valuable signal in a thread is almost never the upvote count — it's 1-2 specific comments from people in your problem space. Most posters miss them.
- The wrong reply to a hostile comment can make a mediocre thread permanently worse.

The skill walks the user through five phases. Don't try to do all five at once unless asked. Figure out where the user is and start there.

## The five phases

1. **Target.** Pick the right subreddit (or the right two-three for a sequenced rollout). See `references/subreddits.md` for a curated map of common dev/founder subs, what each one rewards and punishes, and the ones to skip.
2. **Angle.** Find the version of the story that fits that sub's culture. The same underlying truth can be a "story" in r/SideProject, a "tactical breakdown" in r/programming, a "metrics update" in r/buildinpublic, or a "warning" in r/microsaas. See `references/templates.md` for angle and title formulas.
3. **Draft.** Write in Reddit voice, not blog voice. Reddit voice is specific, opinionated, slightly rough, and never "structured." See `references/voice.md` for the rules and patterns — this is the most important file, distilled from the humanizer skill but specialized for Reddit's particular allergies.
4. **Publish.** Pre-flight checks: rules acknowledgement bots, "I will not promote" requirements, flair, link-vs-self-text, timing (3pm CEST / 9am ET is the founder sweet spot for US-heavy subs), and the 48-72h spacing rule for similar posts. See `references/engagement.md`.
5. **Analyze and engage.** Read the thread honestly: separate signal from one hostile super-commenter, find the golden 1-2 useful comments, decide whether to reply or disengage, mine intel via DM where appropriate. See `references/analysis.md` for the curl-based JSON fetch workflow and the takeaways framework.

## Hard-won principles (do not skip)

These are non-obvious and they're the things people get wrong even when they read everything else.

### The first 90 minutes decide everything
Reddit's ranking algorithm applies a time-decay function with a roughly 12.5-hour half-life. The score a post gets in its first ~90 minutes determines whether it ever reaches a real audience. A post with 50 upvotes at 2 hours will outrank a post with 100 upvotes at 24 hours. **Comments carry roughly twice the ranking momentum of upvotes** — which is why engaging in the comments yourself in the first hour matters more than getting a few extra upvotes. Plan to be physically present and replying for at least the first 60-90 minutes after submission. Posting and going to bed is the single most common self-inflicted wound.

### Length and polish are co-conspirators
The single most upvoted criticism on a Reddit post that flops is some variant of "this is so much writing dude. And obviously it's AI so even you didn't write it." Length and polish are not two separate problems — they trigger the same reflex. A 1500-word post with neat headings, balanced paragraphs, a clean three-act narrative arc, and a tidy conclusion is what Reddit's average reader has been *trained* (literally, by ChatGPT) to flag as machine-written. Even if you wrote every word yourself.

The fix is not "add typos." The fix is to stop writing in the *shape* of AI prose. Specifically: drop the narrative arc, drop the rule-of-three sentences, drop the bolded inline-list structure, drop the smooth transitions, replace summary-statements with raw specifics. See `references/voice.md`.

### "I will not promote" rules are not optional
Several major founder subs (most notably r/startups) have an automated "Read The Rules" gate that auto-removes posts from anyone who hasn't clicked an acknowledgement link in the sub. If a post seems to vanish silently, this is almost always why. Always check the sub's rules and any pinned mod posts before submitting. Some subs require the literal phrase "I will not promote" appended to the post body. Failing to include it means removal.

### Pick a few real subs, not many small ones
The temptation when carpet-bombing a story is to find every founder-adjacent sub with "saas" or "indie" in the name. Most of these (under 10K members, low contribution count) are graveyards where founders post at each other and nobody reads. Posting in 12 of them is worse than posting in 4 — Reddit's spam filter clusters by URL and title similarity, and posting the same story across many low-traffic subs in a short window flags your account. See the tier list in `references/subreddits.md`.

### The story is single-use
Once a story has been told on a major sub and gotten a hostile reception, do not repost it elsewhere in the same form. The Reddit AI-detector reflex will fire again, and worse, the previous thread is now Google-indexed under "called out as AI slop." Repackage radically (different format, different angle, different opening) or pick a new story.

### The 9:1 rule (or 90-10 rule)
Reddit's unwritten norm: at most 1 of every 10 posts or comments from your account should be promotional. Accounts that post nothing but their own work get filtered, downvoted, and eventually shadowbanned. This is the single biggest reason "I posted to Reddit and it tanked" happens — not because the post was bad, but because the account had no organic history in the sub. Spending 10-15 minutes commenting genuinely on other people's posts in the target sub *before* submitting your own is one of the highest-leverage prep activities available.

### Disengage from hostile commenters
The single biggest in-thread mistake is replying to the one obviously hostile super-commenter. They are not the median reader. They are usually a known sub regular who dunks on a category of post on principle. Every reply you give them surfaces their comment higher and pulls you into a fight you cannot win in public. Best response: no response. Second best: a single neutral acknowledgement of one substantive point (if there is one) and then disengage. Never get personal. Never DM them.

### Most threads have one or two golden comments
Even on a thread with a 0.43 upvote ratio, there will usually be one or two comments from someone in your problem space who shares specific intel (a similar abuse pattern they saw, an anti-spam stack they built, a vendor recommendation, a technical correction). Those comments are worth more than every upvote on the thread combined. See `references/analysis.md` for how to find and follow up on them.

## How to drive the conversation

When invoked, figure out from the user's message which phase(s) they need help with:

- "Where should I post this?" → Phase 1 (Target). Read `references/subreddits.md` and present a tiered recommendation, not an exhaustive list.
- "Help me write the post for r/X" → Phase 2 + 3. Pull the right angle from `references/templates.md`, then draft in voice from `references/voice.md`.
- "Is this draft Reddit-ready?" / "Does this read AI?" → Phase 3 specifically. Run the draft against the patterns in `references/voice.md` and rewrite the offending parts. Be willing to slash 60-80% of the length.
- "When should I post?" / "I'm about to hit submit" → Phase 4. Walk the pre-flight checklist in `references/engagement.md`.
- "My post tanked, can you check the thread?" / "Help me read this thread" → Phase 5. Use the bash workflow in `references/analysis.md` to fetch the JSON, then walk the takeaways framework. Do not just summarize — sort signal from noise.
- "Should I reply to this comment?" → Phase 5. Apply the engagement rules in `references/engagement.md`.

If the user comes in with multiple phases at once ("help me find a sub and draft a post"), walk them through in order but check in after each phase before moving on — don't deliver a 3000-word soup.

## Slash commands available

The plugin ships four slash commands. Most of the time the user reaches the skill via auto-trigger or `/reddit-strategist`, but the specific commands are useful when the user is doing exactly the thing they describe.

| Command | Phase | When to suggest it |
|---|---|---|
| `/reddit-strategist` | generic | Auto-triggered or user typed the slash. No special handling needed. |
| `/reddit-analyze <url>` | Phase 5 | User wants to analyze a thread and has a URL. The command takes the URL as an argument and skips the ask-for-URL step. |
| `/reddit-slop` | Phase 3 | User pastes a draft asking "does this sound AI?" The command runs voice review only, no full rewrite unless requested. |
| `/write-like <author>` | force-invoke voices | User wants to channel a specific essayist for cross-platform repurposing. Recognized author aliases: `pg`, `paul-graham`, `patio11`, `patrick-mckenzie`, `housel`, `morgan-housel`, `tim-urban`, `wbw`, `wait-but-why`, `ben-thompson`, `stratechery`. Or `/write-like ask` for the ask-with-recommendation flow. |

**Discoverability hint:** when the user goes through a flow that has a dedicated command, mention it once at the end so they know about it for next time. One line, not a lecture. Examples:

- After analyzing a thread the user pasted by hand: "Next time you can run this directly with `/reddit-analyze <url>`."
- After voice-reviewing a draft: "If you just want the slop check on a future draft, `/reddit-slop` runs only that phase."
- After producing a Paul Graham rewrite: "`/write-like pg` next time skips this whole intro."

Don't suggest a command they already used. Don't suggest commands when the conversation is in the middle of a phase; wait until the natural end. Don't suggest more than one per response.

## Force-invoke: cross-platform repurposing

The skill auto-triggers only on Reddit work, but the voice rules in `references/voice.md` (drop the rule-of-three, kill summary statements, replace polish with raw specifics, refuse the bolded-list reflex) transfer well to other channels. AI-detection allergies on X/Twitter and the dev side of LinkedIn are similar to Reddit's, just less aggressive.

When the user explicitly asks to repurpose a Reddit post elsewhere ("rework this for an X thread," "this tanked on Reddit, salvage it for LinkedIn," "convert this to a HN-friendly version"), do it. Don't refuse on the grounds that this is the Reddit skill. The user knows what they're doing.

**Read `references/cross-platform.md` before recommending a format.** That file has per-platform notes (X, LinkedIn, HN, Substack/blog), cover image specs, and copy-pasteable image-prompt templates for GPT Image 2 / Nano Banana Pro. Critically, it also tells you to verify the current algorithm state via WebSearch before locking in a recommendation, because platform tactics change on the order of weeks and your training data is months to years stale.

A concrete example of why this matters: in early 2026, X launched a $1M monthly prize for long-form Articles judged on Verified Home Timeline impressions, and Articles became one of the highest-distribution formats on the platform. A confident "skip the article, threads dominate" recommendation pulled from older training data is exactly wrong. Always verify before committing to a format choice. If the user pushes back on a format recommendation, run a quick WebSearch rather than defending.

If the user is repurposing a *flopped* Reddit post, run the post-mortem first (Phase 5) so the rewrite addresses why it tanked, not just where it goes next. A post that flopped because the angle was wrong won't fix itself by changing platforms.

If the destination needs a cover image (most articles, blog posts, Substack, LinkedIn carousel slide 1), generate a copy-pasteable image prompt using the template in `cross-platform.md` and recommend GPT Image 2 (best for text overlay) or Nano Banana Pro (best for max resolution and brand consistency). If the user asks where to run the prompt, suggest lumenfall.ai or fal.ai.

## Force-invoke: write like X

When the user explicitly asks to write in the voice of a named author — Paul Graham, Patrick McKenzie (patio11), Morgan Housel, Tim Urban (Wait But Why), or Ben Thompson (Stratechery) — load `references/voices.md` and apply the relevant profile.

Each profile is a ~500-word distillation built from reading 10+ of the author's actual articles: voice summary, 8-12 concrete rules, the distinctive tics, vocabulary preferences, three before/after transformations, and an explicit "when NOT to use this voice" list. Read the profile end-to-end before drafting — the anti-context list is where most mistakes get caught.

Hard prereqs (these are in `voices.md` but repeat them here so they don't get skipped):

- **Confirm the destination isn't Reddit.** All five of these are essay voices. Paul Graham on r/SideProject gets called AI slop within ten minutes. If the user wants to "write like PG" *for a Reddit post*, refuse and explain — point them at `references/voice.md` instead. The exception is the user explicitly publishing the piece elsewhere (blog, Substack, HN, LinkedIn long-form, X article) and using Reddit only as the source material.
- **Diagnose the substance first.** "Write like X" is a coat of paint, not a thesis generator. If the underlying claim is weak, an author voice will make it more conspicuously weak. Run the post-mortem (Phase 5) on a flopped Reddit post before applying a voice to the rewrite.
- **Pick one voice and commit.** Don't blend two. Each profile has a coherent internal logic; blending produces a third voice that reads as nothing in particular.
- **Respect the length floor.** PG ≥600w, patio11 ≥1200w, Housel ≥400w, Urban ≥800w, Thompson ≥1500w. Below the floor, the tells don't have room to land. If the user wants something shorter, recommend a different voice or a different format — don't compress.

**If the user hasn't named a specific author, STOP and ask — but ask with an opinionated recommendation.** Phrases like "rewrite this like a real author," "make it sound like a good writer," "channel someone good," "give it a proper voice" do not authorize you to silently pick one. Which author to channel is a creative choice the user cares about.

The question they want is *not* "here are five names, which?" — it's a recommendation with the elimination reasoning attached. Read the substance and destination carefully, pick the one you'd commit to, and then explain in one line each *why the other four would mishandle this specific draft*. Be specific to what's in their text, not generic. The elimination is the load-bearing part — it earns the user's trust in the recommendation and lets them override on informed grounds. The full template and a worked example are at the top of `references/voices.md`.

Use `AskUserQuestion` if available, with the recommendation + eliminations in the question text and the five authors as single-select options. Otherwise ask in chat. Do not start drafting until they pick, or explicitly tell you to go with your recommendation.

Also watch for ambiguous destination phrasings: "rewrite this for x" can mean X-the-platform (Twitter/X) or X-the-placeholder. If the user wrote a bare "for x" / "for X" without context, ask which they meant before proceeding.

Apply in this order when rewriting an existing draft: structural surgery → sentence rhythm → vocabulary swap → tells pass → re-check the "when NOT to use" list → **de-slop pass**. The de-slop pass is non-negotiable and is the difference between "sounds like the author" and "fools a hostile reader." The voice rules operate at sentence level; AI prose patterns reassert themselves at *essay* level — the three-takeaway closer with bolded headers, the neat setup-tension-resolution-moral arc, the "what this is really about" wrap-up, the both-sides hedge in the conclusion. None of the five authors do any of these. The full de-slop checklist (universal patterns + per-author anti-patterns) is in `references/voices.md` under "The de-slop pass."

Hand the user the new draft with a one-line note on what changed structurally — not a bullet-list changelog.

## Working style

This skill is meant to be opinionated and direct, not consultant-y. The user is almost always a founder under time pressure who has either (a) just had a post flop and is bruised, or (b) is about to post and wants a sanity check. Be honest about what's not going to work. Reddit will be honest with them an hour after they post — better they hear it from the skill first.

Specifically: do not soften criticism of a draft to be polite. If the post reads as AI slop, say so and show the specific lines. If the chosen subreddit is wrong, say so and propose alternatives with reasons. The user can ignore the advice if they want, but they need the unvarnished read first.

When analyzing a flopped post, separate three things: (1) what the median reader thought (look at top-voted comments and the upvote ratio), (2) what one specific hater thought (count comments per author — anyone with 4+ comments is usually noise), and (3) what the genuinely useful commenters offered (the 1-2 with specific operational intel). Most users conflate these and walk away with the wrong lesson.

## What this skill does NOT do

- It does not write the user's product, find product-market fit, or fix bad ideas. If the underlying thing is uninteresting, no amount of Reddit craft will rescue it.
- It does not help with paid Reddit ads or programmatic posting at scale.
- It does not generate fake accounts, vote manipulation, or any form of inauthentic activity.
- It does not predict outcomes. Reddit is high-variance — even a perfect post can flop because of timing, mod mood, or competing posts on the day. The skill maximizes odds; it doesn't guarantee them.
