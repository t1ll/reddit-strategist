# Post-mortem analysis

How to read a Reddit thread honestly, separate signal from noise, and extract the parts that are actually worth acting on. Most founders who post on Reddit either declare victory based on upvote count or declare failure based on the loudest hostile commenter — both readings miss what the thread actually has to offer.

## Step 1: Fetch the thread as JSON

Reddit's old web frontends (old.reddit.com, www.reddit.com) often block automated fetches. The Reddit JSON endpoint, however, works with a generic User-Agent and is the most reliable way to get the data.

For any Reddit post URL of the form `https://www.reddit.com/r/SUB/comments/POST_ID/SLUG/`, append `.json` to get the full thread including comments:

```bash
curl -s -A "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36" \
  -H "Accept: application/json" \
  "https://www.reddit.com/r/SUB/comments/POST_ID.json?limit=200&raw_json=1" \
  -o /tmp/reddit_thread.json
```

Notes:
- The User-Agent matters. A blank or curl-default UA gets blocked.
- The `?limit=200` param raises the comment cap from the default 100.
- `raw_json=1` returns unescaped strings (cleaner for processing).
- The JSON is a 2-element array. Element 0 is the post, element 1 is the comment forest.

## Step 2: Parse the thread

This Python snippet is the workhorse — print the post metadata and walk the comment tree with scores and authors:

```python
import json
with open('/tmp/reddit_thread.json') as f:
    data = json.load(f)

post = data[0]['data']['children'][0]['data']
print('TITLE:', post.get('title'))
print('REMOVED_BY:', post.get('removed_by_category'))
print('SCORE:', post.get('score'),
      '| COMMENTS:', post.get('num_comments'),
      '| RATIO:', post.get('upvote_ratio'))
print()
print('SELFTEXT:')
print(post.get('selftext','')[:1000])
print()
print('=== COMMENTS ===')

def walk(c, depth=0):
    for child in c:
        d = child.get('data', {})
        if child.get('kind') == 'more':
            continue
        body = d.get('body', '')
        author = d.get('author', '?')
        score = d.get('score', 0)
        prefix = '  ' * depth
        print(f'{prefix}[{score}] {author}:')
        for line in body.split('\n'):
            print(f'{prefix}    {line}')
        print()
        replies = d.get('replies')
        if replies and isinstance(replies, dict):
            walk(replies['data']['children'], depth+1)

walk(data[1]['data']['children'])
```

For threads with more than ~200 comments (rare for founder posts, but possible if something goes viral), you'll need to follow the `more` children which contain pagination tokens. For most post-mortems this isn't necessary.

## Step 3: Read the metadata first

Before reading any comments, look at the metadata. The big four numbers tell you most of what you need to know about the *median* response.

| Metadata field | What it tells you |
|---|---|
| `score` | Net upvotes minus downvotes (Reddit fuzzes this, but the relative magnitude is real) |
| `upvote_ratio` | The fraction of votes that were upvotes. **The single most honest number.** |
| `num_comments` | Engagement volume |
| `removed_by_category` | If non-null: `moderator` (a human mod removed it), `automod_filtered` (an auto-mod did), `deleted` (you deleted it), `reddit` (sitewide action). If null: alive. |

How to interpret combinations:

- **High score, ratio > 0.85, many comments:** Real win. Treat the discussion as a goldmine and don't fight any criticism — readers liked it.
- **Low score, ratio < 0.5, many comments:** Controversial or hostile. People engaged but mostly downvoted. The post hit a nerve, possibly the wrong one. **Read the top comments to figure out which.**
- **Low score, ratio ~0.5, few comments:** Dud. Not enough signal to draw conclusions. Probably wrong sub or wrong time.
- **Score 1, comments 1, ratio 1.0:** Almost always a bot-removed post that no humans saw. Check `removed_by_category` and the sole comment — usually it's an auto-mod telling you to acknowledge the rules.
- **High score, ratio ~0.6, many comments:** Polarizing. Some people loved it, others hated it. Read for the camps.
- **`removed_by_category: moderator`:** A human mod pulled it. Check the top comment for a removal reason. Sometimes recoverable by editing and re-posting; sometimes not.

## Step 4: Sort the comments into three piles

This is the most important step and the one founders skip. Most people read comments top-to-bottom and conflate three very different things.

**Pile A: median reader signal.** The top 3-5 comments by score, weighted by upvotes. These represent how the typical reader felt. If the top comment is "this is so much writing dude. And obviously it's AI," that is the median reader's view, not a hot take. Take it seriously.

**Pile B: the hostile super-commenter.** Count comments per author. Anyone with 4+ comments in a thread is almost always a known sub regular who dunks on a category. Their *position* may be valid, but they are not signal about the median reader's view. They will be louder than the median by an order of magnitude. Common signs:
- Multiple comments under different parent threads
- Increasingly personal as the thread continues
- Engages with other commenters who disagree, picking subsidiary fights
- Tends to use specific dunk phrases ("wrapper company," "another saas guy," "ai slop")

Score this pile separately. If you remove their comments mentally, what does the rest of the thread look like? That's a more honest picture.

