# FleetGlue’s Factory Coordination OS: A Field Guide to the Wedge, the Platform, and the Proof  
*An in-depth breakdown you can drop into Substack*

---

## TL;DR
- **Category:** *Factory Coordination OS* — the control-layer glue that makes robots, conveyors, doors, PLCs, sensors, apps, and people behave like **one system**.  
- **Disruption wedge:** Small, brownfield **point-solutions < $150k** that must be **boringly successful**: deploy fast, **pass conformance with evidence**, and reduce variance.  
- **Platform engine:** Reusable **Blocks** (workflows) + **Adapters** (device connectors) + **Conformance** (signed acceptance) + **Governance** (certification, rev-share).  
- **How wins compound:** One successful cell → **spec-line** (“Approved Control Layer — FleetGlue”) → integrators **pull** us by default.  
- **What proves PMF (not vibes):** Time-to-First-Good-Run, First-Try Conformance, Reuse%, Spec inserts, Repeat cells/site, Partner-delivered installs.

---

## 1) The Pain on the Floor (Not Another Robot—**Reliable Composition**)

Factories are heterogeneous by design and by history. What jams projects isn’t the lack of a shiny device—it’s the lack of a **reliable way to make different devices behave together**.

```
[Robot A]──┐
           ├──[Conveyor B]──[Door C]──[Sensors D]
[PLC]──────┘           │
                 [Remote I/O]
```

**Where it hurts:**
- **Every install is different.** Variance sneaks in via bespoke ladder logic and one-off scripts.  
- **Ignored small jobs.** Anything **< $150k** gets punted by big SIs and languishes for months.  
- **Acceptance by opinion.** “Looks good” replaces pass/fail test plans and signed logs.  
- **OEMs go blind post-ship.** No consistent telemetry; support gets expensive and slow.

**Translation:** The constraint is **composition** (cross-device orchestration), not single-device control.

---

## 2) The Disruption Wedge (Why We Win First Where Others Won’t)

Classic disruption says a new entrant wins by playing **with different rules** for an **underserved buyer**. In automation, those rules are:

- **Deployability:** in **days, not months.**  
- **Conformance:** **pass/fail suite + signed logs + rollback** by default.  
- **Lifecycle UX:** alerts, remote access, analytics that make support boring.  
- **PLC-optional (only where trivial & safe):** we **interoperate first**; we don’t rip safety or brownfield controls.

*Where incumbents won’t go:* services-heavy stacks and controller vendors don’t like repeatable sub-$150k kits—they break their margins and channel habits. That leaves a gap you can drive a wedge into.

---

## 3) Platform, Not Pipeline (Ecosystem & Governance)

**Pipeline** = sell hours and one-offs.  
**Platform** = orchestrate producers and consumers so every deployment gets easier.

**Roles:**
- **Owner/Governor (FleetGlue):** APIs, certification, rev-share, access/ban policy, change-control.  
- **Producers:** OEMs & machine builders (Adapters, Deployment Plugins); power SIs (reusable **Blocks**).  
- **Providers:** Boutique SIs & distributors (package kits, deliver installs).  
- **Consumers:** Plants/lines (select kits, run conformance, operate).

**Why governance matters:** Platforms die from **noise** (low-quality blocks) and **misaligned incentives**. Certification gates, versioned/signed configs, and clear rewards keep quality high.

---

## 4) The Core Interaction (Our North Star)

> **Producer publishes Block/Adapter → Provider one-click deploys → Cell passes Conformance → Consumer runs with Telemetry.**

**Preconditions to make that true:**
- **Signed config & versioning** (diffs, rollbacks).  
- **Conformance suite**: safety I/O, network, cycle count, error-rate threshold, **rollback test**.  
- **Telemetry on** by default (**customer owns data**).  
- **Security**: SSO/SAML, RBAC, TLS, audit logs, **offline-first**.

