# Account Setup

## Contents
- [Prerequisites Check](#prerequisites-check)
- [Business Manager](#business-manager)
- [Ad Account](#ad-account)
- [Avoiding Bans](#avoiding-bans)
- [Meta Pixel & Tracking](#meta-pixel--tracking)
- [Facebook Page](#facebook-page)
- [Custom Audiences](#custom-audiences)

Guide for setting up Meta advertising infrastructure. Walk the user through each component: most of these require manual action in Meta's UI.

## Prerequisites Check

Ask the user which of these they already have:

- [ ] Business Manager at business.facebook.com
- [ ] Ad account (with correct time zone and currency)
- [ ] Meta Pixel installed on their website
- [ ] Facebook Page with content
- [ ] Custom audiences configured

Skip to the first unchecked item below.

## Business Manager

The user must create this at business.facebook.com/overview. You cannot do this for them.

**Walk them through:**

1. Create a Business Manager (each person can only create 2: if they've hit the limit, someone else must create one and add them as admin)
2. Add a backup admin: if their account gets locked, someone else can pause ads and recover access
3. Enable 2FA in Security Center: Meta treats this as a trust signal and it unlocks features
4. Fill in business info (legal name, website, phone): another trust signal
5. Verify the business if the option is available (unlocks higher spend limits). May not appear until after some initial ad spend.

**Verify:** Ask the user to confirm they can see their Business Manager dashboard at business.facebook.com/overview.

## Ad Account

Two settings are **permanent and cannot be changed after creation**. Make sure the user gets these right:

- **Time zone:** Set to the customer's time zone, not theirs. The daily budget resets at midnight in this zone. Ask: "Where are most of your customers located?" Use that region's time zone (e.g., New York for US audiences).
- **Currency:** Match their bank account currency to avoid conversion fees.

### Payment method: one card per ad account

This is critical for ban protection. Ask: "How are you planning to pay for ads?"

**Recommend credit cards over debit cards.** Credit cards result in fewer bans in practice, and the user earns miles/rewards on ad spend. Virtual credit cards are ideal: one per ad account.

| Payment method       | Recommendation                                      |
| -------------------- | --------------------------------------------------- |
| Virtual credit card  | Best: one per ad account, fewer bans, earn rewards |
| Physical credit card | Fine if they only have one ad account               |
| Debit card           | Works but higher ban risk                           |
| PayPal               | Avoid: PayPal freezes accounts unpredictably       |

**Why isolation matters:** When Meta bans an ad account, all assets linked to it are at risk - including the payment method. If one card is on five accounts, all five are compromised.

**Pro tip:** If the user can create multiple ad accounts (limit increases with trust), tell them to create the maximum allowed upfront - even empty ones. If one gets restricted, they can't create new ones. Having spares is insurance.

## Avoiding Bans

Bans are a reality of Meta advertising. Almost everyone experiences some form of restriction. The hierarchy of severity:

| Restriction                 | Severity  | What happens                                                                             |
| --------------------------- | --------- | ---------------------------------------------------------------------------------------- |
| Ad rejected                 | Low       | Single ad not published: fix the ad and resubmit                                        |
| Budget restriction          | Medium    | Spend capped (sometimes as low as $2/day): keep spending, it lifts over time            |
| Ad account restricted       | High      | Entire account disabled: switch to a spare ad account                                   |
| Page restricted             | High      | Usually from multiple restricted ad accounts linked to one page, or many user complaints |
| Business Manager restricted | Very high | You can only have 2 BMs: losing one is serious                                          |
| Personal account restricted | Critical  | Cannot create new BMs or ad accounts. Recovery is extremely difficult                    |

**Rules to minimize risk:**

1. **Always pay on time.** If the card gets declined (insufficient funds), it's almost an instant ban. Ask the user: "Does your payment card have enough balance for ongoing charges?"
2. **Respect Meta's ad policies.** Bad landing pages, misleading claims, and policy violations raise CPMs even before a ban. Tell the user to review Meta's advertising standards.
3. **Avoid changing IPs frequently.** Logging in from different countries triggers fraud detection. If the user travels, suggest using a VPN set to their home country.
4. **Don't add payment methods from high-risk countries.** The card's issuing country matters: mismatches between account location and card country raise flags.
5. **Don't create multiple personal accounts.** They're verified with ID. Getting caught means all accounts are at risk.

## Meta Pixel & Tracking

Ask: "Do you have the Meta Pixel installed on your website?"

If no, walk them through it:

1. Install the base pixel code on every page (found in Events Manager → Data Sources → Pixel → Settings)
2. Set up standard events for key actions: always prefer standard events over custom ones (Meta has historical data to optimize standard events)

| Event                    | When to fire                             |
| ------------------------ | ---------------------------------------- |
| `PageView`               | Every page load (included in base pixel) |
| `InitiateCheckout`       | User clicks a buy/subscribe button       |
| `Purchase` / `Subscribe` | After successful payment                 |
| `CompleteRegistration`   | After sign-up                            |
| `Lead`                   | Form submission                          |

3. Include `currency`, `value`, and `predicted_ltv` parameters with purchase events: this lets Meta optimize for revenue, not just conversion count

**Verify:** Ask the user to install the Meta Pixel Helper Chrome extension and confirm events are firing on their key pages.

**Important:** Install the pixel before running any ads. Data collection starts immediately. Lookalike audiences and optimization improve significantly after ~100 conversion events.

### UTM Parameters

Set UTM parameters in each ad's URL Parameters field so external analytics (GA4, Plausible, etc.) can attribute traffic independently of the pixel.

**Name-based (human-readable in analytics):**

```
utm_source={{site_source_name}}&utm_medium={{placement}}&utm_campaign={{campaign.name}}&utm_content={{ad.name}}&utm_term={{adset.name}}
```

**ID-based (doesn't break when you rename things):**

```
utm_source={{site_source_name}}&utm_medium={{placement}}&utm_campaign={{campaign.id}}&utm_content={{ad.id}}&utm_term={{adset.id}}
```

Use the ID-based version if you rename campaigns/ads frequently. The name-based version won't update retroactively in analytics if something gets renamed later.

NOTE: [AdKit](https://adkit.so) add UTM parameters automatically for you.

## Facebook Page

Ask: "Do you have a Facebook Page for your business? Is it filled out with content?"

An empty page kills trust and raises CPMs. Pages with regular content activity consistently get lower CPMs: this is a pattern observed over years of ad spend.

**Walk the user through:**

1. Fill out all info: bio, website, social links, email, phone
2. Post at least a few pieces of content (product updates, tips, anything): bare minimum before running ads
3. Use a profile picture and cover image that match their brand

Even basic posts make a difference. An empty page signals "created 2 minutes ago" to both users and Meta's systems.

## Custom Audiences

Ask: "Do you have any existing customer data (email lists, website traffic via pixel)?"

Three audience types:

| Type          | What it is                                                               | When to use                                                    |
| ------------- | ------------------------------------------------------------------------ | -------------------------------------------------------------- |
| **Custom**    | People who already interacted (pixel events, email lists, video viewers) | Retargeting, building lookalikes                               |
| **Lookalike** | Meta finds people similar to a custom audience (1% = most similar)       | Prospecting: finding new customers who resemble existing ones |
| **Saved**     | Pre-saved demographic/interest targeting                                 | Rarely useful: broad targeting often outperforms              |

### Naming convention (0-3 system)

| Prefix | Temperature | Who                                              | Example                           |
| ------ | ----------- | ------------------------------------------------ | --------------------------------- |
| **0**  | Cold        | Never heard of the brand                         | Interest-based or broad targeting |
| **1**  | Warm        | Engaged on Meta but never visited site           | `1 - Video viewers 50% - 30d`     |
| **2**  | Hot         | Visited site, initiated checkout, didn't convert | `2 - InitiateCheckout - 180d`     |
| **3**  | Customer    | Already purchased/subscribed                     | `3 - Subscribers - 180d`          |

### Lookalike requirements

- Minimum 100 people in the source audience from the target country
- 1% = top 1% most similar people in that country
- Work best with large source audiences (hundreds+ conversions)
- Meta's own targeting has improved: lookalikes are less essential than before but still valuable with strong conversion data

If the user is just starting and has no pixel data or email list, skip audiences for now. Start with broad targeting and let Meta's algorithm find the right people.

### Country Targeting List

Use as a starting point for location targeting:

Tier 1: English-native countries with high purchasing power.

```
United States, Canada, United Kingdom, Australia, New Zealand
```

Tier 2: Countries with English as second languages + high purchasing power.

```
Austria, Australia, Belgium, Canada, Switzerland, Germany, Denmark, Spain, Finland, France, United Kingdom, Ireland, Iceland, Italy, Japan, South Korea, Netherlands, Norway, New Zealand, Portugal, Sweden, Singapore, United States
```

Adjust based on the user's product: remove countries they don't serve, add others where they have customers.
