# dmit hosting: How Pro, Eyeball and Tier 1 Routes Differ, and Which Los Angeles, Hong Kong or Tokyo Plan Is Worth Paying For

Open the DMIT order page for the first time and you will spend a while staring at it. Three network profiles, three locations, several hardware generations, and a price range that runs from $6.90 a month to somewhere near $800. The plan names (TINY, Pocket, STARTER, MINI, MICRO, MEDIUM, LARGE, GIANT) repeat across every combination, so two plans with nearly identical names can differ in price by a factor of ten.

The name that trips people up is not the plan size. It is the letter pair in the middle. `LAX.AS3.Pro.TINY` and `LAX.AS3.T1.TINY` look like relatives; one costs $10.90 a month and the other $6.90, and the hardware is the same. What you are actually buying is the route your packets take back to whichever networks your users sit on. Get that wrong and no amount of extra RAM fixes it.

Here is how the lineup actually breaks down.

## What DMIT is, briefly

DMIT is a US-registered provider (New York) that has been selling KVM virtual servers since 2017, with data centres in Los Angeles, Hong Kong and Tokyo. Everything runs on AMD EPYC hardware with NVMe/SSD storage, and the company's reputation in hosting circles rests on one thing: it sells route quality rather than raw specs per dollar. Most of its capacity sits on China-optimised transit, and community discussion regularly describes DMIT as an upstream supplier of CN2 GIA bandwidth to other well-known brands, including BandwagonHost.

The practical side matters too. You can pay with Alipay, WeChat Pay, PayPal, bank transfer or a credit card, and support handles Chinese. For anyone running a site or service with an audience in mainland China, that combination is the reason DMIT keeps showing up in recommendations despite prices that are two to five times what a generic US VPS costs.

## Route profile is the only decision that really matters

Pick the network first, then the plan size, then the location. In that order.

| Profile | What the routing is | Suits | Relative price |
| --- | --- | --- | --- |
| Premium (`.Pro`) | Tier 1 + DMIT's own backbone + China Telecom CN2 GIA | Sites and apps with mainland China users where peak-hour stability is non-negotiable | Highest |
| Eyeball (`.EB`) | CMIN2 / CMI and similar best-effort China optimisation, no dedicated premium tier | Budget-conscious projects that still want better-than-plain routing to China | Middle |
| Tier 1 (`.T1`) | Straight international BGP, no China-specific routing | International-only traffic, backups, CI runners, relay nodes | Lowest |

A short translation of the jargon, because the abbreviations get thrown around without explanation. CN2 GIA is China Telecom's premium international transit product, carried on AS4809, and it is the reason mainland users experience stable latency during the evening peak when ordinary transit congests. CMIN2 is China Mobile's comparable international network, which has improved a lot in recent years and performs well for mobile users specifically. Tier 1 means none of that: you get good international peering and full bandwidth, but a mainland visitor may route the long way around.

The latency gap is real and worth planning around. Hong Kong Premium sits somewhere in the 20 to 50 ms range for mainland users. Los Angeles Premium typically lands around 140 to 160 ms. Tokyo falls between the two. If your users are in China and the app is interactive, Hong Kong's physical distance is doing most of the work before any routing magic applies.

## Hardware generations explain the price swings

Two plans with identical specs can be priced differently because they sit on different hardware generations.

- **AS3** uses AMD EPYC 7003 series. It is the generation that has been restocked repeatedly through recent months, and it is currently the cheapest way into any DMIT line.
- **AN4** uses EPYC 9004. Mostly retired on the Los Angeles side, with stock that has been drying up.
- **AN5** uses EPYC 9005, the newest platform, with the higher price tag to match.

For ordinary workloads the difference between 7003 and 9005 is hard to notice, while the price difference is very noticeable. DMIT itself notes that the LAX AS3 platform is still in an optimisation phase and that disk performance and SLA guarantees may trail those of the more mature platforms. If you are deploying something important, that caveat deserves a second read.

## Los Angeles plans and prices

All three profiles are sold in LAX. Flow is counted in both directions on Premium and Eyeball plans, which is worth remembering when you size a plan.

