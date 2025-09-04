# FleetGlue Market Pack — 6 Slides (Draft with placeholders)

---
# 1) US Manufacturing TAM & Segmentation

**Scope**: NAICS 31–33 (Manufacturing)

- **Firms vs. establishments (directional)**  
  - ~240,000 **firms** (accounts to target)  
  - ~500,000–600,000 **establishments** (sites/plants)  
  - _Replace with latest **Census CBP 20XX** counts_
- **Revenue segmentation (replace with verified CBP/Econ Census):**  
  - **< $10M:** ~70–85% of firms (long tail)  
  - **$10–$100M:** ~10–20%  
  - **$100M–$1B:** ~3–8%  
  - **> $1B:** <2%
- **Account tiers to prioritize:**  
  - **Tier A ($10–$100M):** fastest wins; high pain; limited in‑house dev  
  - **Tier B (>$100M):** lighthouse logos; pilot first; interop + auditability  
  - **Tier C (<$10M):** via SI partners; simplified SKUs
- **Source placeholders:** Census **CBP 20XX**, Economic Census/ASMF, BLS QCEW

---
# 2) Fast-Growth Verticals (Next 3–5 Years)

- **Biopharma/Diagnostics**  
  - *Drivers:* validation, serialization, continuous manufacturing  
  - *Buying criteria:* auditability, change control, vendor‑agnostic interop
- **Defense/Aerospace**  
  - *Drivers:* rearm, space, reshoring  
  - *Buying criteria:* safety, security, mixed‑brand ops, traceability
- **EV/Batteries & Electronics**  
  - *Drivers:* capex boom, rapid line changes  
  - *Buying criteria:* no‑downtime upgrades, fleet coordination, MTTR
- **Construction Materials**  
  - *Drivers:* demand spikes, brownfield automation  
  - *Buying criteria:* simple retrofit, cross‑system workflows
- **Food & Beverage/CPG**  
  - *Drivers:* SKU proliferation, labor gaps  
  - *Buying criteria:* sanitation windows, exception handling, throughput
- **Source placeholders:** BLS/BEA growth by NAICS (20XX), sector reports

---
# 3A) How many US manufacturers use advanced automation?

## Definition to use on slide
**Robots or machine vision in production plus coordination beyond a single PLC cell.**

---

## Sizing method (show, don’t guess)
- Pull **Census CBP**: count manufacturing establishments by NAICS 31–33 and size band (1–99, 100–499, 500+).  
- Apply adoption rates by vertical and size band using recent surveys (placeholders below). Build low / mid / high scenarios.  
- Cross-check with plant maturity ladder (Stage 1–4) from interviews or surveys.  

---

## Output (fill placeholders once sourced)
- Estimated plants with advanced automation: **[LOW]–[MID]–[HIGH]**  
- Share of all manufacturing establishments: **[x%]–[y%]–[z%]**  
- Concentration: auto, electronics, F&B, 3PL drive most of the count  

---

## Why FleetGlue cares
This is the **top of funnel for orchestration.** Prioritize Stage 2–4 plants and regulated environments.  

---

## Sources to plug in
- U.S. Census CBP 20XX  
- MHI/NAM/Deloitte adoption surveys 20XX  
- Internal discovery notes  

---

# 3B) How many US manufacturers use robotics specifically?

## Definition to use on slide
**At least one industrial arm, cobot, or AMR in production or material flow.**

---

## Sizing method (transparent math)
- Pull **IFR United States:** installed base and density.  
- Estimate robots-per-plant by vertical and size band to convert installed base into a count of plants with ≥1 robot.  
- Bound by **Census CBP** establishment counts to keep ratios realistic.  
- Break out **AMR vs. fixed robots** with A3 trend data and vendor case studies.  

---

## Output (placeholders)
- Plants with ≥1 robot: **[LOW]–[MID]–[HIGH]**  
- Vertical split: auto [x%], electronics [y%], F&B [z%], other [w%]  
- AMR production users: **[LOW]–[MID]–[HIGH]** plants  

---

## Why FleetGlue cares
These are **mixed-brand, multi-system sites** where cross-device workflows and audit logs matter.  

---

## Sources to plug in
- IFR World Robotics 20XX  
- A3 20XX  
- Vendor case studies  
- U.S. Census CBP 20XX  

---

# 3C) AMR: Integration & Scaling

