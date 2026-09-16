# colocation data: What It Means, How It Works, and How to Pick the Right Colo Facility

If you typed "colocation data" into a search box, you're probably circling one of a few real questions: what a colocation data center actually is, whether it's worth shipping your own hardware to one instead of renting cloud instances, how the pricing works, and how to choose a facility without getting burned. This guide walks through all of that, then grounds it in a concrete provider — DMIT's carrier-neutral colocation in Los Angeles, Hong Kong, and Tokyo — so you can see how the abstract criteria map onto a real offer.

## What a Colocation Data Center Actually Is

A colocation data center (often shortened to "colo") is a facility where you rent physical space, power, cooling, and network connectivity for **your own** servers and networking gear. The provider owns the building, the generators, the HVAC, the security guards, and the uplinks. You own the hardware sitting inside the racks.

That distinction matters. With cloud or VPS hosting, you rent compute that lives on someone else's hardware. With a dedicated server, you rent a whole physical box the provider bought. With colocation, the box is yours — you paid for it, you spec'd it, you control it down to the firmware. The colo just gives it a safe, powered, well-connected place to live.

This model makes sense when you already own specialized hardware, when you need predictable long-term costs that cloud pricing can't offer, or when regulatory and compliance reasons require you to keep full hardware control. It also shows up in hybrid setups: companies keep steady-state workloads on their own colocated gear and burst into the cloud for spikes.

## Colocation vs. Cloud vs. Dedicated: Which One Actually Fits

The three options aren't a ladder where higher is better — they're different trade-offs.

**Cloud / VPS** wins on flexibility and time-to-deploy. You spin instances up in minutes, scale up or down, and pay only for what you use. The trade-off is that variable pricing gets expensive fast at sustained high volume, and you have limited control over the underlying hardware.

**Dedicated servers** give you an entire physical machine to yourself without the capital cost of buying it. Good when you want bare-metal performance without owning hardware, but you're locked into whatever configurations the provider sells, and over years the rental adds up to more than buying would have.

**Colocation** has the highest up-front cost — you buy the servers, ship them, and pay for installation — but the lowest ongoing monthly cost at scale. You can swap parts, run exotic hardware, bring your own IP space via BGP, and tune power and bandwidth to match your real usage instead of a provider's packaged tier.

> If your workload is steady, hardware-intensive, and long-lived, colo usually wins on a multi-year cost basis. If your traffic spikes unpredictably or you need to deploy in 10 minutes, cloud still wins.

## What to Actually Look For in a Colocation Facility

Reading provider spec sheets gets overwhelming fast. The criteria that actually decide whether a colo works for you are narrower than the marketing suggests.

**Location and latency.** Every millisecond costs you something. Pick a facility close to your users or close to the networks and IXes you care about. For APAC-facing traffic, being in Hong Kong or Tokyo — with direct subsea cable paths into China and the rest of Asia — beats routing through a generic US east coast facility even if the latter is cheaper per rack unit.

**Carrier neutrality.** A carrier-neutral datacenter lets you blend multiple transit providers, cross-connect to your own carriers, and reach internet exchanges directly. A single-carrier facility locks you into that provider's routing and pricing. For anything more than a single-server hobby deployment, neutrality is non-negotiable.

**Power redundancy and density.** Look for N+1 (or better) UPS, diesel generator backup, and A/B power feeds so a single utility failure doesn't take you down. Also check the power density per cabinet — modern high-core CPUs and GPU rigs draw more than legacy facilities were built to deliver.

**Cooling.** Precision cooling with hot/cold aisle containment keeps gear within operating range. Under-cooled facilities throttle or fail under sustained load, which is the last thing you want after shipping servers across the Pacific.

**Physical security and compliance.** Multi-factor access control, 24/7 CCTV, on-site guards, and a Tier III-class audit trail. If you're handling regulated data, ask whether the facility has been audited against the relevant framework.

**Remote hands.** This is the one nobody thinks about until they need it. When a drive fails at 3 AM, you want engineers on-site who can reboot, re-seat, swap media, and run visual diagnostics without you flying out. 24/7 ticket-driven remote hands is what turns a colocated box into something you can actually operate remotely.

**Install and rack-and-stack.** Shipping hardware internationally is a pain. A provider that receives your equipment, racks it, cables it, sets up IPMI, powers it on, and sends you photos and documentation removes a whole category of headaches.

**Bandwidth flexibility.** Metered (95th percentile), committed, or flat billing — plus port speed options from 1G to 10G and higher. The right model depends on your traffic profile. Burst-heavy workloads fit 95th percentile; steady high-volume traffic fits committed or flat.

## How Colocation Pricing Is Typically Structured

Colo pricing is quoted by **space × power × bandwidth**, not as a flat "per server" fee the way VPS plans are.

Space is sold by the rack unit (1U, 2U, 4U), by the half cabinet (roughly 20–24U), by the full cabinet (42–48U), or by the private cage for larger deployments. Power is charged either as a fixed amp allocation or metered by actual draw. Bandwidth follows one of the billing models above and is layered on top.

