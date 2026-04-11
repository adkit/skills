# Analyzing Results

## Contents
- [Where to Start](#where-to-start)
- [Key Metrics (KPIs)](#key-metrics-kpis)
- [The Diagnostic Framework](#the-diagnostic-framework)
- [Statistical Relevance](#statistical-relevance)
- [When and How to Act](#when-and-how-to-act)
- [Real Diagnostic Example](#real-diagnostic-example)
- [Mindset: Buying Data, Not Sales](#mindset-buying-data-not-sales)
- [Seasonal and External Factors](#seasonal-and-external-factors)
- [Creative Fatigue](#creative-fatigue)

This guide covers the key metrics, how to diagnose problems, and when to act.

## Where to Start

Start with these questions:

- How long have your ads been running?
- What's your current daily budget?
- What are you seeing that concerns you? (or: are things going well and you want to scale?)

If ads have been running < 3 days or have < 1,000 impressions, it's too early to draw conclusions. Wait for more data.

## Key Metrics (KPIs)

| Metric                    | What It Measures                                   | Why It Matters                                                                                                                                                 |
| ------------------------- | -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **CPM**                   | Cost per 1,000 impressions                         | Baseline ad cost. Higher = more competitive/expensive audience. Varies by audience, creative, and season (spikes Nov-Dec).                                     |
| **CTR** (unique outbound) | % of impressions that clicked through to your site | Use unique outbound: one click per person, only counts clicks leaving the platform.                                                                            |
| **CPC**                   | Cost per unique outbound click                     | Derived from CPM and CTR.                                                                                                                                      |
| **Frequency**             | Average times each person saw your ad              | Under 2 is fine. Above 3-4 signals creative fatigue: people start ignoring familiar ads.                                                                      |
| **Hook Rate**             | % who watched first 3 seconds of video             | Custom metric: 3-second video plays / impressions. Measures if your video catches attention. Only relevant for real video ads, not static-image videos.        |
| **Conversion Rate**       | % of landing page visitors who purchased           | Custom metric: purchases / landing page views. Measures landing page and offer effectiveness.                                                                  |
| **ROAS**                  | Revenue per dollar of ad spend                     | A 1.44 ROAS means $1.44 revenue per $1 spent. Factor in customer lifetime value: a subscription product can be profitable at ROAS < 1 if retention is strong. |

**Ask:** "Can you share your CTR, CPM, and cost per result?"

### Click types matter

The platform reports multiple click variants. "Clicks (all)" includes likes, video plays, read-more expands - any interaction. "Link clicks" count clicks to your URL but can include the same person multiple times. **Always use unique outbound clicks** (and unique outbound CTR): this counts one click per person going outside the platform, which is the closest measure of "people who actually visited your site."

### Reading the funnel

**Track every conversion step.** Set up columns for content view, registration, checkout initiated, and purchase. A big drop between steps pinpoints where the problem is. e.g., 100 checkouts but 1 purchase means your checkout flow is broken. Without intermediate steps, you are guessing. With them, you know exactly where to focus.

### Understanding reach vs. impressions

Frequency = impressions / reach. A "high impressions" number can mean either broad reach or repeated exposure to the same people - very different situations requiring different responses.

## The Diagnostic Framework

Think like a doctor: observe symptoms, hypothesize causes, prescribe solutions. You can never be 100% certain. Make your best educated guess and test it.

### Symptom-Cause-Action Table

| Symptom                             | Likely Cause                                                           | Action                                                                                                                                                                               |
| ----------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| No sales + low CTR + low CPM        | Ad not appealing to audience. Cheap impressions but nobody clicks.     | Test new creative. Try different audience. Honestly evaluate if the product has demand.                                                                                              |
| No sales + high CTR + low CPM       | Landing page problem. People click (ad works) but don't convert after. | Install session recording (Hotjar/Clarity) to watch real user behavior. Make a test purchase in production to verify nothing is broken. Improve landing page copy, speed, or design. |
| No sales + high CTR + high CPM      | Expensive audience clicking but not buying.                            | Check landing page first. If landing page is fine, the audience may be too niche or competitive: test broader targeting.                                                            |
| High frequency (3+) + declining CTR | Creative fatigue. Audience has seen the ad too many times.             | Launch new creatives. Expand or change audience.                                                                                                                                     |
| CPM dropping + CTR dropping         | Platform exhausted retargeting pool, now showing to colder audiences.  | Expected behavior. Monitor for 1-2 weeks. If results don't recover, launch creatives tailored to cold audiences (people unfamiliar with your brand).                                 |
| Rising cost per result over weeks   | Audience exhaustion. Often one ad absorbs all budget and wears out.    | Check if budget is concentrated on one ad. Cut exhausted ads. Launch new campaign with fresh creatives.                                                                              |
| Big drop-off between funnel steps   | Broken or weak step in the funnel (e.g., checkout bug, slow page).     | Investigate the specific step. Test the flow yourself. Fix technical issues before changing ads.                                                                                     |

**If you see high CTR but no sales:** test the purchase flow yourself. Something might be broken. A working ad sending traffic to a broken checkout is the most expensive mistake in advertising.

## Statistical Relevance

**Do not draw conclusions from small samples.** Random variance dominates at low volumes.

- **Minimum:** 1,000 impressions before analyzing. Ideally 3,000+.
- **Exception:** If results are catastrophically bad early (CTR under 1%, CPM above $100, CPC above $10 at 500+ impressions), you can act sooner.
- **Use weekly aggregates** over daily when you have 2+ weeks of data. Day-to-day swings (weekends, holidays, random events) are noise. The trend over weeks is the signal.
- **Breakdown by day** to spot patterns (weekends often underperform for B2B), but make decisions on weekly averages.

**Lower budgets amplify this problem.** At $5-15/day, it takes longer to accumulate meaningful data. Consider optimizing for cheaper events (leads, signups) instead of purchases to get statistical relevance faster.

## When and How to Act

**Wait before acting.** Most premature decisions come from too little data or emotional reactions.

**After 1-2 bad days:** this is normal variance. Pull up the weekly trend instead. One bad day - or even two - tells you almost nothing. The question is always: what does the week look like?

Decision tree:

1. **Do I have enough data?** (1,000+ impressions minimum). If no, wait.
2. **Is the trend clear over multiple days/weeks?** If one bad day, wait. If 2-3 bad weeks, act.
3. **Where in the funnel is the drop?** Identify the weakest step.
4. **What changed?** CPM shift? CTR decline? Frequency creeping up? Each points to a different cause.

### Actions by situation:

- **Ad not working (low CTR):** New creative, different angle, different audience.
- **Landing page not converting (high CTR, low sales):** Session recordings, test purchase, improve page.
- **Audience exhausted (declining CTR over weeks, one ad eating all budget):** Cut the exhausted ad, launch fresh creatives. Have new ads ready _before_ old ones fatigue.
- **Results recovering after a dip:** Do nothing. Let the platform optimize. Not every dip requires intervention.
- **Budget not spending fully:** Check for platform-imposed restrictions. Verify ad approval status.
- **Holiday or seasonal dip:** Do not optimize based on seasonal spikes or dips. Compare like periods - this week vs. last week at similar conditions, not Tuesday vs. Sunday.

## Real Diagnostic Example

A campaign running $100/day for 4 weeks:

- **Week 1:** $30 cost per purchase, 7% CTR. Excellent.
- **Week 2:** $40 cost per purchase, 5% CTR. CPM dropping. Platform shifting from retargeting to cold audiences.
- **Week 3:** $50 cost per purchase, 4% CTR. Continued decline. Lowering budget didn't help.
- **Week 4:** $100+ cost per purchase, 3% CTR. One ad consumed all budget with 100,000+ impressions.

**Diagnosis:** Audience pool exhaustion. The creative worked well for retargeting and AI-savvy users but didn't resonate with cold audiences. Frequency was still acceptable (~2), so it wasn't repetition: it was reaching less qualified people.

**Action taken:** Cut the exhausted ad. Gave remaining ads a chance. Launched new campaign with creatives designed for cold audiences (people unfamiliar with the product category).

**Key lesson:** Creatives that work for warm audiences may fail for cold audiences. When the platform expands reach, you may need different messaging.

### What "no action" looks like

Not every dip requires intervention. In the example above, after Week 2 the initial response was to wait and observe: the right call. The platform was testing new audience pockets, and one good day suggested it might self-correct. Only after Week 3-4 confirmed the sustained decline was action taken. Patience with sufficient data beats reactive changes every time.

## Mindset: Buying Data, Not Sales

Frame every spend as data acquisition: which audiences engage, which creatives resonate, where the funnel breaks. Use the diagnostic framework before making any change.

## Seasonal and External Factors

Results fluctuate based on factors outside your control:

- **Holidays** (Easter, Christmas, national holidays): people are offline, not in buying mode. Expect worse results.
- **Q4 (Nov-Dec):** CPMs spike across the board due to e-commerce competition. The same ads cost more to deliver.
- **Weekends:** B2B products typically see lower engagement Saturday-Sunday. B2C varies by category.
- **Platform algorithm changes:** Periodic shifts in delivery behavior. If all campaigns suddenly change at once, it may not be the ads.

## Creative Fatigue

Creatives don't last forever. Every ad eventually wears out as the audience becomes oversaturated.

**Key signals to watch:**

- **Frequency above 3-4:** Each person has seen the ad 3+ times on average. Engagement drops, cost rises.
- **CTR declining week-over-week** while CPM holds steady: the audience is ignoring the ad.
- **Rising cost per result** with no audience or budget changes: the ad is running out of receptive people.
- **One ad absorbing all budget:** When Meta concentrates spend on a single ad, that ad is likely exhausting its audience pocket.

**Fatigue timeline by audience size:**

| Audience size | Typical fatigue point |
|--------------|----------------------|
| < 100k       | 1-2 weeks            |
| 100k-1M      | 3-6 weeks            |
| 1M+          | 6-12 weeks           |

Retargeting audiences (small and warm) fatigue much faster than cold prospecting audiences.

**What to do:**

- Cut exhausted creatives. If one ad has absorbed disproportionate budget and metrics are declining, pause it.
- Launch replacement creatives before the old ones die. Always have fresh creatives in the pipeline: waiting until an ad fatigues leaves you scrambling.
- Rotate angles. A new hook or copy angle extends the life of the same offer by reaching a different segment of the audience.
- Expand or change audiences if the current pool is too small to sustain volume.

