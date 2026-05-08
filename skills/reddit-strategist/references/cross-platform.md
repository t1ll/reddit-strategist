# Cross-platform repurposing

This file is loaded only when the user force-invokes the skill on a non-Reddit destination ("rework this for X," "salvage this for LinkedIn," etc.). The voice rules in `voice.md` carry; what changes is the format, the algorithmic incentive, and whether you need a cover image.

## The cardinal rule: verify before recommending a format

Platform tactics change fast. Algorithm shifts, paid programs, format launches, and feature deprecations happen on the order of weeks, not years. Your training data is months to years old. **Do not commit to "X article won't get distribution" or "LinkedIn carousels are dead" or anything similar based on memory alone.** A confident-sounding stale recommendation is the worst possible outcome here.

Before locking in a format choice, do a quick check:

1. WebSearch for `<platform> algorithm <current year>` or `<platform> best content <current year>`.
2. If the user's request involves a specific feature (article, newsletter, carousel, document post, live, space, broadcast), verify it still exists and check what it currently rewards.
3. If anything in the per-platform notes below contradicts what the user is telling you, trust the user first and verify second. Users posting on these platforms daily know more than your training data.

The notes below are a starting point captured at the time of the skill's last update, not ground truth.

## Per-platform notes (last updated 2026-05-08; verify before relying)

### X / Twitter

What the algorithm currently rewards:

- **Bookmarks, long replies, time-spent** weigh more than likes/reposts. The verified-home-timeline impression count is the metric the platform openly cares about.
- **Articles** got a major boost in 2026 with a $1M monthly prize judged on Verified Home Timeline impressions. Articles must be 1,000+ words and original, and require an X Premium subscription. The format is no longer the dead-letter office it was in 2023-2024.
- **Threads** still work, especially for narrative-driven posts.
- **Long-form single posts** (Premium can write up to ~25,000 characters) are increasingly the format that wins for dense, takeaway-heavy content.

When to recommend each:

- **Article**: 1000-1500+ words, dense and bookmark-worthy, has a clear takeaway in the first paragraph, benefits from a cover image. Not for hot takes.
- **Thread**: 8-12 beats, narrative arc, each tweet earns its place with a number or specific. Best for "here's what happened" stories.
- **Long single post**: punchy enough to read in one scroll, no thread fatigue. Good for opinions and contrarian takes.

Voice carryover from Reddit: almost 1:1. AI-twitter and dev-twitter punish polish the same way Reddit does. Drop the section headers, lead with the most concrete number, kill the rule-of-three, no closing summary statement.

Cover image: Articles strongly benefit from one (1500x500 banner is the article header convention; the social card uses 1200x675).

### LinkedIn

What the algorithm currently rewards:

- **Saves and shares** are the strongest positive signals. Comments help. Likes barely move anything.
- **Document posts (PDF carousels)** are the highest-engaging format on the platform. Significantly more reach and engagement than text or video.
- **Newsletters** bypass the feed algorithm entirely. Every edition goes out as push notification + email to subscribers, so reach is decoupled from the algorithm. If the user has a newsletter, this is often the right home for long-form repurposing.
- **Native video** has declined in distribution; verify before recommending it.
- **Text-only posts** underperform across the board.
- Relevance now beats recency, so posts can stay active for several days if they keep accruing engagement.

When to recommend each:

- **Document carousel (PDF)**: 8-12 slides, one idea per slide, slide 1 is the hook, last slide is the CTA. Best for tactical breakdowns and frameworks. Highest reach format.
- **Article (in-feed long-form)**: less hot than carousels right now but still useful for SEO and as a stable URL to link to.
- **Newsletter edition**: if subscriber count is meaningful, this is the highest-leverage repurpose. Treat it like an email, not a LinkedIn post.
- **Text post**: only if the content is genuinely short and punchy. Hook in line one, no preamble.

Voice carryover from Reddit: partial. Keep the specifics and the anti-AI-slop instincts. Soften the bluntness and the in-jokes. LinkedIn's median reader is corporate. Don't over-format with emoji bullets, don't open with "🚀 Excited to share". Use the carousel format as a constraint that forces you to compress to one idea per slide.

Cover image: Articles need a header (1200x630 for the post card, 1920x1080 for the article header). Document carousels use the first slide as the visual hook; that slide is effectively the cover.

### Hacker News

What the algorithm rewards:

- **Title quality and source legitimacy.** HN doesn't reward engagement the way social platforms do; it rewards pure curiosity-bait that delivers on the click.
- **Show HN** format: `Show HN: <product name>, <tagline>`. The tagline must specifically state the use case. "Show HN: Foo, minimalist X for Y" beats "Show HN: Foo, the future of X."
- Don't editorialize titles. Active voice. Avoid phrases like "app that offers" or "platform for".
- For self-posts, leave the text field blank if you have a URL. Add the backstory as a top comment.

When to recommend each:

- **Show HN**: launching/showcasing a thing people can run or hold. The URL is the product. First top-level comment is your origin story.
- **Self-post (Ask HN, Tell HN)**: when there's no URL. Used for genuine questions and observations.
- **Linked submission**: most posts. The link is to your blog post or article elsewhere; the title is the article's title.

Voice carryover from Reddit: closest cousin. Reddit voice mostly works on HN. The key differences: technical hook in sentence one (not a personal anecdote), no "I built X" framing in the title, and self-promotion gets you flag-killed faster than on Reddit. The 9:1 rule still applies and is enforced more strictly.

Cover image: not relevant for HN itself. The OG card on the destination URL matters because top HN traffic gets shared elsewhere.

