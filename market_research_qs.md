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
# 3) Automation and robotics adoption snapshot

---

## Working definitions

**Advanced automation** = robots, machine vision, sensors, plus orchestration beyond a single PLC cell.  

**Robotics specifically** = industrial arms, cobots, AMRs in production or material flow.  

---

## Maturity ladder (plant level)

- **Stage 0** none  
- **Stage 1** cell  
- **Stage 2** line  
- **Stage 3** plant  
- **Stage 4** multi-site  

**FleetGlue sweet spot:** Stages 2 to 4.  

---

## By size band (insert % after sourcing)

- **1 to 99:** low robotics, pockets in welding and packaging.  
- **100 to 499:** Stage 1 to 2 common, AMR interest rising.  
- **500 plus:** highest penetration, Stage 2 to 3, some Stage 4 in regulated sectors.  

---

## By vertical

- **Auto OE and Tier 1:** high robotics, strict change control, Stage 3 to 4.  
- **Electronics and semi back-end:** high robotics and vision, fast changeovers, Stage 2 to 3.  
- **Aerospace and defense:** validation heavy, Stage 1 to 3.  
- **Food and beverage:** growth in packaging and intralogistics, Stage 1 to 2.  
- **Medical devices and pharma:** strong validation and e-records, Stage 2 to 3.  
- **Metals and job shops:** early but growing for tending and AMRs, Stage 0 to 2.  

---

## How to size penetration (show low and high)

- Pull IFR United States installed base and latest density.  
- Estimate plants with robots by dividing installed base by robots-per-plant assumptions by vertical and size band, bounded by Census establishments.  
- **AMRs:** use A3 trend data and vendor case studies to estimate multi-robot plants and where AMRs are already in production.  

---

## What to capture in CRM for every account

- Stage 0 to 4  
- Brands on site (robots, PLCs, WMS, MES)  
- Validation regime  
- Changeover cadence  
- Exceptions per shift  
- Downtime policy  

**Buying cues:** mixed-brand fleets, no planned downtime, audit trail requirements.  

---

## Pilot metrics to prove fit

- Time to first value in hours  
- Mission success rate  
- Exceptions auto-resolved  
- Changeover time delta  
- Count of no-downtime upgrades  
- Number of signed audit logs accepted by QA or compliance  

---

## Source placeholders

- IFR World Robotics 20XX  
- A3 20XX  
- Deloitte or McKinsey 20XX surveys  
- Census CBP and BLS for denominators  

---
# 4) SI Business Model (Revenue, Pros/Cons) & FleetGlue Angle

- **Revenue mix:** Project engineering (T&M/fixed‑bid); hardware resale margins; custom software; change orders; FAT/SAT; training; support/maintenance; SaaS add‑ons (small)
- **What’s good:** Deep plant access & trust; cross‑brand expertise; sticky lifecycle
- **What hurts:** Lumpy demand; labor‑bound growth; low IP reuse; scope creep; thin margins
- **FleetGlue angle:** Turn one‑offs into **reusable blocks**; vendor‑agnostic orchestration; **recurring site licenses**; **faster time‑to‑ROI**
- **Source placeholders:** A3/RIA member profiles; SI sites; trade interviews

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
