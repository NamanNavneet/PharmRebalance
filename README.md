# PharmRebalance 💊

> **AI Practice Hackathon — Team Vector 5** | ZS Associates  
> A real-time, agentic pharma supply chain optimization system that detects disruptions, rebalances inventory, and prevents stockouts — **before patients are turned away.**

---

## The Problem

Traditional pharmaceutical Supply Chain Management (SCM) is **siloed by design**:

- The **Transfer Team** decides inter-location transfers independently
- The **Supply Team** places replenishment orders independently
- The **Expiry Team** tries to minimize drug wastage independently
- **No one talks to each other in real time**

When a disruption hits — a hurricane, a shipping lane closure, a logistics partner going bankrupt — the response takes **days and weeks** of meetings, spreadsheets, and approvals. By the time the decision is made, the stockout has already happened. The patient has already been turned away.

> **5,398** — the number of patient-days of medication lost to preventable stockouts in the simulation. Behind every stockout-week is a chemotherapy patient, a cardiac patient, a child waiting for a vaccine.

---

## The Solution

PharmRebalance is a **unified, intelligent platform** powered by four specialized AI agents that ingest supply chain data, debate real-world trade-offs simultaneously — just like real teams do — and deliver mathematically optimized, fully auditable recommendations **in seconds**.

It doesn't find the cheapest solution or the fastest one. **It finds the one that works best across every constraint that matters in pharma.**

---

## Meet the Agents

| Agent | Role | Responsibility |
|---|---|---|
| 🔵 **Transfer Optimizer** | LP-based solver | Identifies excess and shortage maps; computes optimal inter-location drug transfers respecting cold chain, FEFO, MOQ, and transport lanes |
| 🟢 **Expiry Manager** | Waste prevention | Validates all plans against batch expiry dates; ensures FEFO (First Expired, First Out) is never violated |
| 🟠 **Supply Adjuster** | Replenishment control | Cross-checks transfer plans; adjusts supply orders to avoid double-solving and redundant procurement |
| 🟣 **Simulation Engine** | Before vs. after proof | Runs counterfactual simulations to prove the impact of decisions before they are executed |

> **No agent works alone.** Every recommendation is pressure-tested by all four agents before it reaches the decision-maker.

### Agent Orchestration Flow

```
11 Datasets Ingested (SKUs, Supply, Demand, Forecast, Routes, Plans)
    │
    ▼
ORCHESTRATOR
    ├── Transfer Optimizer  ──► Checks transfer plan
    ├── Supply Adjuster     ──► Checks both transfer + supply plans
    ├── Expiry Manager      ──► Validates everything (FEFO + Cold Chain)
    └── Simulation Engine   ──► Before vs. After proof
    │
    ▼
Multi-Constraint Optimized Recommendation
    │
    ▼
Explainable Dashboard + AI Command Center
```

---

## Multi-Constraint Optimization

The Transfer Optimizer runs a **Linear Programming (LP) solver** that simultaneously optimizes across:

**Objective Function:**
- Minimize Transfer Cost + Unmet Demand Penalty (weighted by Therapeutic Criticality)

**Hard Constraints:**
- ❄️ Cold Chain Compatibility — temperature-sensitive drugs cannot use incompatible routes
- 📦 FEFO Batch Sorting — First Expired, First Out is always enforced
- 🚚 Transport Lanes — only validated routes used
- 🔢 Integer Feasibility — no fractional unit transfers
- 📋 Released Items & MOQ — minimum order quantities respected
- 🌿 CO₂ Emissions — carbon footprint tracked per transfer

> Unmet demand for cancer and cardiac drugs incurs a **higher penalty weight** than general inventory — therapeutic criticality is baked into the math.

---

## Key Trade-offs the Agents Resolve

| Conflict | How PharmRebalance Handles It |
|---|---|
| **Transfer vs. Expiry** | Transfer Optimizer and Expiry Manager debate; FEFO wins as hard constraint |
| **Cold Chain vs. Optimal Route** | Cheaper routes are rejected if cold chain is violated |
| **Therapeutic Criticality vs. Inventory Balance** | High-criticality drugs get weighted priority in LP penalty function |
| **Cost vs. Waste Prevention** | Agents balance transfer cost against expiry-driven waste |

