# ProxyRack pricing: what $49.95, $65.95 and per-thread billing actually buy, and how to cut the bill

ProxyRack has been selling proxies since 2014, and in that time the company has accumulated more billing models than most competitors have products. There's a metered residential plan charged by the gigabyte, an unmetered residential plan charged by threads, another unmetered plan charged by ports, datacenter pools charged by threads, static US datacenter charged by ports, and mobile traffic charged by the gigabyte again.

That's why "ProxyRack pricing" is a harder question than it sounds. The headline number is $49.95 per month, but $49.95 buys something very different depending on which product page you land on, and the tiers are rendered in the browser rather than listed in a plain table. Third-party trackers that logged ProxyRack's plans in 2026 came back with different entry points depending on which product they measured.

Here's what's actually verifiable, what each model costs in practice, and where a per-IP alternative such as 9Proxy ends up cheaper for the same workload.

## The four billing models behind ProxyRack's prices

Before comparing dollar figures, it helps to know what you're being charged for, because ProxyRack meters four different things.

**Metered residential (Premium Residential)** — billed per gigabyte. You buy a monthly traffic package and the pool rotates. This is the plan most people mean when they search for ProxyRack pricing.

**Unmetered residential** — billed per concurrent thread. No data cap; the limit is how many simultaneous connections you can run.

**Private unmetered residential** — billed per port, with each port giving you a dedicated IP at a time. ProxyRack's own documentation states the thread limit is calculated by multiplying your port count by 140, so a 5-port subscription gives you 700 threads across all ports, not 140 per port.

**Datacenter and mobile** — rotating datacenter pools are charged by thread, static US datacenter by port, and mobile traffic by the gigabyte.

Nothing about that structure is dishonest, but it does mean two people paying "about fifty dollars a month" can be getting wildly different amounts of capacity. If your workload is a slow scraper pulling small JSON responses, threads matter far more than gigabytes. If you're pulling large HTML pages or media, the gigabyte meter becomes the binding constraint.

## ProxyRack's published prices at a glance

These are the figures ProxyRack publishes or documents on its own help pages, cross-checked against independent price trackers.

| Product | Billing unit | Published price |
| --- | --- | --- |
| Premium Residential | Per GB | 10 GB for $49.95/month; 20 GB for $89.95/month; 199 GB for $199.95/month |
| Unmetered Residential | Per thread | Listed from around $65/month by price trackers; other comparison pages quote roughly $199/month for 100 threads |
| Private Unmetered Residential | Per port | From 5 ports at $65.95/month |
| Static USA Datacenter | Per port | From 100 ports at $50.00/month |
| Trial | One-off | $13.95 for 7 days of access to all products |

Two things stand out.

First, the entry tier works out to roughly $5.00 per gigabyte at 10 GB. By the 199 GB tier that drops to about $1.00 per gigabyte — a genuine volume discount, but one you only reach by committing nearly $200 a month up front. ProxyRack does not offer pay-as-you-go traffic, so there is no cheap way to test the metered product at low volume.

Second, the unmetered numbers disagree between sources. ProxyLook's provider page lists an Unmetered Residential tier at $65/month, while comparison pages from other proxy vendors quote unmetered thread plans starting nearer $199/month for 100 threads. Both may be correct for different tiers, but the fact that independent trackers can't agree is itself useful information: ProxyRack's unmetered pricing scales with thread count and isn't cleanly published, so treat any single quoted figure as a starting point and confirm the total at checkout.

The trial is the one unambiguous piece of good news. $13.95 for seven days of access to every product is cheaper than most competitors' entry plans, and it's the only realistic way to measure whether the network performs on your specific targets.

Annual billing cuts roughly 15% off monthly rates. There's no free tier, and no wallet or stored-credit system — each purchase is a separate transaction, which is worth knowing if you're used to topping up a balance.

<blockquote>Practical note: because ProxyRack's tiers load dynamically on the product pages, prices you find in a review written six months ago may already be stale. Confirm on the checkout page before budgeting.</blockquote>

## The per-GB math that decides everything

Here's a rough way to tell whether the metered plan is even the right shape for your project.

A 10 GB monthly package at $49.95 gives you 10,000 megabytes. If your scraper pulls 200 KB per page, that's about 50,000 page loads a month — around 1,600 a day. That's a healthy volume for competitor price monitoring on a few hundred products. It is not enough for going anywhere near a video-heavy site, and it evaporates fast if you're rendering JavaScript pages, where a single request can consume several megabytes before you've parsed anything useful.

If your workload is small requests with high rotation, per-GB pricing is inefficient — you're paying for bandwidth you barely use. That's the gap a per-IP model fills.

## Costs and limits that don't appear in the headline price

Price per gigabyte is only part of the bill. A few ProxyRack conditions affect the real cost of running it:

- **KYC is mandatory.** You verify through the dashboard before using the service. Budget time for that on day one, not day three when a campaign is live.
- **A long blocklist.** ProxyRack restricts a large list of domains, including financial sites, anything matching "bank", and government domains. Email-related ports, remote desktop, database ports, proxy chaining and DDoS traffic are prohibited. If your target list touches any of those categories, you'll be filtering it yourself.
- **No two-factor authentication** on the dashboard, and no address-level wallet. Sub-users are handled by creating an entirely separate dashboard account with its own email address.
- **Fragmented usage stats.** Data isn't cross-referenceable between products or between sub-users, which makes cost-per-project reporting fiddly for teams.
- **Performance varies by region.** Independent benchmarking published in 2026 found ProxyRack's residential pools connecting reliably from US and European exits but with noticeably higher error rates in India and Brazil, and response times up to four times slower than leading alternatives on larger pages. Its US rotating datacenter pool performed much better, with over 99% request success and roughly 40 MB/s throughput in the same tests.

None of this is fatal. It does mean the cheap-looking entry price carries operational overhead that doesn't show up on the invoice.

## Where the model starts to hurt

If you're buying residential IPs for session-based work — holding a login, running account-based tasks, keeping one identity stable across a workflow — per-GB billing charges you for a limit you never hit, while thread or port billing forces you to buy capacity in chunks you may not need.

That's the specific problem 9Proxy was built around. Instead of metering traffic, its IP-based packages sell a fixed number of residential IPs with unlimited bandwidth on each. Unused IPs don't expire, which matters if your work comes in bursts rather than running 24/7.

