# Full-Stack, Systems, and Applied AI Engineering Roadmap

This curriculum targets approximately six months of sustained part-time learning: roughly 15–20 focused hours per week and about 360–480 hours overall. These are workload estimates, not deadlines.

The detailed plan currently runs from **Day 1 through Day 152**. That count emerged from the learning clusters, milestone projects, integration work, and reviews; it was not selected in advance.

## Learning model

A numbered **Day** is a curriculum unit, not a calendar day or fixed study session. Lessons use four different modes:

- **Learn** — follow a bounded resource section and complete its built-in examples, exercises, or checks.
- **Milestone** — combine several recent lessons in a meaningful project or feature.
- **Integration** — connect previously separate capabilities, debug their boundaries, and make trade-offs.
- **Review** — retrieve concepts from memory, repair gaps, and decide whether to continue or slow down.

Most Learn lessons do not invent a second assignment when the resource already provides good practice. Substantial evidence is concentrated in milestones and integrations. Familiar lessons may be combined; difficult lessons may use multiple sessions.

Concepts appear when there is something concrete to attach them to:

- Git starts with saving work; branches and pull requests arrive after the first real project exists.
- The web begins with a simple browser/request mental model; HTTP deepens when Fetch and APIs make it visible; DNS, TLS, and proxies arrive during deployment.
- Testing begins when reusable logic and real regressions exist.
- Caching, queues, distributed failure, and AI agents appear only after the product exposes the problem they solve.

## Curriculum at a glance

| Phase | Sequence | Approximate workload | Capability milestone |
|---|---:|---:|---|
| 1. Foundations | Days 1–32 | 55–75 hours | Build and deploy an accessible HTML/CSS/JavaScript portfolio and API-powered browser feature |
| 2. Modern Application Engineering | Days 33–55 | 55–70 hours | Build and test a typed React frontend and understand its Node boundary |
| 3. Backend and Data Engineering | Days 56–84 | 70–95 hours | Ship an authenticated browser-to-database workflow with safe background work |
| 4. Production and Systems Engineering | Days 85–109 | 60–85 hours | Deploy, observe, secure, measure, and recover a production-style system |
| 5. Applied AI Engineering | Days 110–133 | 60–80 hours | Add an evaluated, source-grounded AI workflow with constrained tools and safe failures |
| 6. Integration, FDE Skills, Portfolio, and Interviews | Days 134–152 | 55–75 hours | Defend the complete system, communicate trade-offs, and present credible engineering evidence |
| **Total** | **Days 1–152** | **Approximately 360–480 hours** | **Deliver and explain a production-style AI-enabled full-stack product** |

## Phase 1 — Foundations

### Learning clusters

- Terminal navigation and enough Git to save and inspect work.
- Semantic HTML, native forms, and HTML accessibility.
- CSS cascade, layout, responsive design, and visual/keyboard accessibility.
- JavaScript values, control flow, functions, collections, modules, DOM, events, persistence, async work, Fetch, and contextual HTTP.
- Browser developer tools and debugging throughout the project milestones.

### Milestones

1. **HTML milestone:** build a semantic multi-page site without styling.
2. **HTML/CSS milestone:** turn it into an accessible responsive portfolio.
3. **Git workflow integration:** add a real portfolio feature through an issue, branch, pull request, and merge.
4. **JavaScript fundamentals milestone:** complete a small data-focused program from requirements.
5. **Browser JavaScript milestone:** add useful interaction and persistence.
6. **API milestone:** add a resilient remote-data feature and explain the observed HTTP exchange.
7. **Foundation review:** deploy, debug, and rebuild a representative slice from memory.

## Phase 2 — Modern Application Engineering

### Learning clusters

- JavaScript execution, closures, prototypes, asynchronous ordering, and testing.
- Strict TypeScript and domain/state modelling.
- React component design, state, forms, effects, routing, accessibility, and behaviour-focused tests.
- Node runtime and raw HTTP introduction after the frontend creates a reason for a backend.

### Milestones

1. **DevDash:** build, test, and deploy a browser application using DOM, persistence, and remote data.
2. **TypeScript migration:** convert a working slice and document bugs caught by strict types.
3. **ClientFlow frontend:** build realistic typed React workflows with loading, validation, and failure states.
4. **Application-engineering review:** demo the frontend from memory and explain its state and network boundaries.

## Phase 3 — Backend and Data Engineering

### Learning clusters