Industry-wide reference ranges (these vary widely by market and facility tier): per-U pricing commonly lands between $50 and $300 per 1U per month; half cabinets run roughly $400–$900; full cabinets run $900–$2,500+. Premium markets — Hong Kong and Tokyo especially — sit at the higher end. Los Angeles is more competitive on power and space cost while still offering excellent APAC routing through subsea cable landings.

Because colo pricing depends on your actual hardware, power draw, bandwidth commit, and contract length, reputable providers quote it custom rather than publishing a flat menu. That's not a red flag; it's how the industry works.

## What DMIT Colocation Brings to the Table

DMIT operates colocation out of three carrier-neutral facilities: **Los Angeles, Hong Kong, and Tokyo**. All three are Tier III-class, audited facilities with N+1 power and cooling, diesel generator backup, A/B power feeds, badge-and-biometric access, 24/7 CCTV, on-site guards, and 24/7 remote hands. The facility-level uptime SLA is 99.99%.

Where DMIT's colo differentiates from a generic colo provider is the **network**. DMIT runs its own backbone with up to 7.6 Tbps of aggregate Tier 1 capacity and, more importantly, holds direct peering with China Telecom (AS4809), China Unicom (AS9929), and China Mobile International (AS58807). On the Premium Network series, traffic also rides China Telecom CN2 GIA — the premium low-latency, low-packet-loss path into Mainland China that most colos can't offer because they don't have the peering relationships.

This matters most when your users are in China or the wider APAC region and you don't want to host inside China itself. Reaching Mainland China from overseas is notoriously bad over standard transit: congested international gateways, peak-hour packet loss, and routing that bounces through random third-country hops. Direct peering plus CN2 GIA is the cleanest workaround short of actually moving hardware into China, which most companies can't or won't do.

For colocation specifically, DMIT offers:

- **Rack Units (1U–4U):** individual servers colocated in shared, secured cabinet space. Best for getting a foothold, edge nodes, or small deployments without committing to a whole cabinet.
- **Half Cabinet:** a lockable half cabinet with dedicated power and bandwidth. Best for mid-size clusters and storage that need isolation and room to grow within the cabinet.
- **Full Cabinet:** a full cabinet with committed power and bandwidth, suited to dense, high-power racks. Private cages are available on request for larger deployments.

All three include rack-and-stack on arrival, 24/7 remote hands, cross-connects to carriers and IXes, and flexible port/billing models (1G/10G/higher, 95th percentile or committed or flat). Power is available as metered or fixed depending on your usage profile.

Pricing for colocation is quoted per deployment based on location, footprint, power draw, and bandwidth — DMIT does not publish a flat colo price list, consistent with how carrier-neutral colo is sold industry-wide. The fastest way to get real numbers is to tell them your hardware, power, bandwidth, and preferred location and have the team build a tailored quote.

## DMIT Colocation Space Options at a Glance

The table below maps the three colocation tiers DMIT offers across their LAX, HKG, and TYO facilities. Because colo pricing is custom-quoted per deployment, the cost column reflects how pricing is determined rather than a flat number.