**Pile C: the golden comments.** The 1-2 comments from someone with specific operational intel. They're usually:
- Not at the top
- Often score 1-3 (not viral, just real)
- Specific in a way that only someone in your problem space would be
- Sometimes in reply to other comments rather than top-level

Examples of golden comments:
- "We saw the same thing — turned out it was the same Telegram group running the same prompts. They're organized, you'll see them again."
- "Try blocking [specific email pattern] at signup, that caught 80% of the same abuse for us"
- "This is a known issue with [specific provider]'s NSFW filter, they've been flaky since [date]"

These are the highest-value output of any Reddit post, often more valuable than 100 upvotes. They're easy to miss because they're not bolded by the algorithm.

## Step 5: Pattern-match the criticism

When a post gets dragged, the criticism almost always falls into one of these buckets. Identifying which one tells you what to fix for next time:

| Complaint pattern | Real underlying issue | How to fix next time |
|---|---|---|
| "Too long" / "TL;DR??" / "wall of text" | Length-plus-polish triggered AI detector OR you didn't earn the length with specifics | Cut by 50%. Front-load specifics. Add TL;DR at top. |
| "Sounds like AI" / "ChatGPT wrote this" / "AI slop" | Smooth prose shape, rule-of-three, bolded headers, smooth transitions | Apply `voice.md` rigorously. Throw the draft out and rewrite shorter. |
| "Just a wrapper" / "you didn't build anything" | r/startups-style anti-AI-infra reflex (hard to fully fix) | Frame around technical depth or specific business mechanics, not the wrapper itself |
| "Where are the numbers?" / "this isn't actionable" | Story without specifics; readers wanted tactical takeaway | Pivot to tactical breakdown angle (`templates.md` template B) |
| "This is just promotion" / "you're shilling" | Even-handed mention came across as pitch OR you violated "I will not promote" rule | Strip ALL product mentions next time, or move them to a single line at the bottom |
| "This isn't relevant to this sub" | Wrong sub | Re-read `subreddits.md` for next attempt |
| "This is the dumbest take I've ever read" / personal attacks | Hostile super-commenter (Pile B), not signal | Disregard, do not engage |

## Step 6: Map the takeaways

Write down four things from the thread (literally — to a notes file or directly into the response):

1. **What the median reader thought.** Top 3 comments by score, paraphrased honestly.
2. **What's noise vs. signal.** Identify the hostile super-commenter if any, and discount.
3. **Golden comments.** What specific operational intel did you get? Who shared it (username, comment id)?
4. **What to change.** One or two concrete adjustments for the next post (different sub, different angle, different length, different opening).

If the takeaway list has more than 5 items, you're overfitting to noise. Pick the top 3.

## Step 7: Follow up on golden comments

For each golden comment from Pile C:

- **Reply publicly** with one short thank-you and ideally a question that invites them to share more. "Wait, can you say more about how you spotted the Telegram pattern? Was there a specific signal that gave them away?"
- **Send a DM** if the public reply gets a substantive response. Frame as: "Your comment was the most useful thing I got out of this thread. If you have 10 minutes for a quick chat about [specific topic], I'd love to compare notes."
- Do NOT pitch them, do NOT ask them to try your product. The point is the relationship and the intel.

This step is the actual ROI of most Reddit posts. The upvotes are a side effect. The 1-2 useful contacts you make per thread are the durable thing.

## Step 8: Decide whether to keep engaging in the thread

After the first 4-6 hours, the post has mostly settled. Decide:

- **If reception was positive:** Reply to top 3-5 comments substantively. Add an "Edit:" to the post if a comment surfaced a useful clarification. Don't reply to every comment — looks needy.
- **If reception was hostile:** Reply to nothing. Do NOT post follow-up explanations. Do NOT defend the post. The thread will sink to the bottom on its own. Every reply you add to a hostile thread bumps it back up.
- **If reception was mixed:** Reply only to substantive comments. Reply to ONE measured acknowledgement of the most valid criticism. Disengage from haters entirely.

See `engagement.md` for specific reply patterns.

## Common analysis mistakes

- **"My post got 50 comments, it must have done well."** Comments are engagement, not approval. A 0.4 upvote ratio with 50 comments is a roast.
- **"Everyone hated it."** No, one or two loud people hated it. Re-read with the hostile super-commenter discounted.
- **"I should have made it longer to address all the criticism."** Almost never the right call. Length-criticism + AI-criticism are a single problem; the answer is shorter, not longer.
- **"I should reply to clarify."** Replying to clarify a hostile comment surfaces both their comment and yours, which makes the thread look more hostile to later viewers. Just don't.
- **"The mods removed it because they're against me."** Almost always: rules-acknowledgement bot, "I will not promote" missing, or some other automatable rule. Read the mod removal reason, fix it, move on.

## Storing analysis

When the user asks you to analyze a flopped post, save the takeaway list as a memory if the user might post again with similar material. Specifically:

- Save what hooked the median reader (positive lessons)
- Save what triggered the AI-slop reflex (negative lessons)
- Save the username + handle of any golden-comment contact you DM'd, so future posts can reference the relationship
- Don't save the post text itself — that gets stale

The point is not to memorize this thread. The point is to make next thread better.
