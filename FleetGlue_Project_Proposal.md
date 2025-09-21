Here’s a complete, incisive project proposal you can drop into a doc or send as-is. It’s tight, technical where it matters, and free of fluff.

# Project Proposal — FleetGlue: Prompt → Plan → Preflight → Play

## Executive Summary
FleetGlue will evolve from a click-heavy control panel into an **intent-first automation platform** with judgment. Operators express intent in plain language (**Prompt**). FleetGlue compiles it into a structured plan (**Plan**). A lightweight feasibility layer validates it against live and static constraints before dispatch (**Preflight**). If clear, it executes and observes (**Play**).  
This delivers immediate reductions in preventable failures while producing reusable constraint data that compounds into a moat (Constraint Packs, Templates, and—optionally—Constructor-Theory-inspired feasibility checks later).

## Goals & Non-Goals
**Goals (Phase 1):**
- Catch ≥70% operator-caused failures **pre-dispatch** on a pilot cell.
- Add a **Preflight** step with clear explanations and one-click remediations.
- Ship a **Prompt Command Bar** that compiles to a minimal **Task DSL** and round-trips to a simple visual graph.

**Non-Goals (Phase 1):**
- No full physics/kinematics engine.
- No broad UI rewrite. We add, not replace.
- No multi-site rollout; pilot only, feature-flagged.

## Problem
Operators must mentally reconcile payloads, buffers, door interlocks, zones, battery, and comms before each run. Misses cause preventable faults, stop lines, and trigger noisy triage. Our current UI is powerful, but assumes hand-wired flows; **intent lives in people’s heads**.

## Solution Overview
**Preflight with explanations** + **Prompt-to-Plan** on top of the existing stack.

- **Preflight:** a fast gate before dispatch that returns **OK / Degraded / Blocked**, with specific reasons and suggested fixes (e.g., split job, alternate buffer, request PLC tag).
- **Prompt Command Bar:** operators type intent; we compile to a **Task DSL**, run Preflight, visualize as a simple graph (Blockly/React-Flow style), then execute.

## User Flow (Operator)
1) **Prompt:** “When Buffer-A < 2, send an OTTO to pick from Cell-3 and drop at Line-B; open Door-12 if closed.”  
2) **Plan:** FleetGlue parses to a Task DSL (intent, resources, constraints, triggers) and shows a small graph for confirmation.  
3) **Preflight:** Validate payload, buffer capacity, door interlock, zone permission, battery, comms latency; return verdict + explanations + suggested fixes.  
4) **Play:** If ✅ OK, dispatch. If ⚠️ Degraded, offer one-click remediation + recheck. If ⛔ Blocked, explain and route to the right person.  
5) **Learn:** Log a `precheck_event` with inputs/telemetry/reasons to build reusable Constraint Packs and evidence.

## Architecture Fit (uses what we already ship)
- **On-prem network (ROS2):**  
  - Option A (fastest): implement Preflight checks inline within **Automation Engine**.  
  - Option B: add a small **feasibility-engine** ROS2 container exposing a local gRPC/REST `/validate`.
- **Deployment Manager (`fg_ros2_launcher`):** param sync for capability and constraint defaults.  
- **Multilink / Drivers:** live signals (battery, PLC tags, buffer depth, statuses).  
- **Emitters/Logs:** attach `precheck_event` to alerts for triage and analytics.

## Minimal Data & Interfaces
**Task DSL (MVP):**
```json
{
  "intent": "replenish_buffer",
  "triggers": [{"type":"threshold","resource":"Buffer-A","op":"<","value":2}],
  "steps": [
    {"do":"navigate_pick","robot":"OTTO_17","from":"Cell-3","load_kg":8},
    {"do":"open_door_if_closed","door":"Door-12"},
    {"do":"navigate_drop","to":"Line-B"}
  ],
  "constraints": ["PayloadWithinLimit","BufferHasCapacity","DoorInterlockReady","ZonePermitted","BatteryAbove30","CommsLatencyOK"]
}
```

**API (cloud/on-prem):**
- `POST /prechecks` → `{ verdict: "ok|degraded|blocked", reasons:[], remediation:[] }`
- `POST /tasks` (create from DSL)  
- `GET /constraints` / `POST /constraints` (manage library)  
- Store `precheck_event` with task reference + telemetry snapshot.

**Initial Constraint Set (6):**
1. `PayloadWithinLimit` (robot.max_payload ≥ load_kg)  
2. `BufferHasCapacity` (buffer.free_slots ≥ 1)  
3. `DoorInterlockReady` (PLC tag TRUE)  
4. `ZonePermitted` (resource.allowed_zones contains route)  
5. `BatteryAbove30` (robot.battery ≥ threshold)  
6. `CommsLatencyOK` (last_heartbeat_latency_ms < threshold)

**Severity policy:** any missing critical signal ⇒ **Degraded** (safe-by-default), require confirm.

