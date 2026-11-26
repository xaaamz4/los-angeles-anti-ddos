# Los Angeles Anti-DDoS Dedicated Server: Do You Need Bare Metal, How Much Filtering Do You Get, and What Does a Year Actually Cost? (SixtyNet LAX Plans Compared)

SixtyNet's Los Angeles DDoS-protected line starts at **$200/year** for 2 cores, 2 GB RAM, 40 GB NVMe, 5 TB of traffic, filtering included and ports 80/443 open. The same line runs to $800 and $1,600 a year for 8-core boxes with 10 Gbps network ports.

Get one thing straight first: SixtyNet does not sell bare metal. Its LAX plans are VPS instances with DDoS protection, in a single Los Angeles data center. If your project needs a dedicated chassis, two 10 Gbps uplinks and 100 TB of transfer, the entry ticket in this city is around $360/month, and the bare-metal section below tells you who sells that. Most people searching for a "Los Angeles anti-DDoS dedicated server" with a budget under $500 a year are actually shopping for what SixtyNet sells, so the rest of this page is about how to tell whether it fits.

Three things decide that: how much scrubbing capacity you actually get per IP, where the traffic is cleaned, and what happens when an attack passes the ceiling. SixtyNet publishes the first two only vaguely, so you will have to ask. More on that below.

