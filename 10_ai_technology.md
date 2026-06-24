# AI & Technology
*Courses: AI Foundations for Managers — AgentOps (AIML 901) · Building Intelligent Products (Spring 2026) · AI for Product Leaders (Summer 2025)*

> Use this when scoping an AI project, evaluating where AI creates real leverage, understanding how LLMs and agents actually work, or making sense of the AI industry landscape for strategy and career decisions.

---

## Quick Reference

- **Find It · Bottle It · Solve It** — the AI project lifecycle: find the problem, understand the data/model, then test and drive adoption
- **5% AI, 95% domain expertise** — the model is the easy part; the value is in the problem, data, and change management
- **How large language models (LLMs) work** — a neural network that predicts the next token; once trained it's frozen (fine-tune or add memory stores to extend it)
- **Training vs. Inference** — training tunes parameters (slow, expensive, upfront); inference generates text (fast, pay-per-use)
- **Pre-train → Post-train → Align** — foundation model learns language → supervised fine-tuning (SFT) + reinforcement learning from human feedback (RLHF) shape behavior → alignment targets Helpful, Honest, Harmless
- **AI Agent** — an LLM running in a loop with tools and a goal; it decides which tools to use, when, and when to stop. The **Model Context Protocol (MCP)** is the standard way tools are exposed
- **RAG (Retrieval-Augmented Generation)** — pulls external docs into context; great for search, not for "teaching" the model
- **AgentOps** — moving from prototype to impact; success needs adoption, data, ROI, governance, talent, and change management — not just a model
- **Evaluation** — split computable/verifiable metrics from human-judgment metrics; use **LLM-as-a-judge** to scale the latter
- **AI stack** — Compute · Infrastructure · Data/MLOps · Foundation Models · Autonomous Systems

---

## Frameworks

### Find It · Bottle It · Solve It — The AI Project Lifecycle
A practical sequence for taking an AI idea from concept to real-world impact.

**1. Find It — Find the problem.**
- Start with the problem, not the technology. Remember: a project is ~5% AI and ~95% domain expertise.
- Choice of problem is the highest-leverage decision. Look for high return-on-investment (ROI), repeatable tasks where AI augments domain experts.
- Best AI use cases cluster into: finding & managing information, pattern recognition & analytics, training/assistants/roleplay, and automation — driving **productivity, upskilling, automation, and innovation**.

**2. Bottle It — Understand the data and the model for the problem.**
- Map the data: collection, organization, quality, and where it lives. Access to the right data is the real moat and the real cost.
- Choose the right model and approach: smaller/cheaper vs. larger/smarter, smart routing, fine-tuning vs. system prompts, RAG for retrieval, tools/MCP for actions.
- Design the agent or workflow around the model's strengths and constraints (non-determinism, context limits, verification cost).

**3. Solve It — Ship it and make it stick.**
- **Test & success criteria** — define measurable, verifiable metrics before building; decide what "good enough" looks like.
- **Change management & adoption** — adding AI means the *whole process* must change. Give users ownership, manage the human/AI interaction, address safety/governance, and run a pilot before scaling.

> The hardest parts of an AI project are at the ends: picking the right problem (Find It) and driving adoption (Solve It). The model in the middle is the commodity.

---

### How LLMs Work
- An LLM is a neural network that **predicts the next token** by matching patterns learned from training data. It's "just an algorithm" — a few-GB file of parameters holds everything it knows.
- Once trained, the model is **frozen** — no new information enters. Extend it via fine-tuning or external **memory stores**.
- **Tokens** are the unit of input/output (words/sub-words). This is why models miscount letters (e.g., "how many R's in strawberry").
- **Temperature** — controls randomness of the probability distribution (higher = more creative/random). **Top-K** — how many candidate next tokens to sample from.
- **Cost drivers:** larger models, longer inputs, and novel (not-seen-before) inputs all cost more. **Smart routing** sends easy queries to small models and hard ones to large models.