👉 [Check 9Proxy's current IP and GB packages](https://bit.ly/9-Proxy)

The trade-off is honest: 9Proxy runs a smaller pool than the largest providers — over 20 million residential IPs across 90+ countries — and it doesn't sell mobile proxies or offer the same enterprise-grade feature depth. If you need mobile IPs or extremely granular targeting on obscure regions, it isn't the right fit.

## 9Proxy plans and prices in full

9Proxy runs three purchasing models, and it announced its first-ever price adjustment effective June 1, 2026 — IP-based and bundle packages went up, GB-based packages stayed the same.

### IP-based packages (unlimited bandwidth per IP)

| Package | Price per IP | Total | Billing | Buy |
| --- | --- | --- | --- | --- |
| 100 IPs | $0.24 | $24 | One-off package, no expiry | [Get 100 IPs](https://bit.ly/9-Proxy) |
| 500 IPs | $0.144 | $72 | One-off package, no expiry | [Get 500 IPs](https://bit.ly/9-Proxy) |
| 1,000 IPs + 500 bonus | $0.084 | $126 | One-off package, no expiry | [Get 1,000 + 500 IPs](https://bit.ly/9-Proxy) |
| 2,500 IPs | $0.084 | $210 | One-off package, no expiry | [Get 2,500 IPs](https://bit.ly/9-Proxy) |
| 5,000 IPs | $0.072 | $360 | One-off package, no expiry | [Get 5,000 IPs](https://bit.ly/9-Proxy) |
| 15,000 IPs | $0.048 | $720 | One-off package, no expiry | [Get 15,000 IPs](https://bit.ly/9-Proxy) |
| 25,000 IPs | $0.035 | $863 | One-off package, no expiry | [Get 25,000 IPs](https://bit.ly/9-Proxy) |
| 50,000 IPs | $0.029 | $1,438 | One-off package, no expiry | [Get 50,000 IPs](https://bit.ly/9-Proxy) |
| 100,000 IPs (Business) | $0.023 | $2,300 | One-off package, no expiry | [Get 100,000 IPs](https://bit.ly/9-Proxy) |
| 200,000 IPs (Business) | $0.021 | $4,140 | One-off package, no expiry | [Get 200,000 IPs](https://bit.ly/9-Proxy) |
| 500,000 IPs (Business) | $0.018 | $8,625 | One-off package, no expiry | [Get 500,000 IPs](https://bit.ly/9-Proxy) |

### GB-based packages (rotation, no IP commitment)

| Package | Price per GB | Total | Validity | Buy |
| --- | --- | --- | --- | --- |
| 5 GB | $3.00 | $15 | 180 days | [Get 5 GB](https://bit.ly/9-Proxy) |
| 50 GB + 5 GB bonus | $2.10 | $105 | 180 days | [Get 50 GB + 5 GB](https://bit.ly/9-Proxy) |
| 100 GB | $1.50 | $150 | 180 days | [Get 100 GB](https://bit.ly/9-Proxy) |
| 200 GB | $1.00 | $200 | 180 days | [Get 200 GB](https://bit.ly/9-Proxy) |
| 1,000 GB | $0.80 | $800 | 180 days | [Get 1,000 GB](https://bit.ly/9-Proxy) |
| 2,000 GB | $0.75 | $1,500 | 180 days | [Get 2,000 GB](https://bit.ly/9-Proxy) |
| Enterprise GB | Custom, down to $0.68 at high volume | Custom | Unlimited | [Talk to 9Proxy about enterprise volume](https://bit.ly/9-Proxy) |

### Bundle packages (IPs plus traffic)

| Package | Contents | Price | Buy |
| --- | --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 | [Get the Starter bundle](https://bit.ly/9-Proxy) |
| Popular | 1,500 IPs + 50 GB | $180 | [Get the Popular bundle](https://bit.ly/9-Proxy) |
| Pro | 5,000 IPs + 500 GB | $720 | [Get the Pro bundle](https://bit.ly/9-Proxy) |

GB-based plans carry 180-day validity, and enterprise plans remove the expiry entirely. Bundle traffic follows the same 180-day window. Protocols covered are HTTP, HTTPS and SOCKS5, with targeting down to country, state, city, ZIP code and ISP.

## How the two compare on the numbers

Put the entry tiers next to each other and the difference becomes very concrete.

|  | ProxyRack | 9Proxy |
| --- | --- | --- |
| Smallest real purchase | 10 GB for $49.95/month (~$5.00/GB) | 100 IPs with unlimited bandwidth for $24, or 5 GB for $15 |
| Unmetered option | From ~$65/month (thread or port based) | 100 IPs at $24 |
| Expiry on unused balance | Monthly subscription — unused traffic doesn't carry over | IPs don't expire; GB traffic valid 180 days |
| Pay-as-you-go | Not offered | Package-based, no subscription required |
| Mobile proxies | Yes | No |
| IP pool | 5M+ monthly residential IPs, 140+ countries | 20M+ residential IPs, 90+ countries |
| Free/trial access | $13.95 for 7 days | Trial access via support promotions |

For a project pulling 30 GB a month, ProxyRack's metered product would land somewhere around $135–150 monthly depending on tier. Coming at the same volume from 9Proxy's GB side, 50 GB costs $105 with 180 days to consume it. That's not a dramatic gap — it's the difference between a monthly meter that resets and a balance that waits for you.

For session-heavy work, the comparison isn't close. 100 residential IPs with unlimited bandwidth for $24 replaces a purchase that ProxyRack only offers at thread or port scale, starting around $50–65 a month.

## Which one to buy

**Choose ProxyRack if** your workload is bandwidth-dominant and continuous — large-scale scraping where you'll reliably consume the gigabytes, or US datacenter scraping where the rotating pool benchmarked well. The thread-based unmetered plans also make sense if you need very high concurrency and want the flexibility of per-session rotation with no data ceiling. Budget for the KYC step and the domain blocklist review.

**Choose 9Proxy if** your work is bursty, session-based, or measured in IP count rather than gigabytes — account management, price checks across a fixed set of regions, or automation that runs a few days a month and idles the rest. Non-expiring IPs and 180-day traffic validity mean you aren't paying monthly for capacity you only use part of the time. The lower entry point also means you can start at $15 or $24 and scale up only if the success rates hold on your targets.

**Run both for a month if** you're spending more than a few hundred dollars on proxies. The 7-day ProxyRack trial costs $13.95, and neither provider publishes success rates on your specific target sites — that number only exists after you test it.

## FAQ

**Does ProxyRack have a free trial?**
No. It offers a $13.95 paid trial that gives seven days of access to all products.

**Is ProxyRack cheaper than 9Proxy?**
Depends entirely on the model. Per gigabyte at low volume, 9Proxy's GB packages are cheaper ($3.00/GB at 5 GB versus roughly $5.00/GB at ProxyRack's 10 GB tier). At very high sustained bandwidth, ProxyRack's thread-based unmetered plans can work out cheaper per gigabyte, provided you actually saturate the threads.

**Do 9Proxy IPs expire?**
Unused IP-based package IPs don't expire. GB-based traffic is valid for 180 days, and enterprise bandwidth has no expiry.

**Can I pay by crypto?**
ProxyRack accepts credit card, PayPal and bank transfer, with Bitcoin and other options through Payssion. Only one payment method is refundable.

**Which is better for mobile proxies?**
ProxyRack, unambiguously. 9Proxy's network is residential IPs.

## Bottom line

ProxyRack's entry price of $49.95 sounds reasonable until you work out that it buys 10 GB, which is a light week for a serious scraper. The unmetered plans are where the real value sits, and they're priced for teams running continuous operations, not for people testing an idea. Add KYC, a long blocklist, and pricing tiers that change between product pages, and the effective cost of getting started is higher than the headline suggests.

If your usage is continuous and bandwidth-heavy, ProxyRack's thread-based unmetered tier is a defensible purchase. If your usage is spiky and measured in IPs rather than gigabytes, buying 100 IPs with unlimited bandwidth for $24 and keeping them until you use them is simply a better-fitting bill.

👉 [Compare 9Proxy's packages and pick a starting tier](https://bit.ly/9-Proxy)