### LAX Premium (CN2 GIA)

| Plan | vCPU / RAM / SSD | Traffic @ Port | Overage | Price | Order |
| --- | --- | --- | --- | --- | --- |
| Pro.TINY | 1 / 2 GB / 20 GB | 1 TB @ 1 Gbps | 4 Mbps unlimited | $10.90/mo | [ Order LAX Pro TINY](https://www.dmit.io/cart.php?region=los-angeles&generation=as3&network=premium&product=lax.as3.pro.tiny&aff=12046) |
| Pro.Pocket | 2 / 2 GB / 40 GB | 1.5 TB @ 4 Gbps | 4 Mbps unlimited | $16.90/mo | [ Order LAX Pro Pocket](https://www.dmit.io/cart.php?region=los-angeles&generation=as3&network=premium&product=lax.as3.pro.pocket&aff=12046) |
| Pro.STARTER | 2 / 2 GB / 80 GB | 3 TB @ 10 Gbps | 4 Mbps unlimited | $34.90/mo | [ Order LAX Pro STARTER](https://www.dmit.io/cart.php?region=los-angeles&generation=as3&network=premium&product=lax.as3.pro.starter&aff=12046) |
| Pro.MINI | 4 / 4 GB / 80 GB | 5 TB @ 10 Gbps | 8 Mbps unlimited | $62.90/mo | [ Order LAX Pro MINI](https://www.dmit.io/cart.php?region=los-angeles&generation=as3&network=premium&product=lax.as3.pro.mini&aff=12046) |
| Pro.MICRO | 4 / 4 GB / 160 GB | 7 TB @ 10 Gbps | 8 Mbps unlimited | $87.90/mo | [ Order LAX Pro MICRO](https://www.dmit.io/cart.php?region=los-angeles&generation=as3&network=premium&product=lax.as3.pro.micro&aff=12046) |
| Pro.MEDIUM | 6 / 8 GB / 160 GB | 14 TB @ 10 Gbps | 10 Mbps unlimited | $199.90/mo | [ Order LAX Pro MEDIUM](https://www.dmit.io/cart.php?region=los-angeles&generation=as3&network=premium&product=lax.as3.pro.medium&aff=12046) |

### LAX Eyeball (CMIN2)

| Plan | vCPU / RAM / SSD | Traffic @ Port | Overage | Price | Order |
| --- | --- | --- | --- | --- | --- |
| EB.TINY | 1 / 2 GB / 20 GB | 1.5 TB @ 2 Gbps | 4 Mbps unlimited | $10.90/mo | [ Order LAX EB TINY](https://www.dmit.io/aff.php?aff=12046) |
| EB.Pocket | 2 / 2 GB / 40 GB | 3 TB @ 4 Gbps | 4 Mbps unlimited | $16.90/mo | [ Order LAX EB Pocket](https://www.dmit.io/aff.php?aff=12046) |
| EB.STARTER | 2 / 2 GB / 80 GB | 5 TB @ 10 Gbps | 4 Mbps unlimited | $34.90/mo | [ Order LAX EB STARTER](https://www.dmit.io/aff.php?aff=12046) |
| EB.MINI | 4 / 4 GB / 80 GB | 10 TB @ 10 Gbps | 8 Mbps unlimited | $62.90/mo | [ Order LAX EB MINI](https://www.dmit.io/aff.php?aff=12046) |
| EB.MICRO | 4 / 4 GB / 160 GB | 14 TB @ 10 Gbps | 8 Mbps unlimited | $87.90/mo | [ Order LAX EB MICRO](https://www.dmit.io/aff.php?aff=12046) |
| EB.MEDIUM | 6 / 8 GB / 160 GB | 30 TB @ 10 Gbps | 10 Mbps unlimited | $199.90/mo | [ Order LAX EB MEDIUM](https://www.dmit.io/aff.php?aff=12046) |

### LAX Tier 1 (international)

| Plan | vCPU / RAM / SSD | Traffic @ Port | Overage | Price | Order |
| --- | --- | --- | --- | --- | --- |
| T1.WEE | 1 / 1 GB / 20 GB | 1 TB @ 4 Gbps | 100 Mbps unlimited | $36.90/year | [ Order LAX T1 WEE](https://www.dmit.io/aff.php?aff=12046) |
| T1.TINY | 1 / 1 GB / 20 GB | 2 TB @ 4 Gbps | 200 Mbps unlimited | $6.90/mo | [ Order LAX T1 TINY](https://www.dmit.io/aff.php?aff=12046) |
| T1.STARTER | 2 / 2 GB / 40 GB | 4 TB @ 10 Gbps | 200 Mbps unlimited | $12.90/mo | [ Order LAX T1 STARTER](https://www.dmit.io/aff.php?aff=12046) |
| T1.MINI | 2 / 4 GB / 80 GB | 8 TB @ 10 Gbps | 200 Mbps unlimited | $21.90/mo | [ Order LAX T1 MINI](https://www.dmit.io/aff.php?aff=12046) |
| T1.MICRO | 4 / 4 GB / 120 GB | 16 TB @ 10 Gbps | 500 Mbps unlimited | $32.90/mo | [ Order LAX T1 MICRO](https://www.dmit.io/aff.php?aff=12046) |

The $36.90 annual WEE plan is the cheapest thing DMIT sells and it disappears from stock constantly. It is also the plan people most often buy by mistake, assuming the low price means it will be fast into China. It will not be.

## Hong Kong plans and prices

Hong Kong Premium is the most expensive line in the catalogue and the one with the best mainland latency. Bandwidth is capped at 1 Gbps across the Premium range, which is unusual next to the 10 Gbps ports on the US lines, but port speed is not what you are paying for here.

### HKG Premium (CN2 GIA)

| Plan | vCPU / RAM / SSD | Traffic @ Port | Price | Order |
| --- | --- | --- | --- | --- |
| Pro.TINY | 1 / 1 GB / 20 GB | 500 GB @ 1 Gbps | $39.90/mo | [ Order HKG Pro TINY](https://www.dmit.io/aff.php?aff=12046) |
| Pro.STARTER | 1 / 2 GB / 40 GB | 1 TB @ 1 Gbps | $79.90/mo | [ Order HKG Pro STARTER](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MINI | 2 / 2 GB / 60 GB | 1.5 TB @ 1 Gbps | $119.90/mo | [ Order HKG Pro MINI](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MICRO | 4 / 4 GB / 80 GB | 2 TB @ 1 Gbps | $159.90/mo | [ Order HKG Pro MICRO](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MEDIUM | 4 / 8 GB / 160 GB | 2.5 TB @ 1 Gbps | $179.90/mo | [ Order HKG Pro MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| Pro.LARGE | 8 / 16 GB / 320 GB | 3 TB @ 1 Gbps | $239.90/mo | [ Order HKG Pro LARGE](https://www.dmit.io/aff.php?aff=12046) |
| Pro.GIANT | 8 / 24 GB / 640 GB | 6 TB @ 1 Gbps | $499.90/mo | [ Order HKG Pro GIANT](https://www.dmit.io/aff.php?aff=12046) |

### HKG Eyeball (CMI)

| Plan | vCPU / RAM / SSD | Traffic @ Port | Price | Order |
| --- | --- | --- | --- | --- |
| EBv2.TINY | 1 / 1 GB / 20 GB | 1 TB @ 1 Gbps | $29.90/mo | [ Order HKG EB TINY](https://www.dmit.io/aff.php?aff=12046) |
| EBv2.STARTER | 1 / 2 GB / 40 GB | 2 TB @ 2 Gbps | $59.90/mo | [ Order HKG EB STARTER](https://www.dmit.io/aff.php?aff=12046) |
| EBv2.MINI | 2 / 2 GB / 60 GB | 3 TB @ 2 Gbps | $89.90/mo | [ Order HKG EB MINI](https://www.dmit.io/aff.php?aff=12046) |
| EBv2.MICRO | 4 / 4 GB / 80 GB | 4 TB @ 4 Gbps | $129.90/mo | [ Order HKG EB MICRO](https://www.dmit.io/aff.php?aff=12046) |
| EBv2.MEDIUM | 4 / 8 GB / 160 GB | 6 TB @ 4 Gbps | $199.90/mo | [ Order HKG EB MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| EBv2.LARGE | 8 / 16 GB / 320 GB | 12 TB @ 4 Gbps | $389.90/mo | [ Order HKG EB LARGE](https://www.dmit.io/aff.php?aff=12046) |
| EBv2.GIANT | 8 / 24 GB / 640 GB | 24 TB @ 4 Gbps | $789.90/mo | [ Order HKG EB GIANT](https://www.dmit.io/aff.php?aff=12046) |

### HKG Tier 1 (international)

| Plan | vCPU / RAM / SSD | Traffic @ Port | Overage | Price | Order |
| --- | --- | --- | --- | --- | --- |
| T1.WEE | 1 / 1 GB / 20 GB | 1 TB @ 4 Gbps | 50 Mbps unlimited | $36.90/year | [ Order HKG T1 WEE](https://www.dmit.io/aff.php?aff=12046) |
| T1.TINY | 1 / 1 GB / 20 GB | 2 TB @ 4 Gbps | 100 Mbps unlimited | $6.90/mo | [ Order HKG T1 TINY](https://www.dmit.io/aff.php?aff=12046) |
| T1.STARTER | 1 / 2 GB / 40 GB | 4 TB @ 10 Gbps | 100 Mbps unlimited | $12.90/mo | [ Order HKG T1 STARTER](https://www.dmit.io/aff.php?aff=12046) |
| T1.MINI | 2 / 2 GB / 60 GB | 8 TB @ 10 Gbps | 100 Mbps unlimited | $21.90/mo | [ Order HKG T1 MINI](https://www.dmit.io/aff.php?aff=12046) |
| T1.MICRO | 4 / 4 GB / 80 GB | 16 TB @ 10 Gbps | 200 Mbps unlimited | $32.90/mo | [ Order HKG T1 MICRO](https://www.dmit.io/aff.php?aff=12046) |
| T1.MEDIUM | 4 / 8 GB / 160 GB | 32 TB @ 10 Gbps | 200 Mbps unlimited | $49.90/mo | [ Order HKG T1 MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| T1.LARGE | 8 / 16 GB / 320 GB | 64 TB @ 10 Gbps | 500 Mbps unlimited | $99.90/mo | [ Order HKG T1 LARGE](https://www.dmit.io/aff.php?aff=12046) |
| T1.GIANT | 8 / 24 GB / 640 GB | 128 TB @ 10 Gbps | 1 Gbps unlimited | $199.90/mo | [ Order HKG T1 GIANT](https://www.dmit.io/aff.php?aff=12046) |

One caveat specific to Hong Kong T1: it uses RETN for Europe-facing routing, which is genuinely useful if your users are in Europe. If your users are on China Telecom, the route can be worse than a Los Angeles box. This is the most common expensive mistake in the whole catalogue.

## Tokyo plans and prices

| Plan | vCPU / RAM / SSD | Traffic @ Port | Overage | Price | Order |
| --- | --- | --- | --- | --- | --- |
| Pro.TINY | 1 / 1 GB / 20 GB | 500 GB @ 1 Gbps | — | $21.90/mo | [ Order TYO Pro TINY](https://www.dmit.io/aff.php?aff=12046) |
| Pro.STARTER | 1 / 2 GB / 40 GB | 1 TB @ 1 Gbps | — | $39.90/mo | [ Order TYO Pro STARTER](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MINI | 2 / 2 GB / 60 GB | 2 TB @ 1 Gbps | — | $79.90/mo | [ Order TYO Pro MINI](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MICRO | 4 / 4 GB / 80 GB | 4 TB @ 1 Gbps | — | $159.90/mo | [ Order TYO Pro MICRO](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MEDIUM | 4 / 8 GB / 160 GB | 5 TB @ 1 Gbps | — | $259.90/mo | [ Order TYO Pro MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| Pro.LARGE | 8 / 16 GB / 320 GB | 8 TB @ 1 Gbps | — | $429.90/mo | [ Order TYO Pro LARGE](https://www.dmit.io/aff.php?aff=12046) |
| Pro.GIANT | 8 / 24 GB / 640 GB | 15 TB @ 1 Gbps | — | $799.90/mo | [ Order TYO Pro GIANT](https://www.dmit.io/aff.php?aff=12046) |
| T1.WEE | 1 / 1 GB / 20 GB | 1 TB @ 4 Gbps | 50 Mbps unlimited | $36.90/year | [ Order TYO T1 WEE](https://www.dmit.io/aff.php?aff=12046) |
| T1.TINY | 1 / 1 GB / 20 GB | 2 TB @ 4 Gbps | 100 Mbps unlimited | $6.90/mo | [ Order TYO T1 TINY](https://www.dmit.io/aff.php?aff=12046) |
| T1.STARTER | 1 / 2 GB / 40 GB | 4 TB @ 10 Gbps | 100 Mbps unlimited | $12.90/mo | [ Order TYO T1 STARTER](https://www.dmit.io/aff.php?aff=12046) |
| T1.MINI | 2 / 2 GB / 60 GB | 8 TB @ 10 Gbps | 100 Mbps unlimited | $21.90/mo | [ Order TYO T1 MINI](https://www.dmit.io/aff.php?aff=12046) |
| T1.MICRO | 4 / 4 GB / 80 GB | 16 TB @ 10 Gbps | 200 Mbps unlimited | $32.90/mo | [ Order TYO T1 MICRO](https://www.dmit.io/aff.php?aff=12046) |
| T1.MEDIUM | 4 / 8 GB / 160 GB | 32 TB @ 10 Gbps | 200 Mbps unlimited | $49.90/mo | [ Order TYO T1 MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| T1.LARGE | 8 / 16 GB / 320 GB | 64 TB @ 10 Gbps | 500 Mbps unlimited | $99.90/mo | [ Order TYO T1 LARGE](https://www.dmit.io/aff.php?aff=12046) |
| T1.GIANT | 8 / 24 GB / 640 GB | 128 TB @ 10 Gbps | 1 Gbps unlimited | $199.90/mo | [ Order TYO T1 GIANT](https://www.dmit.io/aff.php?aff=12046) |

Tokyo Eyeball has been reported as discontinued, and availability across the whole Tokyo range is less predictable than Los Angeles. Stock status changes week to week, so treat the table as a map of the product line rather than a live inventory list.

## The details the price tags leave out

**Traffic is metered in both directions** on Premium and Eyeball plans, and Tier 1 counts the higher of upload or download. A 1 TB quota sounds generous until you remember a busy WordPress site with image traffic can burn through it. Plan for roughly half the listed figure if your workload is symmetric.

**Going over quota throttles you, it does not cut you off.** This is one of DMIT's more sensible policies. Premium plans drop to 4, 8 or 10 Mbps depending on the tier; Tier 1 plans drop to somewhere between 50 Mbps and 1 Gbps. Your site stays up, just slower. For anyone who has had a VPS suspended mid-month by a cheap host, this alone is a reason to care.

**DDoS protection is included at a standard level** on the regular lines, and there is a separate Premium Secure line on the Los Angeles side that adds Cloudflare Magic Transit filtering on the inbound path while keeping CN2 GIA for return traffic. That line exists for a specific problem: sites that get attacked and still need to be fast into China.

**Every plan ships with 1 IPv4 and 1 IPv6 /64.** No auction, no add-on purchase required to get a usable address.

**Maintenance windows are not always emailed ahead of time.** This shows up repeatedly in user reports. Upgrades to host nodes can briefly take a server offline without much warning. If you need written SLA guarantees for a business-critical deployment, that is a genuine drawback to weigh.

**Stock is the real constraint.** The Los Angeles ranges have sold out for extended stretches and restocked in waves, with purchase queues when a restock is popular. If you are shopping on a deadline, buying during a restock matters more than waiting for a better price that may not come.

## Coupon codes: what circulates and what to verify

DMIT runs much of its discounting as built-in annual pricing rather than codes, and some lines get an automatic discount when you choose a longer billing cycle. The codes that circulate most often are line-specific and term-specific:

- `LAX-EB-LAUNCH-NON-MONTHLY-RECURRING-20OFF` for Los Angeles Eyeball plans on quarterly billing or longer, a recurring 20% off
- `202510_HKG_TYO_PRO_20OFF_RECURRING` for Hong Kong and Tokyo Premium on quarterly or longer
- `202510_HKG_TYO_T1_30OFF_RECURRING` for Hong Kong and Tokyo Tier 1 on quarterly or longer, excluding WEE
- `Lite-Annually-Recur-30OFF` and `Lite-Semi-Annually-Recur-20OFF` for Standard-tier plans

Codes in this catalogue expire and rotate. Apply one in the cart and hit the validate button before you pay, because a code that worked last month may simply refuse to apply to the product you have selected. Terms matter: "non-monthly" means monthly billing will not trigger the discount, and "recurring" means the discount applies to renewals too, which is where the real value sits on a multi-year plan.

If you want the current live pricing and any active promotion without hunting through forum posts, 👉 [👉 check DMIT's current plans and offers](https://www.dmit.io/aff.php?aff=12046) is the page that always reflects what is actually in stock.

## Which plan to pick, by situation

- **A personal blog or small site with mainland readers, tight budget.** LAX Eyeball TINY at $10.90/mo with a non-monthly coupon. CMIN2 routing handles mobile users well, and the price sits close to generic hosts.
- **A business site where evening peak performance is the whole point.** LAX Premium or HKG Premium. The CN2 GIA premium is the product you are buying, and Eyeball will not replicate it in the 8pm to 11pm window.
- **Users concentrated in mainland China and the app is interactive.** Hong Kong Premium, even at $39.90 for the smallest plan. Roughly 20 to 50 ms versus 140 to 160 ms changes how an interface feels.
- **International audience, no China traffic at all.** Tier 1. Buying Premium here is money spent on routing your users will never use. The $36.90 annual WEE plan handles a monitoring endpoint or backup node fine.
- **Heavy outbound transfer such as a mirror or download host.** Tier 1 MINI or MICRO, where 8 to 16 TB of monthly traffic costs less than a Premium plan with one fifth of the allowance.

The pattern to notice: the cheapest plan is rarely the right one, and the most expensive plan is rarely necessary. What you are paying for is a route, and picking the wrong route wastes the entire budget.

## Payments, refunds and support

Alipay, WeChat Pay, PayPal, credit cards and bank transfer are all accepted. Alipay is worth choosing if you are unsure about the purchase, since it is the payment route users report as cleanest if you later want a refund. Refunds are handled through a self-service button in the billing tab of the control panel, alongside the usual ticket-based process, and users report multiple-day refund handling rather than instant.

Support is ticket-based with Chinese-language staff. Community reports describe responses as reasonably prompt and DMIT as willing to issue compensation when a node outage affects customers, which is less common among smaller providers than you would hope.

## Questions that come up before buying

**Does the AS3 platform still make sense with AN4 and AN5 available?** For most workloads, yes. EPYC 7003 is not slow, and the AS3 restocks are cheaper and more available. The trade-off is that DMIT describes the AS3 range as still being optimised, with disk performance and SLA possibly below mature platforms.

**Can I use the same account across Los Angeles, Hong Kong and Tokyo?** Yes, they are one product catalogue under one account, and DMIT has enabled private-network data transfer between its locations for cross-region traffic.

**Will a Tier 1 plan be slow for my Chinese visitors?** Measurably slower and less predictable, yes. Mobile users may get acceptable results via CMI, while China Telecom users can see routes that detour through other continents. If mainland experience is a requirement, this is not the tier.

**How often does stock come back?** There is no published schedule. Los Angeles restocks have arrived in waves, sometimes months apart, and the configuration you want may be unavailable when you look.

Worth bookmarking the order page rather than deciding today: 👉 [👉 see what's currently in stock at DMIT](https://www.dmit.io/aff.php?aff=12046). Between the constant restock cycles and the coupon rotation, the lineup you compare this month will not be the lineup available next month.