---

### Pre-training, Post-training & Alignment
- **Foundation / pre-trained models** encode grammar, concepts, and reasoning in their parameters — but raw output is often useless ("gibberish"). They learned *what* but not *how to be useful*.
- **Supervised Fine-Tuning (SFT)** — manually craft example Q&A pairs showing how the model *should* answer; a human checks the output. Doesn't overwrite the base model, just nudges it. A special stop token cuts off the response.
- **System message** — added to the context window; the model is fine-tuned to prioritize it. This is how you set behavior at runtime without retraining.
- **Reinforcement Learning (RLHF / RL)** — removes the human from the loop by letting the model improve against rewards via trial and error (e.g., AlphaGo self-play). Only works for **verifiable tasks** (code, math, reasoning) — not empathy or open-ended knowledge.
- **Alignment** — setting the model's behavior toward **Helpful, Honest, Harmless**. These trade off against each other; it's a genuinely hard problem.

| | System Message | Post-training / Fine-tuning |
|--|----------------|----------------------------|
| Complexity | Easy | Complex |
| Modifies parameters? | No | Yes |
| Speed | Immediate | Slow |
| Cost | None upfront, costs $ at inference | Expensive upfront, cheaper at inference |

**Reasoning:** Chain-of-Thought ("think out loud") and Tree-of-Thought (explore multiple reasoning paths) produce better answers. DeepSeek showed reasoning can be *learned* via RL. Reasoning models can generate high-quality **synthetic data** to train the next generation.

---

### AI Agents
- An **AI agent** is an autonomous system that executes tasks: an LLM running **in a loop** to achieve a goal. Human input → goal → LLM decides actions → defined output.
- The LLM decides **which tools to use, when, and when to stop**. The system message tells it how to use each tool.
- **MCP (Model Context Protocol)** is the standard protocol for connecting AI assistants to any tool; modern models are post-trained to recognize and use it.
- **RAG (Retrieval-Augmented Generation)** lets an LLM pull relevant info from external databases or document collections into context. Caveat: it doesn't *teach* the model anything — it's pattern-matching over retrieved text, and you can't always tell which documents it used. **Best reserved for search.**
- Tool use also fixes brittle reasoning: instead of autocompleting "123 × 456," the agent calls a calculator tool and reports the verified result.

---

### AgentOps — From Prototype to Impact
Getting an agent from a working demo to durable business value.

**Agent-first process, product, or service:** Adding AI isn't a bolt-on — the entire process must be redesigned around the agent. Start from the goal and work backward.

**What a successful AI project needs:**
- Choice of problem (the right, high-value problem)
- Data collection & organization
- Adoption & change management
- Positive net present value (NPV) / ROI
- Safety & governance
- Talent
- Thoughtful human/AI interaction design
- Awareness that AI is still advancing rapidly (design for change)

---

### Evaluation & Continuous Improvement
**Agent evaluation system** — how do you know the agent is actually working? Borrow operations metrics:
- **Flow time** — entire process duration
- **Inventory** — work not done (data not entered, emails not sent)
- **Throughput** — # of visits, touchpoints handled
- **Quality** — defects, errors, customer needs captured correctly
- **Cost**

**Two metric types:**
- **Computable / verifiable** — failure rate, time, whether a record was correctly categorized in the customer relationship management (CRM) system
- **Human / judgment** — "meets standards," "customer need correctly captured," tone, quality

**LLM-as-a-judge:** Use an LLM to score the "human" metrics at scale (e.g., a judge LLM scores drafted emails 1–5). This makes complex, subjective evaluation tractable.

**Human vs. agent evaluation:** Gather data → run the agent → manually compare (human eval), or have a judge LLM score outputs automatically (agent eval).

