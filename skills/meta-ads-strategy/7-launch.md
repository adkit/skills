# Budgets, Testing, and Scaling

## Contents

- [Choosing the Right Optimization Goal](#choosing-the-right-optimization-goal)
- [Creative Testing Setup](#creative-testing-setup)
- [Budget Management](#budget-management)
- [Why Scaling Increases Costs](#why-scaling-increases-costs)
- [Other Setups](#other-setups)

For campaign structure, ad set configuration, and naming conventions: see [6-campaign-structure.md](6-campaign-structure.md).

## Choosing the Right Optimization Goal

The optimization event determines who Meta shows ads to. This is the most consequential budget decision.

**How Meta's optimization loop works:** Your pixel sends conversion data to Meta. The algorithm finds similar people and shows them your ad. Some convert, feeding more data back. More data = better targeting = lower costs. This is why coupling Meta with other traffic channels accelerates learning: the pixel picks up conversions from all sources.

| Goal                                | Use when                                                                                                        | Typical daily budget needed |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------- | --------------------------- |
| **Purchase / Subscribe / Checkout** | Strong landing page, product with proven demand, enough budget for Meta to learn                                | (Acquisition Cost x2)/day   |
| **Signup / Free Trial**             | Product where users convert better after trying it. Test against direct purchase: free trials don't always win. | $25+/day                    |
| **Lead / Email**                    | Pre-launch, low budget, high-touch sales, lead magnets with email automation                                    | As low as $2-5/day          |

> **If budget is under $20/day:** Use Lead/Email optimization. Purchase optimization needs enough budget to generate several conversions per week for Meta to learn.

Collect leads and nurture with email automation instead.

**Lead magnets work:** A free PDF, industry report, or tool that collects emails, followed by an automated email sequence, is one of the most cost-effective funnels for Meta ads.
[Good resource for lead magnets](https://github.com/coreyhaines31/marketingskills/blob/main/skills/lead-magnets/SKILL.md).

**If the chosen event has no data:** Meta is guessing, and results will be poor. Either optimize for a lower-funnel event where you have data (e.g., signup instead of purchase), drive organic conversions first, or use leads as a stepping stone.

## Creative Testing Setup

Methodical testing: change one variable at a time so you know what moved the needle.

### How Many Variants

Run **3-5 ads per ad set**. Fewer gives Meta too little to optimize from. More fragments budget and slows learning.

### What to Iterate (priority order)

1. **Hook:** the first 3 seconds of video or the visual/headline. Most ads are lost here.
2. **Copy angle:** core message framing (pain-focused vs. outcome-focused vs. social proof)
3. **Offer:** pricing, trial, bundle, guarantee
4. **Format:** image vs. video vs. carousel
5. **Full concept:** only after exhausting variations of a working concept

**One variable at a time.** Changing the hook and the offer simultaneously makes it impossible to know which change caused any difference.

### Learning Phase Rules

Meta's algorithm needs time to optimize after any significant change.

- **Target: 50 conversion events per week** per ad set to exit the learning phase.
- **Any significant edit resets learning.** Budget changes, creative swaps, targeting changes all count.
- **Batch changes:** Make multiple edits at once rather than one per day. Each change restarts the clock.
- **Minimum 7 days** before drawing conclusions from a new ad set.

### Flexible Creatives vs. Manual Testing

| Approach               | When to use                                                                              | Trade-off                                                          |
| ---------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| **Flexible Creatives** | Meta finds winning combinations automatically. Good with 50+ conversion events per week. | Less control over which combination runs. Harder to isolate cause. |
| **Manual ads**         | Test specific isolated variables (hook A vs. hook B). Deliberate creative learning.      | Requires more budget per variation to reach statistical relevance. |

Start with Flexible Creatives. Switch to manual testing once you have consistent results and want to understand why something works.

## Budget Management

### Setting Your Initial Budget

**Formula:** Maximum acquisition cost x 2 = daily budget. Run for at least 7 days.

| Optimization | Max cost per result | Daily budget | 7-day spend |
| ------------ | ------------------- | ------------ | ----------- |
| Purchase     | $30                 | $60          | $420        |
| Subscription | $50                 | $100         | $700        |
| Lead         | $3                  | $6           | $42         |

Why 7 days minimum: conversion costs vary by day of week. B2B is cheaper on weekdays. Consumer products spike on weekends. A partial-week test gives unrepresentative data.

**Only spend what you can afford to lose.** Meta ads are a marketing experiment. You are buying data, not guaranteed sales.

### Scaling Rules

| Action              | Rule                      | Why                                                                                         |
| ------------------- | ------------------------- | ------------------------------------------------------------------------------------------- |
| **Increase budget** | Max 10-15% every 48 hours | Larger jumps disrupt optimization. The algorithm needs time to recalibrate.                 |
| **Decrease budget** | Can drop 50%+ immediately | Signals to Meta that current results are poor. Often resets optimization in a positive way. |

Lower budget instead of pausing an underperforming campaign. Only pause if you are done entirely.

### When Ads Are Working

Three options:

1. **Scale budget** (10-20% per 48h): leverages existing data, but may increase cost per conversion.
2. **Leave it alone**: stable, predictable. Every ad eventually fatigues, but this is the safe play.
3. **Launch a new campaign**: test new creatives/audiences without risking what works. Best for significant scaling. Campaigns may compete for the same audience at high spend or very small audiences, but this is rarely an issue under $1k/day.

## Why Scaling Increases Costs

For any budget, Meta prioritizes the cheapest conversions first: people who already interacted with your brand or show strong purchase intent. These "low-hanging fruit" audiences are limited in size.

When you increase budget, Meta exhausts this pool and shows ads to progressively less likely buyers. Same number of sales, higher spend.

**When you cannot scale further**, two options:

1. **Accept the ceiling.** A stable acquisition channel at consistent cost is valuable. Not every product scales beyond a certain spend.
2. **Improve creatives.** A new ad angle that resonates with a different audience segment unlocks a fresh pool of cheap conversions. One product can have many use cases, and each use case appeals to a different pocket of people. Example: a cosmetics brand switching their ad model from a young woman to a grandmother unlocked an entirely new audience that converted at scale.

## Other Setups

### Advantage+ Shopping Campaign

Fully automated: one campaign, one auto-managed ad set, 2-3+ ads. No audience setup, no placement selection. Meta handles everything. Only available for the Sales objective.

**Pros:** Minimal setup. Mixes retargeting and cold audiences automatically. Often strong initial results.
**Cons:** Audience exhaustion after 4-8 weeks. Performance decays and is hard to recover. Best for accounts with substantial existing pixel data. Not recommended as your only campaign.

If Advantage+ decays, fall back to the default manual setup in [6-campaign-structure.md](6-campaign-structure.md).

### Prospecting + Retargeting Split

Separates finding new customers from converting warm ones. Recommend this for advertisers who already have a working campaign and want to scale.

**Prospecting campaign** (finding new people):

- 2-3 ad sets: interest, broad, lookalike
- **Video ads only.** The exclusion mechanism relies on 3-second video views.
- Exclude anyone who watched 3+ seconds of your videos (they move to retargeting)
- Will cost more per conversion. That is expected.

**Retargeting campaign** (converting warm audiences):

- 1 ad set targeting: 3-second video viewers, website visitors (pixel), page engagers
- Exclude existing purchasers (180 days)
- 5-20 ads (images and videos both fine). High volume prevents ad fatigue in small audiences.
- Lower cost per conversion since these people already know you

**Key principle:** Prospecting does not need to be independently profitable. If the combined result across both campaigns is profitable, the system works.