| Space Option | Footprint | Best For | Power & Network | Pricing | Get a Quote |
| --- | --- | --- | --- | --- | --- |
| Rack Units (1U–4U) | Shared, secured cabinet space by the U | Single servers, edge nodes, small deployments, pay-as-you-grow | Metered or fixed power; 1G/10G port options; 95th percentile, committed, or flat billing | Custom quote based on U count, power draw, bandwidth, and location | [Request a colocation quote](https://bit.ly/DmiT) |
| Half Cabinet | Lockable half cabinet with dedicated power and bandwidth | Mid-size clusters, storage needing isolation, room to scale within the cabinet | Dedicated power and bandwidth; cross-connects to carriers and IX | Custom quote based on power commit, bandwidth, and location | [Request a colocation quote](https://bit.ly/DmiT) |
| Full Cabinet | Full cabinet with committed power and bandwidth | High-density, high-power racks; private cages available on request | Committed power and bandwidth; cross-connects; BGP and BYOIP available | Custom quote based on power density, bandwidth commit, contract length, and location | [Request a colocation quote](https://bit.ly/DmiT) |

If you're not sure where to start, the 1U–4U tier is the lowest-commitment way in — you get the same facility, power, and network quality as a full cabinet customer, just with less space and a smaller power commit.

## Beyond Colo: When DMIT's Other Tiers Make More Sense

Colocation isn't always the right answer even when DMIT is the right provider. The same network and facilities back their cloud instances and bare metal servers, so it's worth knowing where the lines are.

**If you don't own hardware yet,** DMIT's cloud instances run on the same AMD EPYC platforms (AN5/Zen 5, AN4/Zen 4, AS3/Zen 3) and the same Premium / Eyeball / Tier 1 network series. Entry-level cloud pricing starts at $10.90/month for a TINY instance (1 vCore, 2GB RAM, 20GB SSD, 1TB transfer, 1Gbps) and scales up through Pocket ($16.90), STARTER ($34.90), MINI ($62.90), MICRO ($87.90), and MEDIUM ($199.90). That's the same China-optimized network at a fraction of what colocating your own box would cost you up front.

**If you need bare metal but don't want to buy it,** DMIT's dedicated server tier gives you single-tenant physical hardware — up to 128-core / 256-thread AMD EPYC, DDR4/DDR5 ECC, full NVMe, 10Gbps uplinks, IPMI access, custom bandwidth and BGP — built to spec and quoted per configuration. That's the middle ground: dedicated hardware performance without owning it, with the same colo-grade facilities and network underneath.

**Colocation is the move when** you already own (or plan to buy) specialized hardware, you want long-term cost predictability, you need BYOIP or BGP control, or you're running hardware configurations the provider's standard dedicated menu doesn't cover.

## Practical Checklist Before You Ship Hardware to a Colo

Once you've picked a facility, the actual onboarding goes a lot smoother if you've nailed down a few things ahead of time.

1. **Know your power draw.** Check the wattage on every server and switch you're sending. Colo is priced partly on power, and underestimating draw is the single most common reason quotes come back higher than expected.
2. **Know your bandwidth profile.** Steady traffic? Bursty traffic? China-facing or global? Pick the right billing model (95th percentile for bursty, committed or flat for steady) and the right network tier. For China-facing traffic, premium CN2 GIA routing is worth the premium if your users actually feel the latency difference.
3. **Pick the right location.** Los Angeles for cost-efficient APAC routing via subsea landings, Hong Kong for the lowest latency into South China, Tokyo for North Asia and high-density compute.
4. **Prepare IPMI / out-of-band access.** Make sure IPMI is configured before shipping so you can manage the box remotely the moment it's racked. DMIT's rack-and-stack includes IPMI setup, but having it pre-configured on your side speeds things up.
5. **Document the hardware.** Serial numbers, MAC addresses, RAID layouts, and BIOS settings. You'll need this for support tickets and for your own asset tracking.
6. **Plan the cross-connects.** If you're bringing your own carrier or peering at an IX in the same facility, list the cross-connects you need up front so they're provisioned with the install.
7. **Understand the SLA and refund terms.** DMIT's facility-level SLA is 99.99%. Service-level SLA credits apply below 99% uptime per their terms. Know what's covered before you sign.

## Common Questions About Colocation Data

**Is colocation cheaper than cloud?** It depends on the time horizon and workload. Cloud is cheaper for short-term, bursty, or unpredictable workloads. Colocation is typically cheaper over 2–3+ years for steady, high-utilization workloads — but only after you've absorbed the up-front hardware and install cost.

**Do I need to be in the same country as the colo?** No. The whole point of remote hands is that you don't need to be on-site. DMIT's 24/7 remote hands covers reboots, part swaps, media handling, and visual diagnostics from anywhere via ticket.

**Can I bring my own IP addresses?** On DMIT colocation, yes — BGP sessions and BYOIP announcements are supported. The same applies on their bare metal tier.

**What happens if my hardware breaks?** You ship replacement parts and DMIT's on-site engineers handle the swap. For critical workloads, keep spare cold parts on-site at the facility so the swap happens in minutes instead of days.

**How is colocation billed?** Typically monthly, based on space (U or cabinet), power (amps or kW, fixed or metered), and bandwidth (95th percentile, committed, or flat). DMIT quotes each deployment custom based on these variables.

**Is Hong Kong colo worth the premium over Los Angeles?** If your users are in Mainland China or South China specifically, yes — Hong Kong to Shenzhen latency is dramatically lower than routing through LA even on premium CN2 GIA. If your users are globally distributed or mostly in the Americas, LA's lower cost and still-excellent APAC routing is usually the better fit.

## The Bottom Line

Colocation data centers aren't a one-size-fits-all solution, but they're the right fit when you need hardware control, predictable long-term costs, and serious network quality. The decision comes down to whether you own (or plan to own) hardware, how much you value full control over the stack, and whether the up-front capital cost makes sense against your multi-year cloud bill.

DMIT's colocation stands out less on raw space pricing — which is custom-quoted like every carrier-neutral colo — and more on the **network underneath**: direct peering with all three major Chinese carriers, CN2 GIA premium routing, multi-Tbps Tier 1 capacity, and three Pacific Rim locations that actually matter for APAC traffic. The facility specs — Tier III-class, N+1 power, 24/7 remote hands, rack-and-stack on arrival — are table stakes done right.

If colocation is on your radar and APAC connectivity is part of the picture, the fastest way to get real numbers is to 👉 [request a colocation quote from DMIT](https://bit.ly/DmiT) with your hardware list, power draw, bandwidth needs, and preferred location. The team will come back with a tailored plan and price.

If you're not ready to colocate your own hardware yet, the same network and facilities are available through DMIT's cloud instances starting at $10.90/month and bare metal servers quoted per configuration — 👉 [explore DMIT's hosting plans](https://bit.ly/DmiT) to see which tier actually fits where you are right now.