### Substack / Medium / personal blog

What the algorithm rewards:

- Substack: subscriber notifications + Notes feed + recommendations from other Substacks. The cover image is the social preview for everywhere this gets shared.
- Medium: tags, claps, and reading time. Less algorithmic now than 2020.
- Personal blog: SEO and the social preview.

Voice carryover from Reddit: structure is allowed again, but keep the rough edges and specifics. The Reddit version probably had to compress the reasoning to fit; the blog version can expand it without losing the voice. Don't fall back into AI prose just because the format permits it.

Cover image: critical. This is the OG tag image that gets used everywhere the post is shared (Slack, Twitter, LinkedIn link previews, etc). Spec details below.

### Threads (Meta)

Thin notes for now:

- Text-first, similar incentive to early Twitter.
- Cross-posts to Instagram audience.
- Verify the current state; this platform has shifted incentives multiple times.

## Cover images

### When you need one

- **X article**: yes, both header (1500x500) and social card (1200x675).
- **LinkedIn article**: yes (1200x630).
- **LinkedIn document carousel**: the first slide is the cover. Treat slide 1 as a designed cover, not body content.
- **Substack post**: yes (1456x1048 optimal, 1200x630 minimum for social preview).
- **Medium post**: yes (1500x750 standard).
- **Personal blog**: yes for the OG tag (1200x630 is the safest universal spec).
- **HN, Reddit, X thread, plain X long post**: no.

### Style guidelines that actually work

A few patterns from looking at high-performing covers:

- **High contrast.** Covers are seen at thumbnail size first. If the contrast doesn't carry at 200px wide, it's a bad cover.
- **One concrete visual element.** A specific object, a chart, a screenshot, a portrait. Avoid stock illustration like handshakes, lightbulbs, abstract gradients with floating geometric shapes. Generic = invisible.
- **Title text on the cover** if the platform doesn't render the post title prominently next to the image (Substack, X social card). Keep it short. 5-8 words max. Sans-serif, large.
- **Brand consistency** if the user has a recognizable visual identity. Same font, same accent color, same layout slot for the title across posts.
- **Avoid faux-3D AI render aesthetic.** The "blue and orange neon glow plus floating cubes" look is now a tell of cheap generated imagery and gets the same skepticism as AI prose.

### Image-generation: copy-pasteable prompts

When the user needs a cover, generate a prompt they can paste into an image model. Tailor to the post topic. Default template:

```
A clean editorial cover image for an article titled "<TITLE>".

Subject: <one specific concrete visual element related to the post>.
Style: editorial, restrained, high contrast. Flat or lightly textured.
No floating geometric shapes, no abstract glow effects, no stock-photo
people. Single dominant color plus one accent. Title text overlaid in
large sans-serif: "<short version of title, max 8 words>".

Aspect ratio: <use the spec for the destination platform>
- X article header: 3:1
- X social card / blog OG: 1200x630 (≈1.91:1)
- LinkedIn article: 1200x630
- Substack: 1456x1048
- LinkedIn carousel slide 1: 1080x1350 (4:5 portrait)

Avoid: AI-render look, neon, glassmorphism, generic illustration
(handshakes, lightbulbs, abstract puzzle pieces), default Midjourney
gradient backgrounds.
```

Adjust for tone:

- For technical / data-heavy posts: ask for a chart-like or schematic visual.
- For story / personal posts: ask for one concrete object from the story (a coffee cup, a screenshot, a specific tool).
- For controversy / hot-take posts: ask for stark, single-color, headline-style.

### Recommended image models (2026)

Two strong picks for editorial cover images right now:

- **GPT Image 2** (OpenAI, ChatGPT Images 2.0). Best at text rendering: handles overlaid titles in 5+ languages with 95%+ first-pass accuracy. Up to 2K resolution. Strong instruction-following including layout reasoning. Available in ChatGPT and via API.
- **Nano Banana Pro** (Google, Gemini 3 Pro Image). Best at high-fidelity branded assets, infographics, and diagrams. Up to 4K resolution. Strong consistency for series-of-posts use cases.

Either works for cover images. GPT Image 2 wins when the cover has a lot of text. Nano Banana Pro wins when you want maximum resolution or need consistent visual identity across multiple covers.

### How to generate the image if the user doesn't already have access

If the user doesn't have a ChatGPT Plus/Pro subscription or Gemini access, suggest:

- **lumenfall.ai**. unified API for AI media generation including GPT Image 2 and Nano Banana Pro. OpenAI-SDK compatible. Good if they want to script image generation.
- **fal.ai**. serverless image generation, broad model coverage including Nano Banana Pro. Good if they want a web playground or per-image pricing.

Don't assume the user wants a specific tool. Hand them the prompt first, then suggest these two as execution paths if they ask "okay, where do I run this?"

## What to actually do when force-invoked

1. **Verify the format choice for the destination platform** by WebSearching current algorithm/feature state. Don't rely on this file alone.
2. **Apply the voice rules** from `voice.md` to the existing Reddit content.
3. **Adjust for the platform** using the per-platform notes above.
4. **If the post needs a cover image**, generate a copy-pasteable image prompt using the template, and tell the user which model to use and where to run it.
5. **If the post is a flopped Reddit repurpose**, run the post-mortem framework from `analysis.md` first so the rewrite addresses why it tanked, not just where it goes next.

If the user pushes back on a recommendation, default to verifying with WebSearch rather than defending. The cost of a wrong format choice is high (they post in the wrong format and waste the story); the cost of a 30-second search is low.