**Piloting a rollout (Proxima Health example):**
- Pilot size: small control group (8–12 reps) + experimental group
- Budget and timeline tied to the sales cycle; a **Go/No-Go checkpoint** ~⅓ of the way through
- Give reps **ownership** so they provide evaluation feedback
- Key performance indicators (KPIs): visit time vs. login time, time on sales vs. admin, data quality / coaching time
- Decision to scale only if targets are hit (e.g., free up 20% of hours + pipeline increase)
- Plan a **fallback** for data risk (work phone, auto-deletion, offline mode)

---

### AI Industry Landscape (Market Thesis)
The AI ecosystem is structured across **five core layers**: Compute · Infrastructure · Data/MLOps · Foundation Models · Autonomous Systems. Three pillars define the current market:

- **Energy Layer (the binding constraint):** Grid capacity is capped, making nuclear (Oklo, TerraPower) and advanced cooling valuable.
- **Data Layer (the nervous system):** Human text is exhausted; focus is shifting to synthetic data and unstructured-data refiners (Snowflake, Databricks, Palantir).
- **Edge & Physical Layer (the body):** To beat cloud latency, intelligence is moving to robotics and edge inference chips.

**Trends:** "Agentic AI" and "vibecoding" are automating enterprise workflows and ticket resolution. AI is moving beyond the software market to disrupt the ~$10T global *services* market (sales, HR, legal, customer service). The moat for AI startups is **deep industry data and expertise** to train high-ROI models. The biggest adoption blockers are **non-deterministic outputs** and **verification time** — if a human must re-check every output, the productivity gain is erased.

**Frontier directions:** wearables, computer vision, multimedia, on-device/edge AI, medical tech, robotics, agentic browsers, coding agents, voice/sound models (voice → transcription → LLM → text/voice), and **world models** to train robots.

---

### Building Intelligent Products — Course Framework
*Course: Spring 2026 (Kellogg + McCormick) | Professor-led; practical AI product development for MBAs*

**Course arc:** What is product management (PM) → MRD (Market Requirements Document) / customer discovery → discovery → execution (PRD, Product Requirements Document) → data & ML platforms → perfecting the product → final presentations.

**Key slides by module:**
- M1 — Intro to PM: What does a PM do? Product lifecycle, roadmap ownership, cross-functional role
- M2 — Everything MRD & Customers: Market requirements, customer segments, voice of customer
- M3 — Discovery: How to validate a problem before building a solution
- M6 — Execution / PRD: Translating discovery into engineering specs; MoSCoW in practice
- M7 — Perfecting the Product: Optimization, A/B testing, launch sequencing
- M8 — Data Planning & Product Platforms / ML: How ML models get trained, deployed, and monitored

**Guest lectures:**
- Matt Yao (Roe) — "Building Scalable and Intelligent Systems": architecture considerations for AI-native products; latency, reliability, and the challenges of scale
- Matt Yao — "Product Career Journey Before and After": how the PM role changes when AI can generate working code; the premium shifts to product taste and problem selection

**Key project deliverables:**
- **Data PRD** — structured requirements for training data: what data, from where, in what format, with what labels
- **Share of Wallet analysis** — estimating how much of a customer's spending your product can capture
- **Uber ML Case — Predictive Surge Mitigation for Event-Based Rides** — applying ML thinking to operational pricing problems; how to frame a predictive model as a product decision
- **Master Prompt (Department Scoping Tracker)** — a full software build specification written as a prompt to Claude/Codex. Produced a working Flask + SQLite app in one unattended pass. Demonstrates: prompt engineering as a product skill, software specification writing, and the shift from "write code" to "specify the system"
- **Presentation + Rubric** — final product pitch evaluated on clarity of problem, solution, feasibility, and go-to-market

**Ideation insight (IT Stakeholder Alignment product concept):**
- Problem: IT projects fail because of misaligned stakeholders. Engineers, budget owners, functional teams, and downstream departments don't agree → poorly adopted software → wasted spend.
- Concept: AI-powered project intake and scoping tool that interviews stakeholders, drafts requirements, and tracks phase progress — reducing IT delivery failures by aligning stakeholders before a line of code is written.
- Competitive advantage: high switching costs once embedded in a company's IT workflow; potential network effects if multiple departments adopt and share requirement templates.

