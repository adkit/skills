# Meta Advertising Fundamentals

## Contents

- [Agent Decision Tree](#agent-decision-tree)
- [Interruption vs Search Advertising](#interruption-vs-search-advertising)
- [Total Addressable Market](#total-addressable-market)
- [How Meta's Auction Works](#how-metas-auction-works)
- [Meta's Algorithm Priorities](#metas-algorithm-priorities)
- [Meta's Targeting Intelligence](#metas-targeting-intelligence)
- [Audience Awareness Levels](#audience-awareness-levels)
- [Ad Fatigue](#ad-fatigue)

Help the user understand Meta advertising before they start creating ads. If the user asks whether Meta is right for them, use the comparison below to guide them. If they're already committed to Meta, skip straight to what matters: creative quality and how the auction works.

## Agent Decision Tree

- **"Should I use Facebook or Google ads?"** - Ask: _What's your product? Is your audience actively searching for it, or do they not know it exists yet?_ Then use the interruption vs search comparison below.
- **"Is Meta worth it for my budget?"** - Reframe: budget matters less than creative quality on Meta. A \$1000/month account with great ads beats a \$2,000/month account with mediocre ones.
- **"I have a novel product with no search volume"** - Meta is the stronger choice. Google captures existing demand; Meta creates new demand. Emphasize the TAM section.
- **"I already run Google Ads, should I add Meta?"** - Yes, if budget allows. Google captures people searching; Meta reaches the far larger pool who would buy but aren't looking.

**Key point to communicate to the user: creative quality is the #1 lever on Meta, not budget.** Return to this throughout the conversation. Most users overestimate the importance of targeting and budget, and underestimate creative.

---

## Interruption vs Search Advertising

Meta ads are **interruption marketing**: ads appear between content users chose to consume. This distinction drives every strategic decision.

|                     | Interruption (Meta, TikTok, TV)           | Search (Google, Bing, Amazon)                   |
| ------------------- | ----------------------------------------- | ----------------------------------------------- |
| **When ads show**   | Between content the user is consuming     | When the user searches a keyword                |
| **Audience intent** | Low: user wasn't looking for you          | High: user is actively seeking a solution       |
| **Conversion rate** | Lower (cold traffic)                      | Higher (warm/hot traffic)                       |
| **Reach**           | Massive: limited only by platform users   | Capped by search volume for your keywords       |
| **Cost**            | Generally cheaper CPMs                    | More expensive (small pool of qualified buyers) |
| **Core challenge**  | Create an impulse to stop scrolling       | Be present at the right moment                  |
| **Creative burden** | High: you must produce compelling content | Lower: copywriting and bid strategy matter more |

### When to use Meta vs Google

- **Use Meta** when your total addressable market is larger than the people actively searching for your solution. This is most products: especially novel ones where buyers don't yet know a solution exists.
- **Use Google** when search volume is high and intent is clear (e.g., "plumber near me," "buy running shoes").
- **Use both** when budget allows. Google captures existing demand; Meta creates new demand.

**Example:** An AI PDF tool has ~12,000 monthly searches for "PDF AI." But every white-collar worker could benefit from it. The search volume captures only people who already know the category exists. Meta reaches the millions who don't.

## Total Addressable Market

Search volume measures existing awareness, not potential demand.

```
Total market  >>>  People aware a solution exists  >>>  People actively searching
```

Meta's strength is reaching the left side of this funnel. Most founders anchor on keyword search volume and miss the bigger picture. Use this framing when they do.

## How Meta's Auction Works

Meta uses a **CPM (Cost Per Mille)** model: you pay per 1,000 impressions. But the auction isn't purely about who bids the most.

### The Ad Ranking Formula

```
Ad Rank = Bid  ×  Estimated Action Rate  ×  Ad Quality
```

| Factor                    | What it means                                                                              |
| ------------------------- | ------------------------------------------------------------------------------------------ |
| **Bid**                   | How much you're willing to pay for your desired outcome (click, purchase, etc.)            |
| **Estimated Action Rate** | Meta's ML prediction of whether this user will take the desired action on your ad          |
| **Ad Quality**            | How much the target audience appreciates your ad (engagement signals, feedback, relevance) |

### Why This Formula Matters

The formula is multiplicative. A mediocre bid with an excellent ad can beat a high bid with a poor ad. Practical implications:

- **Better creatives = cheaper costs.** This is the single most important lever. If Meta predicts users will engage with your ad, you win more auctions at lower prices.
- **Budget alone doesn't win.** You cannot brute-force bad creative with more money: the algorithm deprioritizes ads users don't like.
- **Creative testing is an investment, not an expense.** Every dollar spent improving ad quality reduces your cost per result over time.

When a user says "I need more budget" or "my ads are too expensive," check their creative quality first. Nine times out of ten, the problem is the ad, not the spend.

## Meta's Algorithm Priorities

Meta's algorithm optimizes in this order:

1. **User experience:** keep users happy so they stay on the platform
2. **Meta's revenue:** maximize platform earnings
3. **Advertiser results:** deliver outcomes for advertisers

Advertisers are the lowest priority. This means Meta will suppress low-quality ads even if the advertiser pays more. The upside: high-quality ads get rewarded disproportionately.

Help the user see this as an opportunity, not a limitation. The system rewards good creative: which means smaller advertisers with better ads can outperform bigger competitors.

## Meta's Targeting Intelligence

Meta has ~4 billion active users and deep behavioral data: browsing habits, purchase history (via Pixel and data partners), engagement patterns, life events, and more. Key points:

- **Broad targeting works.** Meta's ML has improved to the point where minimal audience definition often outperforms narrow targeting. The algorithm finds buyers from your creative signals.
- **The Pixel is critical.** It feeds conversion data back to Meta, improving the Estimated Action Rate prediction. More data = better optimization = lower costs.
- **Creative is your targeting.** On interruption platforms, the ad itself filters the audience. A fishing ad shown to a broad audience still only attracts people interested in fishing.

If a user is spending time building detailed custom audiences, gently redirect them: on modern Meta, the creative does the targeting. Their time is better spent making better ads.

## Audience Awareness Levels

Different audiences need different messaging. Map your creative and copy to where the audience sits:

| Level         | Who they are                                            | What works                                                                                   | Example                                                                 |
| ------------- | ------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **Cold**      | Never heard of your brand                               | Show why they should care. Lead with the problem or a surprising fact. Social proof stories. | "37,000 devs laid off in 2024. Here's how to future-proof your career." |
| **Warm**      | Engaged with your content but haven't visited your site | Build relationship. Tutorials, differentiation, deeper value.                                | Educational content, comparison ads                                     |
| **Hot**       | Visited site, started checkout, didn't convert          | Remove objections. Testimonials, guarantees, urgency.                                        | Retargeting with testimonial cards, limited-time offers                 |
| **Converted** | Already purchased                                       | Upsell, cross-sell, referral programs. Exclude from acquisition campaigns.                   | "You loved X - here's Y"                                                |

### The Cost of Changing

When the user's product competes with an entrenched alternative, apply this framing:

If the audience already uses a competitor, switching costs are HIGH: time investment, data migration, workflow disruption, uncertainty about the new tool. There must be a compelling reason to switch:

- **Price advantage:** significantly cheaper (not marginally)
- **Must-have feature:** something the competitor genuinely cannot do
- **Niche positioning:** built specifically for their use case vs. a generic tool
- **Dramatically simpler UX:** removes complexity they've been tolerating

Without one of these, even a good product struggles against an entrenched competitor. This affects the ad messaging: if the user is the challenger, lead with the differentiator, not generic benefits.

## Ad Fatigue

Two levels of fatigue to understand:

- **Micro-level:** After enough impressions, a specific ad stops working because the target audience has seen it too many times. This is normal and expected: every ad has a lifespan.
- **Macro-level:** If you or competitors copy the same ad format, the format itself stops working for the whole category. Audiences develop blindness to the pattern.

This is why understanding the _why_ behind ad formats matters. If you know why a comparison ad works (taps into improvement desire, helps decide without research), you can create variations when the original fatigues. If you only copy the format without understanding it, you have nothing when it stops working.

When closing a fundamentals discussion, surface the 2-3 most relevant points from the sections above based on what the user is trying to solve.