## Integration pain (go-live)
- WMS/MES/ERP adapters & order mapping  
- Doors/conveyors/elevators/chargers handoffs  
- RF coverage & roaming; map/version control  
- Safety zones & traffic rules across brands  

---

## Scaling pain (post-pilot)
- Mixed fleets (multi-brand/model)  
- Mission priority, exception handling, queueing  
- Battery/charger scheduling; congestion  
- Change control, validation, auditability  
- Upgrades with zero planned downtime  

---

## FleetGlue fit
- **Vendor-agnostic orchestration & policy engine**  
- **Reusable adapters/blocks for handoffs**  
- **Signed audit logs; safe changeovers**  
- **Remote ops & no-downtime upgrades**  

---

## Pilot proof metrics
- Time to first value  
- Mission success rate  
- Exceptions auto-resolved  
- Changeover time delta  
- Count of no-downtime upgrades  
- Signed audit logs accepted by QA/compliance  

---

## Source placeholders
- A3 AMR reports 20XX  
- Vendor case studies  
- Customer interviews  
- Internal pilots  

---
# 5) AMR Pain Map → FleetGlue Fit

| AMR Pain Point            | What Plants Experience                                  | FleetGlue Fit (Fortuna)                                      |
|---------------------------|----------------------------------------------------------|--------------------------------------------------------------|
| WMS/MES/ERP interop       | Custom glue, brittle APIs, long lead times               | Prebuilt adapters + reusable blocks; **no‑downtime** cutover |
| Cross‑brand workflows     | AMRs + conveyors/doors/elevators don’t coordinate        | Vendor‑agnostic orchestration; cross‑system mission logic    |
| Traffic & safety rules    | Congestion, near‑misses, inconsistent policies           | Central policy engine + **signed audit logs**                |
| Maps/versioning/changes   | Layout changes break missions; rollback risk             | Versioned maps & workflows; sandbox + safe deploy            |
| Exception handling        | Stalls on edge cases; manual operator fixes              | If‑then automations; escalation; **MTTR** dashboards         |
| Scaling sites             | Each site re‑implements from scratch                     | Blocks/playbooks reusable; templated rollouts                |

---
# 4) SI Business Model (Revenue, Pros/Cons) & FleetGlue Angle

- **Revenue mix:** Project engineering (T&M/fixed‑bid); hardware resale margins; custom software; change orders; FAT/SAT; training; support/maintenance; SaaS add‑ons (small)
- **What’s good:** Deep plant access & trust; cross‑brand expertise; sticky lifecycle
- **What hurts:** Lumpy demand; labor‑bound growth; low IP reuse; scope creep; thin margins
- **FleetGlue angle:** Turn one‑offs into **reusable blocks**; vendor‑agnostic orchestration; **recurring site licenses**; **faster time‑to‑ROI**
- **Source placeholders:** A3/RIA member profiles; SI sites; trade interviews
---
# 6) Competitive Positioning (Quick Matrix)

| Competitor       | Positioning            | Where They Live in the Stack                                   | Our Angle vs. Them                                                   |
|------------------|------------------------|------------------------------------------------------------------|-----------------------------------------------------------------------|
| **SYNAOS**       | Intralogistics OS      | Material‑flow orchestration (VDA‑5050; factories/warehouses)    | **Deeper device‑level control** + **no‑downtime** brownfield integration |
| **InOrbit**      | RobOps cloud           | Telemetry, incident response, fleet ops APIs                     | **Deterministic plant execution** & cross‑system workflows            |
| **Formant**      | Robot data platform    | Data, teleop, analytics for fleets/OEMs                          | **End‑user orchestration/execution** (plants), not just OEM telemetry |
| **Palantir**     | Manufacturing data OS  | Unified data, analytics, decision ops                            | **Execution layer**: we move materials/machines, integrate data       |
| **Meili**        | Universal FMS          | Lightweight mission/traffic control                              | **Enterprise‑grade safety/audit** + multi‑system coordination         |

**Source placeholders:** Company sites, docs, webinars, case studies (20XX).

---
## Notes & To‑Do (for this week)

- Replace directional figures with **verified** numbers (CBP/Econ Census, IFR, A3, BLS/BEA).  
- Add slide footers with **date + source** per figure.  
- Insert 1–2 Midwest logos/use‑cases once approved.
