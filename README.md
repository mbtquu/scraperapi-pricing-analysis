# data scraping software: Real Pricing, the Credit Trap Nobody Warns You About, and How to Pick the Right Tool for Your Stack

Most people searching for data scraping software are trying to solve one problem: get structured data from websites reliably, without maintaining proxies, headless browsers, and CAPTCHA-solving logic themselves. The catch is that pricing pages make every tool look cheap until you actually run a project — then credit multipliers, concurrency caps, and geotargeting limits change the real bill by 5–50x. This guide walks through how modern scraping tools are priced, what ScraperAPI actually charges (verified against its current pricing page), where its credit system can bite you, and which situations call for a different category of tool entirely.

> **Quick picks**
> - Developer pulling structured pages via API: ScraperAPI's Hobby plan at $49/mo (or $44.10/mo billed annually) with 100,000 credits is the entry point. Most credit surprises come from the domain cost table, so read the credit section below before committing.
> - Just testing whether scraping works for your target sites: start with the free plan (1,000 credits, 5 concurrent connections) or the 7-day trial with 5,000 credits, no credit card required.
> - Non-technical business user who wants rows in a spreadsheet: an API is the wrong category — no-code tools like Browse AI (from $19/mo) or Octoparse (from $69/mo) fit better.
>
> 👉 [Check ScraperAPI's current plans and trial](https://www.scraperapi.com/?fp_ref=coupons)

## Why "data scraping software" now splits into five very different categories

The single biggest mistake buyers make is comparing tools across categories as if they compete head-to-head. They don't. A scraping API, a no-code desktop app, and an enterprise proxy network solve different jobs, and picking the wrong category means paying for proxies, browser sessions, or maintenance you never needed.

The categories that matter:

1. **Scraping APIs** (ScraperAPI, ScrapingBee): developers send a URL to a single endpoint; the vendor handles proxies, CAPTCHAs, and rendering. Smallest request surface, fastest integration.
2. **Managed platforms** (Apify): ready-made scrapers, scheduling, storage, and execution in one place. Apify's store now lists more than 65,000 ready-made scraping and automation tools.
3. **No-code visual tools** (Octoparse, Browse AI, ParseHub): you build the scraper by clicking, not coding.
4. **Enterprise infrastructure** (Bright Data): proxy networks and scraper IDEs for large-scale, heavily protected targets, typically from around $500/mo.
5. **Open-source frameworks** (Scrapy, Crawlee): maximum control, but your team owns deployment, proxies, monitoring, and recovery.

Context matters here too. The Thales/Imperva 2025 Bad Bot Report found automated traffic hit 51% of all web traffic in 2024, with bad bots at 37%, up from 32% in 2023. Sites fight back harder than they used to, which is why access reliability — not feature checklists — should drive your shortlist.

## ScraperAPI plans and pricing: the full lineup

ScraperAPI's pricing page currently shows seven paid tiers plus a free plan, all priced in USD per month. Every plan includes JavaScript rendering, premium residential and mobile IPs, JSON auto-parsing, CAPTCHA and anti-bot detection, custom headers and sessions, automatic retries, unlimited bandwidth, and a 99.9% uptime guarantee.

| Plan | Monthly price | Annual (per month, 10% off) | API credits | Concurrent threads | Get it |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | — | 1,000 | 5 | [ Sign up free](https://www.scraperapi.com/?fp_ref=coupons) |
| Hobby | $49 | $44.10 | 100,000 | 20 | [ Start Hobby](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 | [ Start Startup](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 | [ Start Business](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Scaling (most popular) | $475 | $427.50 | 5,000,000 | 200 | [ Start Scaling](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 | 300 | [ Start Professional](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 | 500 | [ Start Advanced](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | [ Talk to sales](https://www.scraperapi.com/pricing?fp_ref=coupons) |

Two things on this table deserve a second look. First, Hobby and Startup only support geotargeting in the US and EU; country-level targeting starts at Business. Second, analytics history on Hobby and Startup is capped at the last 30 days, while Business and up get unlimited history. Neither limit shows up prominently on marketing pages, but both matter once you're running scheduled jobs.

New accounts also get a 7-day trial with 5,000 credits and no credit card required — and if you pay and change your mind, there's a 7-day no-questions-asked refund on top.

## The credit system: where pricing pages get quietly complicated

A "standard page" costs 1 credit, but ScraperAPI — like every credit-based scraping API — charges more for harder targets. This is the part most comparison posts skip, and it's where real budgets get decided.

The fixed domain costs, per ScraperAPI's own pricing FAQ:

- Standard pages: **1 credit**
- E-commerce (Amazon, Walmart, eBay): **5 credits**
- Google and Bing (including subdomains): **25 credits**
- LinkedIn: **30 credits**
- Sites behind Cloudflare, Datadome, or PerimeterX: **+10 credits per request** when bypassed

Rendering and proxy options stack multipliers on top: JS rendering or premium proxies cost 10 credits, premium plus rendering costs 25, and ultra-premium plus rendering costs 75 per request.

What this means in practice: that 100,000-credit Hobby plan isn't 100,000 pages. At standard rates it is; if half your requests are Google SERP scrapes, it's closer to a few thousand of those plus your standard pages. The same plan can realistically deliver anywhere from roughly 1,300 to 100,000 scrapes depending on what you're hitting.

Two safeguards make this manageable rather than scary:

- The **Domain Cost Estimator** in your dashboard shows the exact credit cost for any URL before you run it.
- The `max_cost` parameter caps how many credits any single request can burn, so one accidentally expensive target can't drain your pool.

Also worth knowing: failed requests don't consume credits. ScraperAPI retries with different IPs until a request succeeds, and only successful responses are billed.

## Real annual cost: monthly vs annual, and what happens when you run out

Annual billing takes 10% off every paid plan. On Hobby that's $588 versus $529.20 over a year — $58.80 saved. On Business it's $3,588 versus $3,229.20, saving $358.80. Meaningful, not dramatic; the more consequential difference between plans is what happens when credits run out.

- **Hobby, Startup, Business**: scraping pauses until the next billing cycle. Your options are upgrading manually or enabling **Auto-upgrade** (opt-in), which moves you to the next plan automatically when credits deplete.
- **Scaling, Professional, Advanced, Enterprise**: you can enable **Pay-as-you-go** overage at a fixed per-credit rate, up to a monthly spending cap you set, without changing plans.

That's a genuine decision factor. If your request volume spikes unpredictably — flash sales, news cycles, monitoring jobs that balloon — a plan with PAYG overage prevents hard stops mid-project. If your volume is steady, paying for a Scaling plan just to unlock overage is unnecessary; Auto-upgrade on Hobby through Professional covers gradual growth.

Concurrency is the other hidden governor. Exceeding your plan's thread limit returns a 429 response — requests are rejected, not queued, and you're expected to throttle and retry. Twenty concurrent threads on Hobby is plenty for a script polling a few endpoints; it's tight for a fan-out job over thousands of URLs.

## Who ScraperAPI isn't for

An API requires writing code. If your team's workflow is "open a browser, highlight the data, export to Sheets," a scraping API adds friction instead of removing it. For that profile, the no-code category fits better: Browse AI starts at $19/mo for scraping and monitoring, Octoparse from $69/mo for desktop-plus-cloud visual workflows, and ParseHub offers a free desktop tool with paid plans from $189/mo. Browser extensions like Clura or the webscraper.io extension handle quick in-browser extractions, with Clura's free tier allowing 20 scrapes per day at 500 rows each.

At the other end of the scale, if your targets are aggressively protected sites and you need millions of requests monthly with fine-grained proxy control, Bright Data's infrastructure (from roughly $500/mo, usage-based) is built for that job and has the deeper proxy network. Apify sits between: its paid plans start at $29/mo, and its marketplace approach means common targets often have a pre-built actor you can run before writing anything.

ScraperAPI's sweet spot is the middle: developers who want predictable, per-credit pricing and a single GET endpoint instead of managing proxy pools and headless browsers. Its "dead simple API" positioning is real — one endpoint, parameters like `render=true` for JavaScript pages, `country_code=us` for geotargeting, and `premium=true` for residential IPs. Official SDKs cover Python, Java, PHP, Ruby, Node, and Bash.

## What actual users say

ScraperAPI holds a 4.4/5 on G2 as of mid-2026 roundups. The most frequently mentioned complaint in user reviews is customer support responsiveness — some reviewers report waiting over 24 hours for a reply — and a subset of users have flagged lower-than-expected success rates on specific targets. Both complaints point to the same practical advice: test your actual target sites on the free plan or trial before committing to an annual term. Success rates vary sharply between sites, and a generic ranking can't predict how your specific targets behave.

On the company side: ScraperAPI was founded in 2018, bootstrapped to roughly $3M in revenue with about 10,000 customers, and was acquired by SaaS.group in 2020. In April 2026 it acquired Traject Data, whose portfolio includes the Rainforest and SerpWow APIs — meaning Amazon and SERP data now flow through the same credit system. Also confirmed in its billing docs: there's no bandwidth-based pricing and no option to buy individual proxies; billing is purely per-request credits.

## FAQ

**Do failed requests cost credits?**
No. ScraperAPI retries failed requests with different IPs automatically, and only successful responses are billed.

**What happens when I hit my concurrency limit?**
You get a 429 response and the request is rejected rather than queued. Lower your concurrency and retry; there's no extra charge.

**Is there a free plan?**
Yes — 1,000 free API credits with up to 5 concurrent connections, available at signup. The separate 7-day trial adds 5,000 credits with no credit card required.

**Can I get a refund after paying?**
Yes. ScraperAPI offers a 7-day no-questions-asked refund after you go paid, so the effective risk-free window is roughly two weeks counting the trial.

**How many pages does 100,000 credits actually get me?**
Between about 1,300 and 100,000 scrapes, depending on targets and options. Standard pages cost 1 credit; Amazon costs 5, Google/Bing cost 25, LinkedIn costs 30, and JS rendering or premium proxies add multipliers up to 75 credits per request.

## Choosing: a decision rule you can actually use

Match the tool to your target and your team, in this order:

1. **You write code and want predictable per-request pricing** → ScraperAPI. Start on the free plan, run your real targets, then pick the tier whose credits survive your worst-case domain costs. 👉 [Start the 7-day trial with 5,000 credits](https://www.scraperapi.com/?fp_ref=coupons)
2. **Your volume spikes unpredictably** → pick Scaling or above to unlock pay-as-you-go overage instead of hard stops.
3. **You need country-level geotargeting or unlimited analytics history** → Business is the floor; Hobby and Startup are US/EU-only with 30-day analytics.
4. **You don't code** → skip APIs entirely; no-code tools from $19/mo will serve you better.
5. **You're scraping heavily protected sites at enterprise scale** → proxy-infrastructure vendors built for that tier are the better fit, even at $500+/mo.

One last check before you click buy: open the Domain Cost Estimator, paste the URLs you actually plan to scrape, and confirm your chosen plan's credits cover at least two months of projected volume at those rates. If the numbers work, the 7-day trial and refund policy make it cheap to verify the rest. 👉 [View ScraperAPI's full plan comparison](https://www.scraperapi.com/pricing?fp_ref=coupons)
