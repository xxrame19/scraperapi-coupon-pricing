# scraperapi coupon code: which codes actually work, what you'll really pay, and how to pick a plan that doesn't burn credits

The short version: the promo code that keeps getting independently verified for ScraperAPI is **START10** — 10% off your first month on any paid plan, for new signups. Beyond that, the biggest discount has nothing to do with coupons: annual billing takes 10% off every month of the year, no code required. And if you haven't used the service yet, the 7-day free trial hands you 5,000 API credits without asking for a credit card.

There's a catch worth understanding before you type a code into checkout, though. ScraperAPI bills by credits, and "1 request = 1 credit" stops being true the moment you point the API at Amazon, Google, or anything sitting behind Cloudflare. This article covers which codes are real, the full current plan lineup, what a credit actually costs you on different target sites, and the billing math that matters more than the coupon itself.

## Quick picks

> **Most people:** the **Hobby plan at $49/month** ($44.10/month billed annually) is the entry point, and **START10** knocks another 10% off the first month. Scraping Google SERPs or heavily protected sites? Read the credit-cost section first — it changes the math. Still evaluating? Burn the free 5,000 trial credits on your real target sites before paying for anything.

👉 [See all plan prices and claim the free trial](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Which ScraperAPI coupon codes actually work

One code has consistent, multi-source verification: **START10**, worth 10% off your first month on any paid subscription, applied at checkout during signup and limited to new accounts.

The aggregator scene around this product is messier than for most SaaS tools. Sites listing "28% off," "50% off," or hundreds of "verified" codes are mostly running auto-generated placeholders — ScraperAPI's own pricing page publishes no public coupon program, so those numbers have nothing behind them. Other codes that circulate in affiliate content occasionally get claimed to work, but none carry the track record START10 does, and affiliate codes can be retired without notice.

Two details on how the discounts stack:

- **START10 can combine with annual billing.** Annual is already 10% off every month, and the code's first-month discount applies on top at checkout. That makes month one the cheapest month you'll ever have — from month two, you're back to the standard rate.
- **The trial needs no code.** The 7-day trial with 5,000 credits requires no promo code and no credit card, so there's nothing to stack there.

## ScraperAPI plans and pricing (full lineup)

ScraperAPI currently lists seven self-serve tiers plus a custom Enterprise option. Annual billing takes 10% off all paid plans; the table shows the official monthly rate with the annual per-month rate in parentheses.

| Plan | Monthly price | Annual (per month) | API credits / month | Concurrent threads | Geo targeting |
| --- | --- | --- | --- | --- | --- |
| Free Trial | $0 (7 days) | — | 5,000 one-time | 5 | — |
| Hobby | $49/mo | $44.10/mo | 100,000 | 20 | US & EU only |
| Startup | $149/mo | $134.10/mo | 1,000,000 | 50 | US & EU only |
| Business | $299/mo | $269.10/mo | 3,000,000 | 100 | Global |
| Scaling | $475/mo | $427.50/mo | 5,000,000 | 200 | Global |
| Professional | $975/mo | $877.50/mo | 10,500,000 | 300 | Global |
| Advanced | $1,975/mo | $1,777.50/mo | 21,500,000 | 500 | Global |
| Enterprise | Custom quote | Custom | 22,000,000+ | 500+ | Global |

Every paid plan ships with the same core feature set: JavaScript rendering, premium residential and mobile IPs, automatic CAPTCHA handling, JSON auto-parsing, custom sessions and headers, automatic retries, unlimited bandwidth, and a 99.9% uptime guarantee. The tiers mostly buy you volume, concurrency, and geography.

| Plan | Buy link |
| --- | --- |
| Hobby | [ Start the Hobby plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | [ Start the Startup plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | [ See the discounted annual rate](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | [ Check current pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional / Advanced | [ Check current pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | [ Contact sales for a custom plan](https://www.scraperapi.com/?fp_ref=coupons) |

One detail that matters if you outgrow your plan: once credits run out, Hobby, Startup, and Business simply pause until the next renewal. You can upgrade mid-cycle or opt into auto-upgrade, but there's no automatic overflow billing on those tiers. Only Scaling and above get **pay-as-you-go**, which keeps scraping past your allocation at a fixed per-credit rate up to a monthly cap you set. If your request volume spikes unpredictably, that difference alone can justify the jump from Business to Scaling.

What do actual customers say? The recurring themes across Capterra and GetApp reviews are fast integration (several reviewers describe swapping one line of code and having everything work), savings in engineering hours compared with maintaining your own proxy rotation, and responsive support. The recurring complaint: occasional timeouts or lower success rates on specific hard-to-scrape sites. None of that is universal, which is exactly why the trial credits are worth using on your real targets.

## What a credit actually buys (the part most coupon pages skip)

Here's what separates people who are happy with ScraperAPI from people who torch 100,000 credits in a week: credits are not requests.

The official cost model looks like this:

| Request type | Credits per request |
| --- | --- |
| Standard unprotected page | 1 |
| Amazon | 5 |
| Google / Bing (including subdomains) | 25 |
| LinkedIn | 30 |
| `render=true` (JavaScript rendering) | +10 |
| `premium=true` (residential/mobile proxies) | +10 |
| `screenshot=true` | +10 |
| Cloudflare / Datadome / PerimeterX bypass | +10 |
| `ultra_premium=true` | +30 |
| `premium=true` + `render=true` combo | 25 total |
| `ultra_premium=true` + `render=true` combo | 75 total |

Note that the combos don't add linearly — pairing ultra-premium proxies with rendering costs 75 credits flat, not 40.

The math gets ugly fast. On Hobby, scraping Amazon product pages with rendering enabled costs 15 credits per request — your 100,000 monthly credits get you roughly **6,600 successful scrapes**, not the 100,000 the plan name implies. A Google SERP scrape with rendering runs 35 credits. Point the same API at a plain, unprotected blog and you're back near the sticker number.

Two built-in tools keep this under control:

1. **Domain Cost Estimator** — enter any URL in the dashboard before you build your scraper, and it tells you exactly what that target costs per request. Run your real target domains through it before picking a plan; it's the single best predictor of whether Hobby is enough.
2. **`max_cost` parameter** — set a ceiling on what any single request can consume, so an accidental flag combination can't silently drain thousands of credits.

One genuinely fair detail worth knowing: failed requests don't burn credits. Anything outside a successful response gets refunded, so you're paying for data actually delivered rather than for the service's own failures. And unused credits don't roll over — whatever you don't spend by renewal is gone.

## What you'll actually pay in year one and year two

Coupons make the first month look cheaper than the subscription really is, so it's worth running the numbers on the two most common entry points.

**Hobby, annual billing, with START10:**

- Month 1: $44.10 × 0.90 = **$39.69**
- Months 2–12: $44.10 × 11 = **$485.10**
- Year one total: **about $524.79**, or roughly $43.73/month
- Year two onward: $529.20/year — the coupon is gone, the annual discount stays

**Hobby, monthly billing, with START10:**

- Month 1: $49 × 0.90 = **$44.10**
- Months 2–12: $49 × 11 = $539
- Year one total: **about $583.10**
- Year two onward: $588/year

In the first year, annual billing with the coupon comes in about **$58 cheaper** than monthly billing with the coupon, and the gap roughly doubles in year two once the coupon disappears from both scenarios. Another way to see it: START10 saves $4.90 one time, while annual billing saves $4.90 every month — so the annual discount's total value catches up with the coupon's by the second month and keeps growing. Annual billing on Business saves about $358 per year.

One honest caveat. START10 circulates through affiliate and review pages rather than being published on ScraperAPI's own pricing page, which means it can be pulled at any time. If checkout rejects it, you haven't lost much — the annual discount applies regardless, and it's the bigger saving anyway.

👉 [Open an annual plan and apply the code at checkout](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Which plan fits which use case

The pricing table hides one restriction that trips people up: **Hobby and Startup only geotarget the US and EU.** If your project needs local data from Southeast Asia, Latin America, or anywhere else, country-level targeting starts at Business ($299/month). No coupon fixes that, so check it before anything else.

Rough decision rules based on the current lineup:

- **Just evaluating, or a few hundred pages a month** → the permanent free plan (1,000 credits/month, 5 concurrent threads) or the 7-day trial. Don't pay yet.
- **Personal projects, price checks, light monitoring of unprotected sites** → Hobby at $49. Fine as long as you're not hammering Google or Amazon heavily.
- **SERP tracking, competitor monitoring, regular scraping on US/EU targets** → Startup at $149. Ten times Hobby's credits for triple the price, plus 50 concurrent threads.
- **Production workloads needing global geotargeting** → Business at $299, which unlocks country-level targeting everywhere and unlimited analytics history (lower tiers only keep about 30 days of dashboard data).
- **Spiky or growing volume** → Scaling at $475, the first tier with pay-as-you-go overflow instead of a hard stop.
- **Millions of requests daily** → Enterprise custom quote; anything above 22M credits/month goes through sales.

Integration effort is low across all tiers: you swap your existing HTTP request URL for ScraperAPI's endpoint and pass your API key as a parameter. Official SDKs cover Python, Node, PHP, Ruby, and Java, and most setups go live in under an hour — which means the trial credits give you a genuinely representative test rather than a toy demo.

## How to apply the code, step by step

The discount applies during signup, not afterward:

1. [Start your free trial or pick a plan](https://www.scraperapi.com/?fp_ref=coupons) — the trial needs no credit card.
2. At checkout, choose monthly or annual billing (annual is 10% off every month on its own).
3. Enter **START10** in the promo code field. The 10% comes off your first month's charge.
4. Test your real target domains with the trial credits before the first paid renewal. If a target turns out to cost 15–35 credits per request, you still have time to switch tiers before money is on the line.

That last step is the one people skip. The coupon saves you a few dollars; picking the wrong tier costs far more, either in upgrade hassle or in credits wasted on an expensive target.

## Frequently asked questions

**Is there a working ScraperAPI coupon code right now?**
START10 is the code with the most consistent independent verification — 10% off your first month, any paid plan, new signups. The big-percentage codes on coupon aggregators are auto-generated and don't work.

**Does ScraperAPI have a free trial?**
Yes. New signups get 5,000 API credits on a 7-day trial, no credit card required. There's also a permanent free plan with 1,000 credits per month and 5 concurrent connections.

**Do unused credits roll over?**
No. Credits expire at each renewal. Annual plan users who run out early can renew ahead of schedule for a fresh batch.

**What happens if I exceed my plan's limits?**
On Hobby, Startup, and Business, scraping pauses until renewal unless you upgrade mid-cycle or enable auto-upgrade. Scaling and above can keep going on pay-as-you-go pricing with a monthly cap you control. Exceeding your concurrent thread limit returns a 429 error — requests are rejected rather than queued, and not billed.

**Can I use the coupon with annual billing?**
Yes — START10 applies to your first month on top of the annual discount, which is the cheapest possible first month. From month two, you pay the standard annual rate.

**Is it worth paying just to scrape Google?**
Only if you budget for it. Google costs 25 credits per request, 35 with rendering, so do the division against your actual volume before committing to a tier.

## Before you check out

Three quick checks prevent most regrets. Run your real target domains through the dashboard's Domain Cost Estimator. Confirm whether you need non-US/EU geotargeting — if yes, Hobby and Startup are off the table and you're starting at Business. And pick annual billing if you expect to keep the service past a couple of months, since its cumulative saving passes the coupon's by month two.

If those check out, [👉 claim the free trial and enter START10 at checkout](https://www.scraperapi.com/?fp_ref=coupons) for another 10% off your first month. If your volume is unpredictable or your targets sit behind serious anti-bot protection, start with the trial credits alone and only choose a tier once you've seen the real per-request cost.
