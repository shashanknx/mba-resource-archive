# Operations
*Courses: Designing & Managing Business Processes (OPNS 440) · Business Analytics*

> Use this when analyzing a process, finding where capacity is constrained, designing service systems, or validating a change before rolling it out.

---

## Quick Reference

- **Little's Law: I = R × T** — know 2 of 3, solve for the third; links ops to financials
- **Bottleneck** — the slowest resource constrains the entire system; improve it first
- **TFT** — Theoretical Flow Time = time along the critical path (no waiting)
- **Buildup diagram** — track inventory when demand or capacity varies over time
- **Queuing (TUV)** — utilization approaching 1 → exponentially longer waits; pooling always beats splitting
- **Experimentation** — A/B test, switchback, synthetic control; p < 0.05 to detect a real effect

---

## Frameworks

### Little's Law: I = R × T

| Variable | Meaning |
|----------|---------|
| **I** | Average inventory (# of flow units in system) |
| **R** | Throughput rate (units / time) |
| **T** | Flow time (avg time a unit spends in system) |

**How to use:**
1. Draw the process flowchart
2. Build a table — one column per activity, rows for I, R, T
3. Total I = sum across all activities; Total T = sum across all activities
4. Know 2 of 3 → solve for the third ("Sudoku step")
5. Translate to financials: multiply by unit economics

Units must be consistent. R in units/hour → T in hours, I in units. Only valid for stable processes (inflow = outflow).

**RTB case:** R = 500 machines/month leaving the system, I = 4,300 total → T = 8.6 months average ownership. Count inventory across *all* locations.

---

### Bottleneck / TFT / Capacity

**Theoretical Flow Time (TFT)** = time along the critical path (longest path, no waiting). Answers: "How fast can we handle a rush order?"

**Capacity** = throughput of the bottleneck resource. Answers: "How much volume can we handle?"

**Finding the bottleneck:**
Build a table: Resource | Unit Load | Unit Capacity (= 1/Unit Load) | # of Units | Total Capacity
Bottleneck = lowest total capacity. Process capacity = bottleneck capacity.

**Key rule:** Improving any non-bottleneck does nothing for total throughput. Fix Herbie first.

Mixed order types: weight each resource's unit load by the fraction of orders it handles.

---

### Buildup Diagram
*Use when:* Demand or capacity changes over time (peak hours, shift changes, seasonal surges).

**Steps:**
1. Identify time intervals where R_in or R_out changes
2. Build table: Interval | R_in | R_out | ΔR | ΔI (= ΔR × period length) | I at end of period
3. Inventory cannot go negative — negative means customers are waiting
4. Graph I over time; connect the dots

**GlobalTech case:** US center (8 AM–4 PM, 60 calls/hr) + India center (4 PM–midnight, 40 calls/hr). Daily capacity (800) > daily demand (780), but inventory builds overnight when no center operates. Fix: shift India center hours.

---

### Queuing (TUV)

**TUV intuition:**
- **T** (service time) → longer = worse
- **U** (utilization = R / capacity) → approaching 1 → exponentially longer waits
- **V** (variability) → amplifies waits; the hidden driver most managers ignore

**Economies of scale in queuing:** One large pooled queue with the same utilization always outperforms two separate smaller queues. Never split a shared resource by order type unless forced to.

**Spreadsheet inputs:** # servers (s), mean arrival rate (λ), mean service rate per server (μ).
**Outputs:** Average queue length, average wait, utilization, % waiting > X minutes.

**Francona's Pizza case:** West Side (8 workers, 2× demand of East Side) has shorter wait than East Side (4 workers) — economies of scale dominate. Splitting workers by dine-in vs. delivery removes this advantage.

---

### Experimentation

| Method | When to use | Key requirement |
|--------|------------|-----------------|
| **A/B test** | Split population into control/treatment | Groups must be statistically comparable |
| **Switchback** | Alternate control/treatment over time | Account for seasonality; equal periods per "season" |
| **Synthetic control** | No clean control group | Weighted combo of untreated units = counterfactual |

**p-value guide:**
- Testing if a change worked → want p < 0.05
- Detecting noise from signal → want p > 0.05

**3-sigma control limits:** UCL = μ + 3(σ/√n) · LCL = μ − 3(σ/√n). Sample mean outside = real process change.

**Watch for:** A/B tests fail when treatment contaminates control — common in networks, shared infrastructure, or anything with social spillovers.

---

### PQTV — What Is Good Operations?
Good operations = alignment between process and value proposition.

| Dimension | What It Measures |
|-----------|-----------------|
| **P** — Price | Cost efficiency; can you compete on cost? |
| **Q** — Quality | Defect rate, reliability, consistency |
| **T** — Time | Speed of delivery, responsiveness |
| **V** — Variety | Flexibility for different customer needs |

You cannot maximize all four simultaneously. Pick your rank order based on strategy, then design operations to match.

---

## Mental Models

**"Find Herbie."** One resource constrains the entire system. All improvements are wasted until the bottleneck is addressed. (From *The Goal* — the slowest hiker sets the pace for the whole group.)

**Pooling > Splitting.** Shared queues and pooled resources almost always outperform dedicated lanes. Most managers still don't believe it; the math always proves it.

**Inventory is capital in disguise.** Every unit sitting in a process is money not moving. Cutting flow time frees cash. Little's Law is the bridge between ops and finance.

---

## My Notes & Updates
*Add new entries at the top. Format: [Month Year] — note*

[April 2026] — File created. Covers Designing & Managing Business Processes (Winter OPNS 440), Business Analytics.
