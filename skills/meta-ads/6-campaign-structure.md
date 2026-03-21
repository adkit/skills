# Launching Campaigns: Setup and Structure

## Contents

- [Before You Start](#before-you-start)
- [Account Safety](#account-safety)
- [The Three-Level Hierarchy](#the-three-level-hierarchy)
- [Campaign Objectives](#campaign-objectives)
- [Ad Set Configuration](#ad-set-configuration)
- [Recommended Account Structure](#recommended-account-structure)
- [Naming Conventions](#naming-conventions)

## Before You Start

Ask the user:

- What do you sell? (product type, price point)
- What's your daily budget?
- Do you have pixel data already? (conversions firing?)
- Have you run Meta ads before?

Use the answers to route through this guide:

| Situation                            | Recommended path                                                                                                  |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| No pixel data, no ad history         | Leads objective, single ad set, low budget ($2-5/day). Jump to **Low budget setup**.                              |
| Has pixel data, budget under $10/day | Sales objective, single ad set with Flexible Creatives. Optimize for the event with the most data.                |
| Has pixel data, budget $25-50+/day   | Sales objective, 2-3 ad sets (interest + broad + lookalike). Full **Default setup**.                              |
| Has pixel data, budget $100+/day     | Consider Advantage+ Shopping in addition to manual campaigns. See **Other Setups** in [7-launch.md](7-launch.md). |
| New ad account, any budget           | Warmup first: $2-5/day for a few days (billing verification, not data). Then scale to target budget. See **Account Safety** below. |

> **Ask:** "What's your main goal: sales or leads?" Use the answer to select the campaign objective below. Never use awareness/traffic/etc unless the user specifically asks for it.

## Account Safety

New ad accounts need a **warmup period**: a few days at low spend so Meta can verify billing. Not for data collection. Scale to target budget after warmup.

| Situation                  | Rule                                             | Consequence of breaking it                                |
| -------------------------- | ------------------------------------------------ | --------------------------------------------------------- |
| New or low-history account | Start at $2-5/day                                | High initial spend triggers fraud detection, possible ban |
| Payment method             | Use a working credit card (not debit)            | Rejected payment = instant ban                            |
| Location / VPN             | Access from the billing address location, no VPN | Account flag, possible restriction                        |
| Scaling budget             | Increase max 10-20% every 48 hours               | Larger jumps disrupt optimization and look suspicious     |
| Launch timing              | Start between midnight and 6 AM target timezone  | Mid-day start = rushed spend, less relevant audiences     |
| Underperforming campaign   | Lower budget instead of pausing                  | Repeated toggling resets learning phase and flags account |
| New account review         | Schedule 12h buffer for first launch             | Meta reviews new ads; if delayed, budget gets rushed      |

## The Three-Level Hierarchy

Every Meta ad account is organized in three nested levels:

| Level        | What you set here                                                | Think of it as                            |
| ------------ | ---------------------------------------------------------------- | ----------------------------------------- |
| **Campaign** | Objective, overall budget (CBO), spending limits                 | The goal                                  |
| **Ad set**   | Audience, placements, schedule, optimization event, budget (ABO) | Who sees it, when, and how Meta optimizes |
| **Ad**       | Images/videos, copy, headlines, CTA, destination URL             | What people actually see                  |

## Campaign Objectives

| Objective                 | When to use                                                                                            | When to skip                                           |
| ------------------------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------ |
| **Sales**                 | You sell a product/subscription and want direct conversions. Default for most advertisers.             | You have no pixel events firing yet.                   |
| **Leads**                 | You collect emails, signups, or contact info. Great for pre-launch, lead-magnets, or high-touch sales. | You can already sell directly from a landing page.     |
| **App Promotion**         | Same as sales but when advertising a mobile apps. Requires separate tracking setup.                    | You don't have a mobile app.                           |
| **Engagement/Video View** | When making retargeting audiences + cheap Social Proof.                                                | You care about revenue, not vanity metrics.            |
| **Traffic**               | Never, garbage traffic.                                                                                | Always skip.                                           |
| **Awareness**             | Massive brand-building budgets (think Coca-Cola). Don't use                                            | You need measurable ROI. 99% of advertisers skip this. |

**Most common choice:** Sales. If budget is tight or you lack pixel data, start with Leads.

## Ad Set Configuration

### Optimization and Conversion Events

Set **Performance goal** to "Maximize number of conversions" and select a pixel event (purchase, subscribe, signup, etc.). Use the goal table in [7-launch.md](7-launch.md) to pick the right event based on budget and product price.

If the chosen event has zero or very few fires, Meta has nothing to learn from. Options: optimize for a lower-funnel event with data (e.g., signup instead of purchase), drive some organic conversions first, or use leads as a stepping stone.

### Audiences

**Start broad.** Meta finds buyers without interest targeting. Over-targeting from day one limits the algorithm.

| Type               | Setup                                                                                          | Best for                                                        |
| ------------------ | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| **Interest-based** | Add relevant interests. Use Meta's "Suggestions" button to expand. Aim for 50M+ audience size. | First ad sets when you have no pixel data.                      |
| **Broad**          | No interests, no custom audiences. Just location + age. Let Meta figure it out.                | Accounts with existing pixel data. Often outperforms interests. |
| **Lookalike**      | Based on a custom audience (subscribers, purchasers). Meta finds the top 1% similar users.     | You have 1,000+ people in a source audience.                    |

**Location:** Target all countries you sell to, not just US/UK/CA/AU. Can include Europe etc. - anywhere with purchasing power (if it makes sense).

**Age and gender:** Leave as broad as possible (18-65+, all genders). Meta already knows who converts. Even for gendered products, Meta can find gift buyers.

**Exclusions:** To target only new people, exclude custom audiences of existing subscribers or purchasers at the ad set level.

### Placements

Use **Advantage+ placements** (Meta's default). Manual placement selection is almost never worth it. Meta automatically stops showing ads on underperforming placements.

### Schedule

**Start between midnight and 6 AM** in the target timezone. Mid-day launches cause Meta to rush spending the remaining daily budget on less relevant audiences. For new accounts, schedule for the next day with a 12-hour buffer to account for Meta's ad review.

**End dates:** Don't set them unless running a time-limited promotion. Pause manually instead.

## Recommended Account Structure

> **Ask:** "How much can you spend per day on ads?" Then recommend the matching structure below.

**Default setup (works for $25-50+/day):**

```
Campaign (Sales, CBO, $25-50/day)
+-- Ad Set: Interest-based (SEO, marketing, etc.)
|   +-- Ad (Flexible Creatives): 3 media + 2 texts + 1 headline
+-- Ad Set: Broad (no targeting)
|   +-- Ad (Flexible Creatives): same assets
+-- Ad Set: Lookalike (if you have 1k+ source audience)
    +-- Ad (Flexible Creatives): same assets
```

- 1 campaign, 1-3 ad sets, one **Flexible Creatives** ad per ad set or 3 manual ads.
- Enable **Flexible Creatives**. Meta mixes media, copy, and headlines to find winning combinations.
- Flexible Creatives formula: **3 media + 2 primary texts + 1 headline** (reduce to 2 media + 1 text if budget is under $10/day). For the 2 texts: one short (hook + benefit + CTA) and one long (PAS or 5-step framework: see `4-copy.md`).
- Create the first ad set with its ad fully configured, then **duplicate** the ad set to create variations. This preserves ad setup and saves time.

**Low budget setup (under $20/day):**
Optimize for Leads instead of Purchase, then manually contact leads. Consider Meta's **Instant Forms** instead of a landing page: conversions happen inside Facebook, so tracking is 100% accurate and costs are lower.

Ads under $20/day are not recommended tho, better use other channels until cashflow is available.

## Naming Conventions

Consistent naming makes it easy to analyze performance and cross-reference with external analytics.

**Campaigns:** `{project} {goal} {date}` - e.g., `Adkit - Sales - 2027-03-20`. Keep it explicit so you can differentiate campaigns at a glance.

**Ad sets:** `{event} {audienceType} {audienceName}` - e.g., `Purchase - Interest - Executives` or `Purchase - Broad`. The event tells you what you're optimizing for, the audience type tells you how you're targeting, and the audience name identifies the specific group (omit if broad).

**Ads:** `{creativeId} {copyId} {headlineId}` - e.g., `video_a3kx - copy_b7mq - headline_c2nf`. Generate short unique IDs for each creative, copy, and headline. This lets you identify winning combinations from the dashboard without opening individual ads. If headline and copy are the same across ads, the only variable is the creative ID, making it easy to spot the winner at a glance.

**UTM parameters** for external analytics (Posthog, GA, etc.):

| Parameter      | Value                  |
| -------------- | ---------------------- |
| `utm_source`   | `{{site_source_name}}` |
| `utm_medium`   | `{{placement}}`        |
| `utm_campaign` | `{{campaign.id}}`      |
| `utm_content`  | `{{ad.id}}`            |
| `utm_term`     | `{{adset.id}}`         |

Set these in the ad's URL Parameters field. They survive ad blockers that may block pixel events, providing a backup data source.

---

For optimization goals, budget formulas, scaling, creative testing, and advanced setups: see [7-launch.md](7-launch.md).