---

## Product Features

### 📊 Consolidated Dashboard
- Single-pane view of service level, stockouts, cost savings, and actions executed
- 8-week demand trends, 4-week inventory projections, real-time supply pipeline status

### 🌍 Risk Radar — Real-Time Risk Sensing
- Live global events mapped to the supply network
- Input: real-world disruption (e.g., hurricane threatening the Gulf Coast)
- Output: affected locations, at-risk SKUs, patient impact, and recommended countermeasures — **before disruption hits**

### 🤖 AI Command Center
- Natural language interface over the optimization engine
- LLM selects from **9 deterministic Python functions** that query real pipeline data
- Answers come from computed optimization outputs — **not probabilistic generation**
- Zero hallucination. Full audit trail.

### 📦 Inventory Planning
- Batch-level visibility across every location
- Demand patterns and forecast confidence broken down by SKU

### ✅ Recommendations Engine
- Every action includes: cost, carbon footprint, stockout impact, therapeutic area
- Nothing is a black box — every recommendation is **fully traceable**

### 🗺️ Network Health View
- Every supply chain node scored and color-coded by health
- Full topology view from plants to depots

---

## Determinism — Why This Matters

Most AI systems in supply chain are probabilistic — they guess. PharmRebalance is built on a **hybrid deterministic + AI architecture**:

| Component | Approach |
|---|---|
| Transfer optimization | LP solver — mathematically guaranteed optimal solution |
| Expiry/Cold chain enforcement | Hard constraints — never violated |
| AI Command Center | LLM chooses *what to ask*; Python functions provide *the answers* |
| Audit trail | Every decision is fully traceable to its data source |

> **"The LLM decides what to ask. Deterministic Python functions provide the answers. No hallucination. Full audit trail."**

---

## Impact Metrics

| Metric | What It Measures |
|---|---|
| 🏥 **Patients Saved** | Reduction in stockout-days for critical therapeutic categories |
| ♻️ **Waste Eliminated** | Drug units saved from expiry through intelligent rebalancing |
| 🌿 **CO₂ Footprint** | Carbon emissions tracked and minimized across transfer routes |

---

## Data Inputs

The system ingests **11 datasets** covering:
- SKU master data
- Supply elements
- Demand elements
- Demand forecasts
- Route maps
- Transfer plans
- Batch inventory (with expiry dates)
- Cold chain compatibility mappings
- Transport lanes
- Therapeutic criticality classifications
- Real-time external event feeds (news/risk signals)

---

## Team

**Team Vector 5 — ZS Associates AI Practice Hackathon**

| Name | Role |
|---|---|
| Kashish Bhagat | Team Lead |
| Shivam Tyagi | Team Member |
| Hrishiraj Mallick | Team Member |
| **Naman Navneet** | Team Member |

---

## Inspiration & Research Foundation

PharmRebalance builds on ZS's published research in pharma SCM:

- **"Pharma's Next AI Edge: A Purpose-Built Data Strategy"** — Sourirajan, Shastri, Jarvis (Jan 2025) — *Data architecture foundation*
- **"Optimizing External Supply & Contract Manufacturing"** — George, Khare, Mutya (ZS 2022) — *Selective supply order logic*
- **"Digital Twin Technology in Pharma SCM"** — H. Caglar Ozdag (Jan 2024) — *Digital twin blueprint*
- **"Gartner SCM Symposium: AI & Agility Q&A"** — H. Caglar Ozdag (2025) — *Agility framework*
- **"AI, Analytics & Supply Chain Resilience"** — John DeSarbo (Jun 2025) — *Coordination imperative*
- **"How Supply Chains Win in an Era of Disruption"** — Ozdag & DeSarbo (2025) — *Self-correcting system design*

---

## Skills Demonstrated

`Agentic AI` · `Multi-Agent Orchestration` · `Linear Programming (LP Optimization)` · `LLM Function Calling` · `Pharma Supply Chain` · `Real-Time Risk Sensing` · `Deterministic AI` · `Explainable AI (XAI)` · `Digital Twin Concepts` · `Natural Language Interface` · `Constraint Optimization`
