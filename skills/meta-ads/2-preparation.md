# Preparing For Ads

## Contents

- [Readiness Check](#readiness-check)
- [Product Validation](#product-validation)
- [Acquisition Cost & Profit](#acquisition-cost--profit)
- [Cashflow Management](#cashflow-management)
- [Knowing Your Customer](#knowing-your-customer)
- [Funnel & Landing Page](#funnel--landing-page)
- [Pre-Launch Checklist](#pre-launch-checklist)

Before the user spends money on ads, walk them through four pillars: numbers, cashflow, customer knowledge, and funnel. Skipping any of these wastes ad budget.

## Readiness Check

Before proceeding, ask the user these questions. If any answer is no, address that section first before moving on.

- **Do they have paying customers or proven demand?** If not, walk them through the Product Validation section below.
- **Can they calculate their LTV?** If not, walk them through the LTV section below.
- **Do they have a funded payment method?** If not, cover Cashflow Management first.
- **Do they know their customer?** If they can't describe their ideal customer's problem, goals, and objections: they aren't ready. Walk them through Knowing Your Customer.
- **Is their landing page ready?** If it's not live, or they haven't optimized copy and conversion path: cover Funnel & Landing Page first.

## Product Validation

Ads amplify what already works. Without proven demand, there's no signal to optimize against and budgets burn fast with no learnings.

**Ads make sense when:**

- People are already buying (even a few customers proves demand)
- LTV is high enough to support paid acquisition (see Acquisition Cost & Profit below)
- The funnel converts organic traffic (landing page works, people sign up/buy)
- Cash reserves can cover the learning period (ads aren't always profitable immediately)

**Warning signs (proceed with caution):**

- No customers yet, product still unvalidated
- Can't describe the target customer from real experience
- Landing page has never converted a stranger

If the user has no validation, warn them clearly but don't block them. Recommend they read [When Should a SaaS Run Ads?](https://adkit.so/resources/when-to-run-ads-for-saas) before deciding.

## Acquisition Cost & Profit

Ads trade profit margin for volume. The question isn't "will ads eat my profit?" It's "how much profit am I willing to trade for how many more customers?"

Ask the user: "What's your product's price, and do you have upsells or recurring revenue?" Use their answer to walk them through LTV calculation.

### Lifetime Value (LTV)

LTV = total revenue one customer generates over their entire relationship with you.

| Business Model                      | LTV Calculation                               | Example                               |
| ----------------------------------- | --------------------------------------------- | ------------------------------------- |
| Subscription                        | Monthly price x avg months before churn       | $10/mo x 12 months = $120             |
| One-time + upsells                  | Initial purchase + avg upsell revenue         | $50 course + $100 consultation = $150 |
| Ad-monetized (newsletter, free app) | Revenue per user per period x active duration | $0.10/ad x 12 months = $1.20          |

### Key Formulas

```
Max Acquisition Cost = LTV - Operational Cost Per User
```

This is the **break-even point**. Spend more than this and you lose money.

```
Target Acquisition Cost = Max Acquisition Cost - Desired Profit Per Customer
```

This is what to actually aim for, defined by the user's profit goals. There is no universal benchmark.

**Example:** SaaS with $200 LTV, $10/user server costs - max acquisition cost = $190. If the user wants $90 profit per customer, the target acquisition cost is $100.

### Key Insight

If the user's product is cheap with no upsells (e.g., a $5 one-time purchase), ads will be nearly impossible to make profitable. Ask them: "Can you increase your LTV? Add upsells, bundles, annual plans, or complementary products?" If the answer is no, be honest: ads probably aren't the right channel for them yet.

## Cashflow Management

Ads drain cash **before** revenue comes in. This mismatch kills campaigns. Walk the user through payment setup carefully: mistakes here can permanently lose them their ad account.

### What to Know

- Ad platforms bill frequently (Meta starts at $2-$5 thresholds for new accounts, increasing with payment history)
- **Failed payments trigger instant, permanent account bans.** This is extremely difficult to recover from. Emphasize this to the user: it's one of the most common and devastating mistakes.
- If acquisition cost exceeds first-sale revenue, you run negative upfront. e.g., $50 acquisition cost on a $20/mo subscription means 3 months to break even per customer

### Payment Method Setup

Ask the user: "What payment method are you planning to use for ads?"

- **Credit cards are better than debit cards for ad payments.** Credit cards have fewer payment failures (which cause bans), earn miles/rewards on ad spend, and offer fraud protection. If the user only has a debit card, strongly recommend they get a credit card first.
- **Recommend virtual credit cards: one per ad account.** Services like Privacy.com or bank-issued virtual cards let the user isolate each ad account. If one account has issues, it doesn't affect others.
- If the user says they'll use a debit card, warn them: a single insufficient-funds event can trigger an irrecoverable ban.

### Rules to Follow

| Rule                                                     | Why                                                                   |
| -------------------------------------------------------- | --------------------------------------------------------------------- |
| Ensure payment method always has sufficient funds        | One failed payment can trigger account restrictions or permanent bans |
| Notify your bank that ad platform charges are legitimate | Banks sometimes flag recurring platform charges as fraud              |
| Start with $2-5/day budgets on new accounts              | Large spend on new accounts triggers fraud detection and bans         |
| Set Stripe/payment payouts to daily or weekly            | Monthly payouts create dangerous cashflow gaps                        |
| Prefer steady low spend over start-stop cycles           | The algorithm penalizes pausing and restarting campaigns              |

### Cash Strategies

Walk the user through which of these apply to their business model:

- **Annual plans**: collect 12 months upfront instead of monthly, fund ads immediately
- **Upsells at checkout**: increase upfront revenue per customer
- **Budget for negative ROI period**: if their payback period is 3 months, they need 3 months of ad budget as working capital

## Knowing Your Customer

### What You Must Know

| Dimension       | What to Capture                                                | Why It Matters for Ads                                                               |
| --------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Demographics    | Age, job title, gender, location                               | Targeting and creative tone                                                          |
| Goals           | What they want to achieve                                      | Ad messaging: speak to the outcome                                                   |
| Before/After    | Current pain → life after your product                         | Ad copy structure (problem → solution)                                               |
| Objections      | Hesitations, deal-breakers, unanswered questions               | Handle in ad copy and landing page                                                   |
| Awareness level | Never heard of solutions like yours vs. comparing alternatives | Unaware audiences need problem-first messaging; aware audiences need differentiation |

### How to Collect This

1. **Customer interviews** (best): 15-30 min calls reveal triggers you'd never guess
2. **Email surveys** (good): one question at a time. "What problem does [product] solve for you?"
3. **Competitor research** (no customers yet): read their reviews, social proof, landing page copy, and Twitter/Reddit mentions

### Questions to Ask the User

Walk the user through these one at a time. If they struggle to answer, they need to do customer research before running ads.

- Who is your ideal customer? (job, demographics, context)
- What problem does your product solve for them?
- What were they doing before they found your product?
- What objections come up before purchase?
- Has your audience heard of products like yours, or is this a new category?

If the user can't answer these, tell them directly: "You aren't ready for ads yet." Help them run customer research first.

## Funnel & Landing Page

The funnel matters more than the ads. A great ad sending traffic to a bad page wastes every dollar. Improving landing page conversion from 0.5% to 1% doubles results at the same ad spend.

Ask the user: "What page will your ads send people to?" Then walk them through the checklist below.

### Why It Matters to the Algorithm

Ad platforms evaluate landing page quality. A poor page lowers the quality score, which raises costs and reduces delivery. The funnel is the **only part of the ad system the user fully controls**.

### Optimization Checklist

- **Copywriting is the #1 conversion lever.** Rewrite headlines and CTAs before changing anything else
- **Minimize clicks to conversion.** One or two clicks max. Skip account creation for direct sales: send users straight to checkout
- **Only ask for what you need.** At signup, ask for email only. Collect the rest later
- **Shortest path to email capture.** Even if they don't buy, get the email so you can follow up

### Post-Click System

Ask the user: "What happens after someone clicks your ad and lands on your page?" If they don't have email sequences set up, flag it: they're leaving money on the table.

| Scenario              | Required Setup                                                       |
| --------------------- | -------------------------------------------------------------------- |
| Free trial / freemium | Email onboarding sequence nudging toward paid                        |
| Direct purchase       | Abandoned cart email sequence (drives 15-30% of e-commerce sales)    |
| Newsletter / lead gen | Lead magnet: free PDF, mini-course, template - in exchange for email |

### Policy Compliance

Tell the user: "Before you launch, read Meta's advertising policies. It takes about 15 minutes and can save your account."

Bad landing pages, misleading claims, and policy violations can get ads rejected. Repeated violations lead to account bans: like payment bans, these are very hard to reverse. Ad platforms scan the landing page linked in the ad. Non-compliant pages get ads rejected. Only the page you link in the ad gets scanned: other site pages are unaffected.

If the user's landing page makes income claims, health claims, or before/after promises, warn them these are the most commonly flagged categories.

## Pre-Launch Checklist

Before the user spends a single dollar on ads, walk them through this list and confirm each item:

- [ ] LTV and max acquisition cost are calculated
- [ ] Target acquisition cost is defined (with desired profit margin)
- [ ] Payment method is a credit card (ideally virtual), funded, and bank is notified
- [ ] Starting budget is low ($2-5/day)
- [ ] Customer persona is documented (demographics, goals, objections, awareness)
- [ ] Landing page copy addresses the customer's problem and objections
- [ ] Conversion path is 1-2 clicks max
- [ ] Email sequences are set up for non-converters
- [ ] Ad platform policies have been read