> **Quick pick:** LAX-STARTER, $200/year on annual billing. 2 cores, 2 GB RAM, 40 GB NVMe, 5 TB traffic, DDoS protection, 80/443 open. Enough for a blog, a small store, a panel or a low-pop game server. 👉 [See the LAX plans and current annual prices](https://sixtynet.net/vps-hosting?aff=39)

## SixtyNet's Los Angeles plans in one table

All five plans below sit on the LAX line and include DDoS protection. The first three are the general-purpose ones; the last two are RAID-10 storage variants with the same 10 Gbps network and the same filtering.

| Plan | CPU / RAM | Storage | Network & traffic | Annual price | Order |
| --- | --- | --- | --- | --- | --- |
| LAX-STARTER | 2 cores / 2 GB | 40 GB NVMe | 2 Gbps, 5 TB | **$200/yr** (list $240) | [ Order LAX-STARTER](https://sixtynet.net/vps-hosting?aff=39) |
| LAX-MEDIUM | 8 cores / 8 GB | 160 GB NVMe | 10 Gbps, 20 TB | **$800/yr** (list $960) | [ Order LAX-MEDIUM](https://sixtynet.net/vps-hosting?aff=39) |
| LAX-LARGE | 8 cores / 16 GB | 320 GB NVMe | 10 Gbps, 40 TB | **$1,600/yr** (list $1,920) | [ Order LAX-LARGE](https://sixtynet.net/vps-hosting?aff=39) |
| LAX Storage 500 GB | 4 cores / 4 GB | 300 GB + 200 GB bonus, RAID 10 | 10 Gbps, 10 TB | Shown at checkout | [ Order the 500 GB storage plan](https://sixtynet.net/vps-hosting?aff=39) |
| LAX Storage 1 TB | 8 cores / 8 GB | 700 GB + 300 GB bonus, RAID 10 | 10 Gbps, 15 TB | Shown at checkout | [ Order the 1 TB storage plan](https://sixtynet.net/vps-hosting?aff=39) |

The jump from MEDIUM to LARGE costs $800 a year and buys double the RAM, double the storage and double the traffic at the same 8 cores. If your workload is a database or a game server that keeps more in memory than on disk, that upgrade is worth it. If it is a website, MEDIUM already has more headroom than most small operations use in a year.

## The cheaper SixtyNet plans that cannot host a public website

SixtyNet's homepage pushes residential IP VPS hard, and those plans cost less: **$25/month** for 2 cores and 2 GB, or **$260/year** on the annual deal, with 5 TB of traffic. They look like a better version of the same thing.

They are not, for this purpose. Residential plans have ports 80 and 443 closed because of IP risk control, and SixtyNet states that on the plan page. No public website, no HTTPS storefront, no API on standard ports. They exist for social accounts, scrapers and ad verification, where the point is looking like a home connection rather than a rack.

Two more things on that page worth knowing: the residential range includes AS9929 China-optimized variants, and refunds on those go to account balance rather than back to your card. If you want a normal public server, stay on LAX.

## What "anti-DDoS" actually buys you: three numbers to ask for

Provider marketing mixes three different measurements, and comparing them directly is how people end up disappointed.

**Per-service scrubbing capacity.** This is the number that matters. One Los Angeles host states plainly that every service includes 10 Gbps / 30 Mpps of filtering. That is a per-server figure you can plan against. Ask for yours in Gbps and in packets per second, because a 2 Gbps volumetric flood and a 20 Mpps SYN flood stress completely different parts of the filter.

**Network-wide capacity.** When a provider advertises "5 Tbps of mitigation capacity," that is the total across every scrubbing center they can reach, shared by every customer. It says something about the operator's size and nothing about your ceiling.

**Regional quotas.** Some plans split protection into a China quota and a global quota, for example 50G China plus 1600G global. Useful if your users are in mainland China, confusing everywhere else.

SixtyNet's plan page lists "DDoS Protection" as a line item with no capacity figure attached, and third-party write-ups of the LAX line put absorption at over 1,000 Gbps without citing a source. Treat that as unconfirmed. Ask support for the per-IP scrubbing ceiling, the Mpps limit, and whether protection is always-on or kicks in after detection. Get it in a ticket so you have it in writing.

The second question is where the cleaning happens. Inline filtering inside the same Los Angeles facility keeps your routes unchanged. Hauling traffic to an overseas scrubbing center and injecting it back adds a round trip to every packet, which is why one LA provider's own description of its "overseas scrubbing center" is a detail worth reading twice. SixtyNet runs one data center in Los Angeles, which makes local inline filtering the likely setup, but the site does not say so explicitly. 👉 [Open the LAX plan page and check the protection line on the plan you want](https://sixtynet.net/vps-hosting?aff=39)

Third: over-limit behavior. Blackhole (traffic dropped, server unreachable) and rate-limit (traffic slowed, server slow) feel very different at 2 a.m. Ask which one applies.

## What a year actually costs, and the 3-day clock

Take LAX-STARTER. The list figure is $240 and the annual price is $200, which is the 12-month total at the monthly rate minus 17%. Prepaying a year saves you roughly two months of service. Renewal at the same $200 keeps that saving; if the annual discount lapses, you are back at $240.

The refund window is the part to plan around. A third-party write-up of SixtyNet reports a **3-day money-back window**, well short of the 30 days most hosts offer. Whether that is current policy is worth confirming before you pay, but if it is accurate, your testing has to happen in the first 72 hours: deploy the site, run a load test, check the port speeds, open a ticket to ask the filtering questions above, and decide. Do not plan to "try it for a couple of weeks."

## When you need bare metal instead

A VPS with 2 GB of RAM will not run a busy game server or a heavy database, and no amount of filtering fixes that. For reference, here is what actual Los Angeles bare metal with always-on filtering costs from two providers whose pages I could check:

| Provider | Los Angeles hardware | Filtering | Price | Billing |
| --- | --- | --- | --- | --- |
| ServerSide | 2× Xeon Gold 6248 (40 cores), 128 GB DDR4, 2× 1.92 TB NVMe, 100 TB at 2× 10 Gbps | Corero, inline and always-on for every LA server, included | $360/mo | Monthly |
| ServerSide | Ryzen 9 9950X (16 cores), 192 GB DDR5, 1.92 TB NVMe, 50 TB at 2× 10 Gbps | Same | $415/mo | Monthly |
| Dedicated.com | Xeon or Ryzen, 4 to 36 cores, up to 256 GB RAM, 1 or 10 Gbps uplinks | Corero SmartWall inline, 10 Gbps / 30 Mpps free with every service | From $36/mo (base configs) | Month to month, no contract |

That $360 figure is roughly 21 months of LAX-STARTER. The comparison is not Sixtynet versus ServerSide; it is "do I need a chassis or do I need a server that stays up." A $200/year filtered VPS beats a $360/month bare-metal box you cannot afford to keep.

Dedicated.com's from-$36 pricing is entry-level hardware, so do not read it as a like-for-like alternative to the $360 configs above. Both are useful as anchors: real dedicated hardware in Los Angeles with real filtering starts in the low hundreds per month, not the low tens.

## Why Los Angeles, and the China question

Los Angeles is where transpacific cables land on the US side, and the downtown carrier buildings a few blocks from One Wilshire hold the peering that makes LA the shortest US path to Tokyo, Seoul, Sydney and Singapore. For an audience split between California and East Asia, LA is usually the right single location.

SixtyNet's LAX plans specify a "premium network" without a China route claim. If mainland China latency is your main problem, the plan that speaks to it directly is SixtyNet's **Los Angeles China Unicom Premium** option: AS9929, a free BGP session, 100M base with 3× burst and 95th-percentile billing, at $2,500/year. That is a different product at a different price, and its page does not advertise DDoS protection the way LAX does. Confirm coverage before switching a China-facing site onto it.

## FAQ

**Is SixtyNet's LAX plan a dedicated server?**
No. It is a VPS. SixtyNet sells no bare-metal servers, and runs one data center, in Los Angeles.

**How much DDoS protection do I get?**
Not published per plan. Ask for the Gbps and Mpps ceiling, whether it is always-on, and what happens past the limit.

**Can I pay monthly?**
LAX prices are quoted annually. The $240 list price on LAX-STARTER is the 12-month cost at the monthly rate, so monthly billing exists at a higher effective rate. Residential plans are quoted monthly at $25, $45, $85 and $165.

**How fast is delivery?**
Not stated on the plan page. Ask before you buy if you are migrating under attack.

**Is there a European or Asian location?**
No. Los Angeles only.

**Can I get a refund?**
A third-party write-up reports 3 days, and the AS9929 residential variants refund to account balance. Verify both at checkout.

## Which one to order

- Blog, small store, panel or a game server under 32 slots: **LAX-STARTER at $200/year.** Nothing above it earns its price for that workload.
- Several sites, a database that lives in RAM, or a 10 Gbps port you actually saturate: **LAX-MEDIUM at $800/year.** LARGE only if you need the 16 GB and 40 TB.
- Backups, media libraries, log retention: the **RAID-10 storage variants**, not the general plans.
- Real bare metal with dual 10 Gbps and 100 TB: SixtyNet is not the vendor. Budget $360/month and up elsewhere.
- Mainland China users first, filtering second: the AS9929 China Unicom plan, after confirming DDoS coverage.

Before you pay, get three answers in writing: the per-IP scrubbing ceiling in Gbps and Mpps, whether filtering is inline in Los Angeles and always-on, and the exact refund window. Then start small, because the cheapest plan and the most expensive one run the same filter.

👉 [Start with LAX-STARTER at $200/year on the SixtyNet LAX order page](https://sixtynet.net/vps-hosting?aff=39)
