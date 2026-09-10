# Curriculum Audit and Rebuilt Full-Stack/FDE Roadmap

This document audits the core roadmap against current full-stack, product, AI, and Forward Deployed Engineer practice and proposes a more realistic progression.

The repository's existing [`ROADMAP.md`](ROADMAP.md) is treated as the baseline.

## Background

I started this roadmap to become a stronger full-stack developer: someone who can build both the user-facing frontend and the backend systems behind a product confidently, explain how they work, and make informed decisions instead of guessing. The goal is not simply to learn a list of technologies, but to understand how a product moves from an idea to a reliable, deployed application.

As I researched the kind of engineer I want to become, I realised that writing frontend and backend code is only the foundation. A strong product engineer must also understand how to turn a user problem into a product, deploy and operate that product, make sensible system-design decisions, and use AI where it genuinely improves the workflow. The important decision is not to jump straight into agents, RAG, or advanced infrastructure. The sequence should be deliberate: build strong full-stack foundations first, then add production engineering, then practical AI capabilities, and finally the customer-facing problem-solving skills associated with Forward Deployed Engineering.

This document captures that progression and keeps the focus on becoming a competent engineer rather than merely completing a curriculum.

## 1. External Curriculum Analysis

The external curriculum material is useful as a source of themes, but its breadth should not be treated as a personal checklist. The table below records topics worth considering; the sequencing and scope decisions in this document are recommendations.

### Topics identified for consideration

| Area | Verified topics |
|---|---|
| FDE foundations | Customer-embedded engineering, discovery, solution thinking, production Python, async Python, Pydantic, pytest, CI, and AI development tools |
| Backend | HTTP, REST, FastAPI, OAuth2, JWT, OIDC, RBAC |
| Data | PostgreSQL, JSONB, full-text search, `pgvector`, NoSQL, vector databases |
| Async systems | Celery, queues, Redis, WebSockets, SSE, serverless/event-driven workflows, and background workflows |
| Observability | OpenTelemetry, Grafana, logs, tracing |
| Cloud | AWS IAM, VPC, EC2, S3, RDS, SQS, KMS, Secrets Manager |
| DevOps | Docker, Kubernetes, EKS, Helm, GitHub Actions, ArgoCD, Terraform |
| AI | LLM APIs, prompting, RAG, embeddings, hybrid search, RAGAS evaluation, document processing, and AI-first frontend delivery |
| AI safety | Guardrails, prompt injection/security, latency, cost, model routing |
| Agents | Tool calling, structured outputs, MCP, human-in-the-loop, multi-agent systems |
| Integrations | Connector design, enterprise systems, API integration patterns, messy data, entity resolution, and an enterprise support-copilot build |
| FDE delivery | Discovery, PRD-lite, options matrix, risk register, demos, stakeholder communication |
| Reliability | Multi-tenancy, Postgres RLS, incident response, customer-facing RCA, load testing with k6, security/privacy, and go-live readiness |
| Capstone | Discovery → solution design → core build → integration → hardening → evaluation → demo day |

The wider material also includes DSA, SQL, Java/OOP, design patterns, Spring Boot, Kafka, Spark, Hadoop, Hive, Airflow, dbt, AWS, distributed systems, product management, and interview preparation. These are not one required path.

## 2. Lessons Worth Stealing

1. Engineering fundamentals should come before AI hype.
2. AI systems must be evaluated, not merely demoed.
3. Customer discovery is part of technical competence.
4. Production engineering includes deployment, monitoring, security, and incident handling.
5. One serious end-to-end capstone is more valuable than many disconnected tutorials.
6. Tool calling and integrations matter more than prompt syntax alone.
7. Architecture should be taught through failure modes:
   - slow database → indexes or caching;
   - long-running task → background job;
   - repeated client integration → connector abstraction;
   - unreliable AI output → structured output, evaluation, and guardrails.

## Independent Technical Verification

The progression below was checked against current primary documentation rather than copied from a course outline:

- FastAPI recommends learning its Tutorial before the Advanced User Guide. That supports using FastAPI as a limited, later AI-service layer rather than as a second full backend curriculum. ([FastAPI tutorial](https://fastapi.tiangolo.com/tutorial/), [Advanced User Guide](https://fastapi.tiangolo.com/advanced/))
- `pgvector` supports exact nearest-neighbour search by default and approximate HNSW/IVFFlat indexes as an explicit speed/recall trade-off. Learn ordinary PostgreSQL search first; add embeddings and indexing only when the project has a retrieval problem. ([pgvector documentation](https://github.com/pgvector/pgvector))
- Structured outputs enforce an application-defined JSON schema, while tool calling is a multi-step application-controlled loop. Learn schemas and validation before granting an AI a write-capable tool. ([Structured outputs](https://developers.openai.com/api/docs/guides/structured-outputs), [Function calling](https://developers.openai.com/api/docs/guides/function-calling))
- Evaluation requires a dataset and explicit testing criteria, so RAG evaluation belongs immediately after the first retrieval workflow—not as a final presentation step. ([Evals guide](https://developers.openai.com/api/docs/guides/evals))
- MCP standardises access to tools and resources but carries explicit consent, authorization, and data-sharing risks. It is an optional interoperability layer after ordinary tools are understood, not a prerequisite for the first AI feature. ([MCP specification](https://modelcontextprotocol.io/specification/latest))
- Incident response and postmortems are most useful after there is a deployed system with signals, a rollback path, and a deliberately injected failure. ([Google SRE incident management](https://sre.google/sre-book/managing-incidents/), [Google SRE postmortems](https://sre.google/sre-book/postmortem-culture/))

### Verification risks and changes

| Risk | Change |
|---|---|
| Two backend stacks create unnecessary context switching | Keep Node/TypeScript as the product backend; use Python/FastAPI only for a bounded AI service or experiment. |
| `pgvector` becomes cargo-cult infrastructure | Start with PostgreSQL full-text or metadata search; add embeddings, then compare exact and approximate retrieval on a small evaluation set. |
| RAG is declared successful because the demo sounds good | Track retrieval hit rate, answer support, refusal behaviour, latency, and cost on labelled examples. |
| Tool calling is treated as autonomous authority | Begin with read-only tools; add writes only with server-side authorization, validation, idempotency, audit logging, and explicit confirmation. |
| MCP adds protocol complexity without a real integration need | Learn the protocol conceptually and implement it only if the project needs a reusable external-tool boundary. |
| Incident response becomes theatre | Deploy first, add logs/health checks and a rollback note, then inject one failure and write a short blameless postmortem. |
| Tenant data leaks through retrieval filters | Make tenant/workspace filtering part of every retrieval query and test cross-tenant denial before tuning vector indexes. |

## 3. Things We Should Not Copy

Do not copy the reference programme's entire breadth into the core personal curriculum.

Defer:

- Kubernetes, EKS, and Helm.
- Terraform and GitOps.
- Multi-region AWS.
- Spark, Hadoop, and Hive.
- Airflow and dbt.
- Kafka and advanced event streaming.
- Multiple backend languages and frameworks.
- Java/Spring if Node/TypeScript is the primary stack.
- Advanced distributed consensus such as Raft.
- Fine-tuning and model quantisation.
- Multi-agent systems before single-agent/tool workflows are reliable.
- Full enterprise compliance implementation such as SOC2/GDPR.
- Advanced payment microservices.
- A full data-engineering specialisation.

## 4. Independent Feasibility Audit

The roadmap is directionally sound, but it still carries too many technologies and too many transitions for one person. This audit assumes an experienced software engineer who needs depth in a modern product stack, not beginner-level repetition.

### Concrete corrections

| Current proposal | Correction | Why |
|---|---|---|
| Vite/React first, then a separate Next.js phase | Use Next.js as the primary frontend after a short React fundamentals slice | A later rewrite duplicates routing, data fetching, deployment, and component work |
| Express API plus Next.js route handlers | Choose one backend boundary for the flagship app: a TypeScript Node API; use Next route handlers only for small web-facing concerns | Two API styles create avoidable architectural noise |
| DevDash, IssueBoard, then ClientFlow | Remove the separate DevDash and IssueBoard deliverables; turn their best features into vertical slices of the flagship | Three applications consume time without proving more engineering ability |
| A rushed web-foundations slice | Use a bounded foundations block before JavaScript: semantic HTML/forms, CSS/layout/responsiveness, then a static prototype and review | An experienced engineer can move quickly, but CSS and responsive layout still need enough repetition to be usable without copying |
| JavaScript days 11–30 followed by TypeScript days 31–40 | Start TypeScript during the first real application after a short JavaScript runtime review | TypeScript is the working language of the product stack; defer only syntax-heavy edge cases |
| PostgreSQL before the flagship begins | Move the first database-backed onboarding and delivery slice earlier; keep advanced indexing/performance after real queries exist | Database learning sticks when attached to the product’s actual data model |
| Next.js days 106–109 | Move Next.js to the start of the React phase and delete the later comparison phase | The current ordering teaches a framework after the product has already been built in another framework |
| Python/FastAPI as a second production backend | Add one small Python AI service only after the TypeScript product API is stable | Python is needed for AI integration, not as a second general-purpose backend curriculum |
| RAG, tool calling, agents, MCP, and evaluation in one AI phase | Sequence: LLM API → structured output → one tool → retrieval → evaluation/security; defer agents and MCP | Each step depends on the previous one; agents before reliable tools and evaluation are mostly demo work |
| Redis, WebSockets/SSE, queues, and background jobs as optional extras | Add at most one: a background job for document ingestion; use a managed queue only if deployment requires it | These are useful failure-mode exercises, but not four additional platform skills |
| Sentry plus structured logs plus OpenTelemetry/Grafana | Start with structured logs, health checks, and one error tracker; add traces only when debugging a real multi-step flow | Observability tools should answer a demonstrated question, not become a tooling tour |
| A large fixed-duration roadmap | Keep a flexible core; make advanced material optional | A deadline distracts from demonstrated competence |

### Revised scope

The executable target is the canonical numbered curriculum, designed for approximately six months at roughly 15–20 focused hours per week, or about 360–480 hours overall. The lesson numbers measure curriculum progress, not elapsed time or session count.

The minimum shippable flagship scope is:

1. Next.js/React frontend.
2. TypeScript product API.
3. PostgreSQL with authentication and workspace-level authorisation.
4. Tests, Docker, CI, deployment, logs, health checks, and one monitored production workflow.
5. One Python/FastAPI AI service with structured output, one explicitly authorised tool, retrieval over project documents, an evaluation set, and prompt-injection tests.

Everything beyond that is a stretch goal and must not delay the core release.

### Reordered phases

| Phase | Correction |
|---|---|
| Foundations | Git, semantic HTML/forms, CSS, accessibility, responsive UI, and a static prototype |
| Product frontend | JavaScript review, TypeScript, React, and a single application frontend |
| Backend/data | TypeScript API, PostgreSQL, authentication, validation, and tests |
| Production | Docker, CI, deployment, logs, health checks, and security |
| Optional advanced extension | Product discovery, system design, and bounded AI work after the core project has real evidence |
| Release and career | Reliability pass, case study, demo, interviews, and applications |

The product is defined in a PRD and prototype after the foundations phase. Its implementation grows continuously; there is no separate DevDash or IssueBoard release.

### Readiness gates

- Build a typed feature without following a tutorial.
- Ship a browser-to-database feature with authentication, validation, and tests.
- Deploy from a clean checkout and diagnose one intentionally injected failure.
- Explain an architecture decision and trade-off to a non-specialist.
- For any optional AI feature, show retrieval metrics and reject unsafe or malformed tool calls.
- Demo the system and defend what was deliberately left out.

If a gate fails, pause new topics and repair the relevant feature. Do not continue to the next technology merely because the sequence says so.

## 5. Existing Core Plan Audit

| Existing area | Decision | Reason |
|---|---|---|
| Git, HTML, CSS, accessibility | KEEP, REDUCE | Essential, but ten days is enough for a working foundation |
| JavaScript runtime | KEEP | Core to React, Node, and debugging |
| DevDash | REMOVE as separate project | Fold its best exercises into the flagship project |
| TypeScript | KEEP | Essential for modern product engineering |
| React | KEEP | Essential frontend skill |
| IssueBoard | REMOVE as separate project | Duplicate project; use the flagship application |
| Node/Express | REDUCE | Keep API/backend concepts without overbuilding a separate API |
| PostgreSQL/SQL | KEEP | High-value and directly useful |
| Authentication/authorisation | KEEP | Required for credible full-stack work |
| Testing | KEEP | Continuous practice, not a final phase only |
| Docker | KEEP | High-value production skill |
| CI/CD | KEEP | Use GitHub Actions initially |
| Sentry/logging | KEEP | Important operational skill |
| Next.js | REDUCE | Learn enough to build one feature, not a second full rewrite |
| System design | KEEP, SPREAD OUT | Learn through project failures |
| DSA | KEEP, REDUCE | Fundamentals and interview practice, not a marathon |
| ClientFlow | KEEP, REFRAME | Convert it into the onboarding and delivery-intelligence flagship product |
| Python | ADD | Needed for practical AI/FDE work |
| FastAPI | ADD, LIMITED | Use it for an AI service, not a second full backend stack |
| LLM APIs | ADD | Directly relevant |
| Structured outputs/tool calling | ADD | Higher-value than prompt tricks |
| RAG and evaluation | ADD | Core practical AI engineering |
| AI security | ADD | Prompt injection, data leakage, unsafe tools |
| FDE discovery/documentation | ADD | Differentiates FDE work from ordinary feature development |
| Redis | DEFER, then optional | Add only when the project demonstrates a real need |
| WebSockets/SSE | DEFER, then add one | Add only for a real notification or streaming feature |
| Kubernetes | DEFER | No need for one small application |
| Kafka/RabbitMQ | DEFER | Understand queue concepts first |
| Spark/Airflow/dbt | REMOVE from this roadmap | Data-engineering specialisation, not an immediate priority |

## 6. Workload Calculation

These estimates assume existing software-engineering experience rather than starting from zero.

| Topic | Learning | Practice | Project | Total |
|---|---:|---:|---:|---:|
| Web, Git, HTML, CSS | 20h | 20h | 25h | 65h |
| JavaScript runtime and browser APIs | 35h | 45h | 55h | 135h |
| TypeScript | 20h | 25h | 25h | 70h |
| React and frontend architecture | 35h | 45h | 65h | 145h |
| Node, HTTP, REST, and backend | 30h | 40h | 55h | 125h |
| PostgreSQL and SQL | 25h | 35h | 35h | 95h |
| Auth, security, and validation | 15h | 20h | 30h | 65h |
| Testing and debugging | 15h | 30h | 30h | 75h |
| Docker, CI, deployment, observability | 20h | 25h | 40h | 85h |
| System design and FDE practices | 25h | 25h | 25h | 75h |
| Python/FastAPI AI service | 25h | 30h | 35h | 90h |
| LLMs, structured output, RAG, evaluation | 35h | 45h | 55h | 135h |
| Interview and portfolio preparation | 15h | 35h | 10h | 60h |
| **Total** | **315h** | **420h** | **485h** | **1,220h** |

A sensible first target is an **800–900 hour curriculum**, excluding Kubernetes, advanced data engineering, multi-agent systems, and deep cloud infrastructure.

## 7. Workload boundaries

The core curriculum budgets about 480 focused hours at its recommended pace. The wider AI/FDE scope above is intentionally optional: add it only after the core project is deployed, explained, and supported by evidence.

## 8. Recommended pace

I recommend the core curriculum.

Preferred commitment:

- Minimum: 3 focused hours per study day.
- Ideal: 4 focused hours per study day.
- Recommended rhythm: roughly 5 focused learning sessions per learning week.
- Expected capacity: approximately 480 focused hours.

Familiar material can take less time; difficult material can use additional sessions.

Why numbered lessons?

- The core gives a focused full-stack foundation and production experience.
- It does not claim mastery of every cloud, FDE, and AI specialisation.
- Optional advanced material can follow once the core evidence is real.
- It avoids pretending that Kubernetes, RAG, and FDE client work can each be learned meaningfully in a few lessons.

## 9. Final Learning Stack

### Primary stack

- HTML
- CSS
- JavaScript
- TypeScript
- React
- Next.js
- Node.js
- Express
- PostgreSQL
- SQL
- REST APIs
- Authentication and authorisation
- Vitest/Playwright
- Docker
- GitHub Actions
- One cloud deployment platform
- Logs, health checks, and basic observability
- Python
- FastAPI
- LLM APIs
- Structured outputs
- Tool calling
- Embeddings
- PostgreSQL `pgvector`
- RAG
- RAG evaluation
- Prompt-injection defence
- Basic AI cost and latency measurement
- Customer discovery and technical documentation

### Explicitly not learning yet

- Kubernetes, EKS, Helm
- Terraform
- Kafka and RabbitMQ
- Spark, Hadoop, Hive
- Airflow and dbt
- Elasticsearch clusters
- Multi-region AWS
- Fine-tuning and model quantisation
- Complex multi-agent orchestration
- Advanced ML mathematics
- Multiple backend frameworks

## 10. Execution approach

The numbered lessons are a capability and effort estimate, not a fixed schedule. Detailed work is planned in rolling learning blocks, chosen from the active learning stack only after the preceding checkpoint is passed.

| Phase | Outcome |
|---|---|
| Web foundations | Semantic HTML/forms, CSS, accessibility, responsive layout, Git, browser debugging, and a static UI prototype |
| Product frontend | JavaScript, TypeScript, React, Next.js, client-side state, and frontend tests |
| Full-stack delivery | TypeScript API, PostgreSQL, authentication, authorisation, validation, and tests |
| Production and product delivery | Docker, CI, deployment, logs, health checks, security, discovery, and architecture decisions |
| Practical AI | Python/FastAPI, structured outputs, one safe tool, retrieval, evaluation, and AI security |
| Evidence and career readiness | Hardening, system explanation, case study, interview practice, and release |

Learning, building, review, and shipping should be separate session types. A learn day uses small disposable examples; a build day applies already-studied concepts; a review day rebuilds, tests, and documents; a ship day packages a finished slice. This prevents premature product implementation.

The active learning block, exact resources, and checkpoint rules live in [Engineering Growth Plan](ENGINEERING_GROWTH_PLAN.md). The product definition and Figma design brief live in [ClientFlow Assist PRD](CLIENTFLOW_ASSIST_PRD.md).

## 11. Flagship Project

Rename ClientFlow to **ClientFlow Assist — Client Onboarding & Delivery Intelligence**.

### Product

A multi-tenant workspace for small service teams that turns onboarding briefs, notes, and documents into human-reviewed delivery plans.

### Core features

- Users and workspaces
- Clients and onboarding briefs
- Delivery plans, projects, and tasks
- Notes/activity
- Search/filtering
- Authentication
- Authorisation
- Audit trail
- Notifications
- Document upload
- Source-grounded document questions
- AI-assisted extraction of requirements, risks, tasks, and owners into a review screen
- One explicitly approved action: create tasks from a reviewed delivery plan

### Architecture

```text
React/Next.js frontend
        |
Node/TypeScript product API
        |
PostgreSQL first; add `pgvector` when retrieval requires it
        |
Python/FastAPI AI service
        |
LLM provider + retrieval/tools
```

Start as a modular monolith. Add a separate Python service only when the AI feature needs it.

### Evolution

1. Write the [PRD](CLIENTFLOW_ASSIST_PRD.md) and create a full Figma prototype before product implementation.
2. Build web foundations with disposable HTML/CSS exercises, then recreate selected prototype screens as static evidence.
3. Add JavaScript domain state and interactions, then build the typed React/Next.js product frontend.
4. Add the Node API, PostgreSQL, authentication, workspace isolation, tests, Docker, deployment, logs, and health checks.
5. Add document ingestion, structured AI outputs, and one explicitly approved action.
6. Add embeddings and `pgvector` only after a full-text baseline exists, then add RAG and a labelled evaluation set.
7. Add retries, timeouts, cost/latency measurements, and guardrails; add MCP only if a reusable external-tool boundary is justified.
8. Simulate an incident, produce a blameless RCA, and present the project as an FDE-style engagement from discovery to demo.

Do not begin with agents. Begin with one reliable AI-assisted workflow.

The current resource map is maintained only in [Engineering Growth Plan](ENGINEERING_GROWTH_PLAN.md#free-resource-map) so the public documents do not drift apart.

## 12. Career Milestones

### Checkpoint 1 — Frontend/product-capable

Around Days 45–65.

Expected skills:

- Responsive accessible interfaces.
- JavaScript and TypeScript.
- React components and forms.
- Browser debugging.
- State and data-flow reasoning.

Possible roles: frontend engineer, React developer, product-engineer trainee.

### Checkpoint 2 — Junior full-stack capable

After the Backend and Data Engineering phase.

Expected skills:

- APIs and PostgreSQL schemas.
- Authentication.
- Frontend/backend testing.
- Deployment of a small application.

Possible roles: full-stack engineer, product engineer, backend-leaning application engineer.

### Checkpoint 3 — Strong full-stack/product foundation

Around Days 150–180.

Expected skills:

- Own a feature from requirements to production.
- Make architecture decisions.
- Diagnose performance and reliability issues.
- Explain trade-offs.
- Work with CI, Docker, and observability.

Possible roles: full-stack product engineer, software engineer, backend/product engineer.

### Checkpoint 4 — AI-enabled full-stack engineer

In the optional advanced extension.

Expected skills:

- Integrate LLMs safely.
- Use structured outputs and tools.
- Inspect retrieval pipelines.
- Evaluate AI quality.
- Measure latency and cost.
- Handle failures and fallbacks.

Possible roles: AI application engineer, applied AI engineer, AI product engineer.

### Checkpoint 5 — Entry-level FDE capability

After the flagship project is complete and defended.

Expected skills:

- Run a discovery conversation.
- Convert ambiguity into a scoped solution.
- Produce a PRD-lite, ADR, and risk register.
- Integrate with an external system.
- Deploy and monitor the result.
- Explain an incident to technical and non-technical audiences.

Possible roles: Forward Deployed Engineer, solutions engineer, AI implementation engineer, applied AI/product engineer.

Completing the roadmap does not make someone a senior FDE. FDE hiring also depends on communication, customer-facing judgement, domain knowledge, and evidence of operating in unfamiliar environments.

## 13. Final Verdict

### Is the core goal realistic?

Partly.

The core plan is realistic for:

- A strong full-stack foundation.
- One credible deployed project.
- React, TypeScript, Node, PostgreSQL, authentication, testing, and Docker basics.

It is not realistic for all of these at meaningful depth:

- Strong full-stack engineering.
- Cloud and DevOps.
- System design.
- FDE consulting.
- RAG evaluation.
- Tool calling.
- AI security.
- Agents and MCP.
- Incident response.
- Enterprise integration.

### Final decisions

Keep:

- JavaScript and TypeScript.
- React.
- Node and REST APIs.
- PostgreSQL and SQL.
- Authentication.
- Testing.
- Docker.
- Deployment.
- Debugging.
- Basic system design.
- One evolving flagship project.

Cut:

- DevDash and IssueBoard as separate major projects.
- Multiple backend stacks.
- Excessive DSA.
- Technology-tourism.
- Kubernetes and data engineering.
- Separate rewrites of the same application.

Postpone:

- Kubernetes.
- Kafka/RabbitMQ.
- Spark/Airflow/dbt.
- Multi-region AWS.
- Fine-tuning.
- Multi-agent systems.
- Advanced distributed systems.

Recommended pace: approximately six months at roughly four focused hours across five learning sessions per learning week. Move ahead after demonstrated competence, not after time spent.

The key change is not adding more technologies. It is replacing several small projects with one evolving product that demonstrates engineering, production delivery, AI integration, and FDE-style problem solving.