## UI Additions (small, surgical)
- **Preflight Panel** in the run modal: traffic-light verdict, bullet reasons, “Apply fix & Recheck”, policy-gated “Force run (reason required)”.  
- **Command Bar** at the top of Automate: prompt → confirm chips for ambiguity (robot/zone) → show graph → “Run Preflight”.

## Deliverables (Phase 1)
- `POST /prechecks` endpoint + server code in Automation Engine (or feasibility-engine container).  
- 6 working constraints + bindings to Multilink/driver signals and param sync for static limits.  
- Preflight panel + Command Bar MVP + tiny graph view.  
- New tables: `constraint`, `precheck_event`; basic analytics view (top failing constraints, override rate).

## Success Metrics
- **Prevention:** ≥70% operator-caused failures prevented pre-dispatch on the pilot cell.  
- **Latency:** <150 ms average Preflight response.  
- **Force-run rate:** <10% (policy-gated).  
- **Ops time:** minutes saved per prevented run (target: measurable impact per shift).  
- **Quality:** declining repeat reasons as fixes are productized.

## Timeline
**Week 0 (prep):** finalize pilot cell, signals, owners; feature flag.  
**Week 1 (ship MVP):** API + 6 constraints + Preflight panel + Command Bar MVP + logging.  
**Week 2 (stabilize):** add 1–2 remediations (split job, alternate buffer); polish explanations; operator keyboard shortcuts.  
**Weeks 3–4 (measure):** run the pilot, collect KPIs, decide on Phase 2.

## Phase 2 (30–60 days)
- **Constraint Packs** per vendor/device (MIR, OMRON, OTTO, Kepware/PLC, Door).  
- **Auto-remediation** for top degraded cases (split load, reroute, drain buffer).  
- **Preflight Report** exports for QA/customer sign-off.  
- **Templates:** turn common prompts into parameterized recipes.

## Risks & Mitigations
- **Telemetry gaps:** treat unknown as **Degraded**; provide operator confirm; ship shims for missing tags; track gaps in analytics.  
- **Prompt ambiguity:** disambiguation chips (choose robot/zone/door) before Preflight; keep parser deterministic to the DSL.  
- **Operator friction:** <150 ms Preflight, one-click “Apply fix & Recheck”, shortcuts; clear override policy with reason capture.  
- **Scope creep:** feature flag; pilot only; start with 6 constraints.

## Org & Business Impact
- **Ops:** fewer failed runs; faster triage with evidence; less tribal knowledge risk.  
- **Product:** every precheck reason becomes reusable IP (Constraint Packs, Templates).  
- **Sales/Success:** demo becomes “type → preflight → run”; provide exportable Preflight Reports.  
- **Strategy:** creates the backbone for **Feasibility-as-a-Service** (constructor-theoretic checks, humanoid balance/torque, etc.) without changing the UX.

## Resourcing
- **1 backend** (Automation Engine / feasibility-engine + API)  
- **1 FE/UX** (Preflight panel + Command Bar + small graph view)  
- **0.5 FDE** (pilot wiring, signals validation)  
- **QA** (pilot cell only; feature-flagged)

## Demo Script (5 minutes)
1) Type prompt → parsed plan appears.  
2) **Run Preflight** → ⚠️ “Buffer full; suggest: drain 1 slot or route to Buffer-B (click to apply).”  
3) Apply fix → **Recheck** → ✅ OK → **Run**.  
4) Open Evidence → `precheck_event` with reasons, telemetry snapshot, remediation chosen.

---

## Appendix A — Constraint Interface (MVP)
```ts
type ConstraintInput = {
  task:any,                // parsed DSL
  resources:any,           // static caps/limits
  telemetry:any            // live signals (drivers, PLC tags)
}
type ConstraintResult = {
  id:string,
  ok:boolean,
  severity:"degraded"|"block",
  msg?:string,
  remediation?:string
}
interface Constraint {
  id:string
  appliesTo:string[]       // "robot","door","buffer"
  check(input:ConstraintInput): Promise<ConstraintResult>
}
```

## Appendix B — Example Explanations
- **Blocked:** “Door-12 interlock FALSE (PLC: DOOR_READY=0). Request tag or escalate.”  
- **Degraded:** “Buffer-A full. Suggest: drain 1 slot or route to Buffer-B. Click to apply.”  
- **OK:** “Payload 8 kg ≤ 15 kg; Zone=Permitted; Battery 72%; Latency 38 ms.”

## Appendix C — Minimal Table Sketches
- `constraint(id, name, device_class, severity, default_params)`  
- `precheck_event(id, task_id, verdict, reasons_json, remediation_json, telemetry_snapshot, ts, actor_id)`  
- (Optional) `capability(resource_id, verb, params)`; `resource(resource_id, type, limits_json)`

---

### One-liner (for the cover slide/email)
**Intent-first with judgment**: operators state what they want, FleetGlue compiles the plan, **proves it will work** with Preflight, and executes—while every check becomes reusable constraint IP that compounds across customers.