---

### AI for Product Leaders — Summer 2025
*Three PDFs: AI Intro for PMs · JR Master Class Prompting · Prompt Engineering*

**AI Intro for PMs:** Product managers need a working model of how AI functions to scope features, write data PRDs, and evaluate feasibility. Core concepts: LLMs, tokens, context windows, fine-tuning vs. prompting, RAG vs. training.

**Prompt Engineering (JR Master Class):**
Key prompting patterns for PMs:
- **Role + context + task + constraints** — always give the model a clear frame before the ask
- **Chain-of-thought** — ask the model to reason step by step before giving a final answer; improves accuracy on complex tasks
- **Output format specification** — tell the model what format you want (JSON, bullet list, table, paragraph); it follows format instructions reliably
- **Iteration over perfection** — treat prompts as code: version them, test them, refine them. A prompt that works 80% of the time is version 1, not done.
- **Persona injection** — "You are a senior product manager reviewing a PRD…" gives the model a useful evaluative stance
- **Few-shot examples** — showing 2–3 examples of the desired input/output format dramatically improves consistency

---

## Cases & Examples

| Case | Course | Lesson |
|------|--------|--------|
| Proxima Health — sales process | AgentOps / AIML 901 | Optimize the rep workflow (prep → touchpoint → log → follow-up → handoff); pilot with control/experimental split before scaling |
| Tech Crunch Disrupt insights | AgentOps / AIML 901 | Verification time is the enemy of enterprise AI adoption; deep industry data is the moat; "bubbles are necessary" to fund innovation |
| Waymo vs. Uber (autonomy) | AgentOps / AIML 901 | Waymo claims 5× human safety, 2M miles/week; Uber hedges via partnerships — own the tech or own the customer |
| Uber ML Case — Predictive Surge Mitigation | Building Intelligent Products | How to frame a predictive model as a product decision; event-based surge is a pattern-recognition problem, not just a pricing one |
| Mars candy / AI model | Building Intelligent Products | An AI recommendation with a narrative (story + POV) beat a 196-slide McKinsey report — story is the delivery mechanism |
| Department Scoping Tracker | Building Intelligent Products | A well-written master prompt produced a working Flask + SQLite app in one pass; specification quality is the new code quality |
| EyeMax (Warby Parker smart glasses) | Research Design Build / Growth Innovation | Applied AI/hardware concept — see [9_projects_interests](9_projects_interests.md) for full project |

---

## Mental Models

**5% AI, 95% domain expertise.** The model is the commodity. The value is in choosing the right problem, owning the data, and driving adoption.

**Adding AI means redesigning the whole process.** An agent bolted onto an unchanged workflow fails. Go agent-first: redesign around what the agent can do.

**Verification time kills ROI.** If a human must re-check every AI output, you've added work, not removed it. Design for trust and verifiable outputs.

**Only verifiable tasks can be learned via RL.** Code, math, and reasoning improve through reward signals; empathy and open-ended judgment don't.

**"Heartbeat" agents.** Agents can run on scheduled, recurring triggers (a "heartbeat") to act autonomously over time rather than only on demand.

---

## My Notes & Updates
*Add new entries at the top. Format: [Month Year] — note*

[June 2026] — Major update: Added Building Intelligent Products course (Spring 2026) — all modules, guest lectures (Matt Yao), key project deliverables (Data PRD, Uber ML Case, Department Scoping Tracker master prompt), and ideation notes on the IT stakeholder alignment concept. Added AI for Product Leaders (Summer 2025) — prompt engineering patterns. Expanded cases table.

[June 2026] — File created from AI Foundations for Managers — AgentOps (AIML 901) class notes, plus AI industry briefs (industry landscape, Tech Crunch Disrupt). Added the Find It · Bottle It · Solve It framework.