- Express routing, middleware, REST contracts, validation, errors, and API tests.
- PostgreSQL querying, joins, aggregates, schemas, constraints, migrations, transactions, indexes, and query plans.
- Authentication, sessions, authorisation, and workspace isolation.
- Background processing, retries, idempotency, and worker failure.

### Milestones

1. **API milestone:** implement and test a validated in-memory resource API.
2. **SQL milestone:** answer product questions using a deliberately designed relational schema.
3. **Persistence milestone:** connect the API to PostgreSQL and justify one measured index.
4. **Authentication milestone:** prove login and cross-workspace denial end to end.
5. **Background-work milestone:** process a durable job safely under retry and duplicate delivery.
6. **Full-stack milestone:** ship a complete ClientFlow browser → API → database workflow.

## Phase 4 — Production and Systems Engineering

### Learning clusters

- Containers, configuration, CI/CD, deployment, processes, DNS, TLS, and reverse proxies.
- Logs, health checks, metrics, traces, and error monitoring.
- Threat modelling, web security, abuse controls, and dependency hygiene.
- Caching, queues, performance, timeouts, retries, backups, service objectives, incidents, and system design.

### Milestones

1. **Deployment milestone:** start from a clean checkout and deploy through a repeatable workflow.
2. **Observability milestone:** diagnose a hidden failure using system signals.
3. **Security milestone:** turn a threat model into reproduced tests and fixes.
4. **Performance/reliability integration:** measure a bottleneck, rehearse recovery, and explain the trade-off.
5. **Production milestone:** operate the capstone through an injected incident.

## Phase 5 — Applied AI Engineering

### Learning clusters

- AI use-case selection, LLM APIs, prompting, structured outputs, and validation.
- Application-controlled tool calling with authorisation and human confirmation.
- Evaluation datasets, scoring, embeddings, ingestion, vector/lexical retrieval, RAG, and citations.
- Failure analysis, prompt injection, guardrails, tenant isolation, observability, MCP, and agentic trade-offs.

### Milestones

1. **Structured extraction:** turn a client brief into validated, reviewable domain data.
2. **Tool boundary:** expose one authorised read and one confirmed write without delegating authority to the model.
3. **Retrieval milestone:** ingest documents, retrieve relevant authorised sources, and evaluate ranking quality.
4. **Grounded workflow:** generate cited output and measure support, refusal, latency, and cost.
5. **MCP integration:** expose one narrow capability while preserving application security.
6. **Applied AI milestone:** demonstrate evaluated quality, safe failures, constrained agency, and a written case for when not to use an agent.

## Phase 6 — Integration, FDE Skills, Portfolio, and Interview Readiness

### Learning clusters

- End-to-end architecture, distributed failure, consistency, scalability, and reliability.
- Technical discovery, requirements, decomposition, options, architecture decisions, proposals, and stakeholder communication.
- Capstone security, AI quality, performance, accessibility, recovery, documentation, and incident hardening.
- Portfolio evidence plus selective DSA, SQL, debugging, and system-design practice.

### Milestones

1. **FDE delivery simulation:** move from discovery through proposal to a small external integration and stakeholder demo.
2. **Release-candidate hardening:** rerun security, AI, performance, reliability, accessibility, and end-to-end checks.
3. **Operational evidence:** publish onboarding documentation, runbooks, and a customer-facing incident analysis.
4. **Portfolio milestone:** publish a case study and architecture walkthrough grounded in measured evidence.
5. **Final assessment:** release the capstone and defend its product, engineering, AI, and operational trade-offs.

## Project progression

| Project | Role in the curriculum | Completion evidence |
|---|---|---|
| Portfolio Foundation | Integrates HTML, CSS, accessibility, browser debugging, Git workflow, JavaScript, Fetch, and deployment | Public URL, milestone notes, responsive/keyboard checks, merged feature PR, debugging record |
| DevDash | Integrates deeper JavaScript, browser APIs, persistence, async states, tests, and TypeScript | Deployed app, failure-state handling, regression tests, typed migration |
| ClientFlow Assist | Evolves from React frontend through backend/data, production, AI, and FDE work | Deployed product, tests, telemetry, recovery proof, evaluation report, security evidence, case study, demo |

## Progress tracking

```text
Current lesson: Day 1 — Terminal Orientation
Completed: 0 / 152
Current phase: Phase 1 — Foundations
Next milestone: HTML Milestone
```

The complete resource-led sequence is in [`STUDY_PLAN.md`](STUDY_PLAN.md).