**North-star metric:** **Core-Interaction Pass Rate (first attempt).**  
If this is **boringly reliable**, network effects kick in. If it’s noisy, they don’t.

---

## 5) From Win → **Pull** (The Spec-List Ladder)

One successful cell isn’t enough. You need **default** status.

1) **One cell works** (evidence, not vibes).  
2) **Paste the spec-line** across projects.  
3) **Integrators must use us** (default control layer).

**Paste-ready spec (factory):**
```
Approved Control Layer — FleetGlue (Factory Coordination OS)
• Interfaces: EtherNet/IP, OPC UA, MQTT, REST
• Deployment: acceptance suite + signed logs; versioned rollback
• Security: SSO/SAML, RBAC, TLS, audit; offline-first
• Data: customer-owned; OEM-branded insights (opt-in)
• Brownfield: PLC-interop; PLC-optional only for temperature/interlocks
```

**Principle:** **Pull > Push.** Specs are platform governance, not a feature list.

---

## 6) Positioning & Boundaries (Say What We Are—and What We’re Not)

**2×2 mental map:**  
- **X:** Deployability & Conformance (low → high)  
- **Y:** Vendor Lock-in (high → low)

**Place the field:**
- Big PLC stacks → *High lock-in / Mid deployability*  
- Big SIs → *Mid lock-in / Low deployability* (bespoke)  
- Vendor fleet mgrs → *Mid/Mid* (single-brand orchestration)  
- **FleetGlue** → **Low lock-in / High deployability** (cross-vendor + evidence)

**Boundaries:**  
- Not MES/SCADA/OEE (that’s the **scoreboard**)  
- Not a robot OEM (we integrate, don’t compete)  
- Not a custom SI (we standardize; services enable, they don’t define us)

**Line to remember:** *“We coordinate devices; we don’t replace them.”*

---

## 7) Evidence > Opinions (The Scoreboard That Sells Itself)

Measure what the buyer cares about *at the coordination layer*:

- **Time-to-First-Good-Run (days)**  
- **First-Try Conformance (%)**  
- **Handoff retry rate ↓** (robot↔conveyor/door/sensor)  
- **Cross-device MTTR ↓** / **takt variance ↓**  
- **Unplanned downtime ↓** (coordination-attributable)  
- **Repeat cells/site** & **Spec inclusions (#)**

**Back-of-napkin ROI:**  
**Days saved × Cost per line-day** = $ impact / site / quarter.

OEE improves **because** coordination improves, but OEE isn’t the thing we sell. It’s the scoreboard; we’re the quarterback with the receipts.

---

## 8) Repeatability (Avoid the “False Dawn”)

A few founder-led wins can lie. Publish a **Repeatability Scorecard** and hold the bar:

- **TTFGR:** median ≤ **14d**, P90 ≤ **28d**  
- **First-Try Conformance:** ≥ **80%**  
- **Block reuse:** ≥ **70%** of steps from library  
- **Adapter reuse:** ≥ **80%** from catalog  
- **Partner-delivered installs:** ≥ **60%** (not founder-delivered)  
- **Spec inserts:** ≥ **50%** within 30–60 days  
- **Repeat cells/site:** ≥ **2** within 90 days  
- **Discount discipline:** ≥ **70%** at list ±10%

**Red-flag traps (false dawn):** founder favors, >60 ENG hours on site, one-off adapters, no spec insert, price wobble, security/offline gaps that stall IT.

---

## 9) The Flywheel Meter (Watch Compounding, Not Just ARR)

Track these weekly and make them visible:

- **# Certified Blocks**  
- **Adapter coverage %** (for top robot/PLC/fieldbus/equipment)  
- **# Conformance runs (signed)**  
- **# Accredited partners** (active)  
- **# Spec inclusions** (plant/network)

If these rise together, you’re building gravity a competitor can’t copy with a slide deck.

---

## 10) ICP & The “Ignored Cell” (Where to Hunt First)

**Who:** Mid-market discrete manufacturers, **brownfield**, mixed vendors.  
**Deal shape:** **Point solutions < $150k**, pilotable in **2–4 weeks**.  
**Tells:** acceptance by opinion; integrator churn; taped-over buttons; Excel dispatch; walkie-talkie handoffs.  
**Rule:** **PLC-interop first**; PLC-optional **only** for trivial, approved logic (temperature/interlocks).

**Two live examples:**
- **With robots:** AMR → safety door → conveyor → barcode: enforce interlocks, timing, retries; log **pass/fail** acceptance.  
- **No robots:** oven + door + carts + labeler: sequence, safety, dwell timers, compliance evidence.

---

## 11) Day-One Playbook (Two Experiments, Real Dates)

**Experiment A — AMR handoff cell (<$150k)**
- **Blocks:** AMR handoff, conveyor sync, scanner QA.  
- **Conformance 5:** network; safety I/O; cycle count; error-rate < X; rollback test.  
- **Gate:** TTFGR ≤ 14d; First-Try Conformance ≥ 80%; **spec insert** in 30 days.

**Experiment B — No-robot utility loop (<$150k)**
- **Blocks:** door interlock, oven dwell, label print-and-verify.  
- **Same gates.**

**If you miss a gate:** capture gap → add Block/Adapter or tighten governance → re-run within 30 days.

---

## 12) FAQ (Crisp, Safe, Reusable)

- **Do you replace PLCs?**  
  *No. We **interoperate first**. We’re PLC-optional only for narrow, trivial, **approved** logic.*

- **Are you RobotOS?**  
  *Robots are one instrument. We’re the **conductor**—the Factory **Coordination** OS for the whole band.*

- **Is this OEE software?**  
  *OEE is the **scoreboard** (MES/SCADA). We coordinate execution and provide **conformance** evidence.*

- **Who owns the data?**  
  ***The customer.*** We provide secure plumbing and optional **OEM-branded** views (opt-in).

- **Security/offline?**  
  *SSO/SAML, RBAC, TLS, audit logs, signed configs, versioned rollback, **offline-first**.*

---

## 13) Templates You Can Paste

**Spec insert (factory):** *(repeat from §5)*

**Conformance checklist (starter):**
- Connectivity pass (fieldbus/API)  
- Safety I/O pass (interlocks verified)  
- Cycle count N without error  
- Error-rate < X% over Y cycles  
- Rollback to prior version, re-run pass scenario  
- **Signed** result + config hash stored

**Block library seed (examples):**
- AMR → conveyor handoff  
- Door interlock supervisor  
- Buffer/zone manager  
- QA image capture & classify  
- Barcode/UID reconcile  
- Changeover recipe apply + verify

---

## 14) Positioning for Each Audience (Same Core, Different Hook)

- **Plants (main buyer):** “Live in weeks, **pass acceptance with proof**, fewer regressions.”  
- **Integrators:** “Make **< $150k** jobs profitable and predictable; less rework; faster commissioning.”  
- **OEMs/Machine builders:** “Every install behaves the same; **OEM-branded** health; fewer support fires.”  
- **Distributors:** “Quick-Start kits that unlock small projects and move hardware.”

---

## 15) The One-Liners (Tattoo These)

- **“We sell deployability—with proof.”**  
- **“Disruption gets us in; platform keeps us in—spec makes us default.”**  
- **“Evidence beats opinions.”**  
- **“Blocks compound—services don’t.”**  
- **“We coordinate devices; we don’t replace them.”**

---

### Closing Thought
Winning here isn’t about being **30% better** at a feature; it’s about **changing what buyers value**: **deployability, conformance, lifecycle UX**. Land where those are non-negotiable (**ignored sub-$150k cells**), make the **core interaction** boringly reliable, then let the **platform flywheel** do what pipelines can’t—compound.
