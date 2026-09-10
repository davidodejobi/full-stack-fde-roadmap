# Engineering Growth Plan: Full-Stack to AI Product Engineering

## Why this plan exists

I started this journey to become a stronger full-stack engineer: someone who can build the user-facing frontend and the backend systems behind a product confidently, explain how they work, and make informed decisions instead of guessing.

I already write software professionally. I have also studied parts of Python and AI engineering before, but I did not yet use many of those skills deeply enough for them to become dependable. This plan therefore treats some subjects as a focused rebuild, not as a first introduction. Prior experience should help me move faster, but it does not replace the need to build, debug, and explain the work.

The destination is not “I know many tools.” It is: I can take an ambiguous product problem, clarify it, design a sensible solution, build and test it, deploy and operate it, add AI only where it is useful, and explain the trade-offs to both engineers and non-engineers.

That is the progression in this document:

```text
Full-stack foundation → product delivery → production engineering
→ practical AI features → customer-facing engineering judgement
```

The order is intentional. Advanced AI, agents, and infrastructure are not shortcuts around engineering fundamentals.

## What the roles mean

| Role | Practical meaning |
|---|---|
| Frontend engineer | Builds usable, accessible interfaces and understands browser behaviour. |
| Backend engineer | Designs APIs, data models, authentication, business rules, and reliable server-side systems. |
| Full-stack engineer | Can deliver a feature across interface, API, database, tests, and deployment boundaries. |
| Product engineer | Adds product judgement: turns user problems into small, useful, measurable solutions. |
| AI product engineer | Builds normal software first, then integrates LLMs, retrieval, tools, evaluation, security, latency, and cost controls responsibly. |
| Forward Deployed Engineer (FDE) | Works close to a customer or business workflow: discovers the problem, scopes a solution, integrates with real systems, ships it, and owns its reliability and communication. |

This is a progression, not a set of titles automatically earned by completing a document.

## Relationship to the core curriculum

[`ROADMAP.md`](ROADMAP.md) is the canonical curriculum. It is designed for approximately six months at roughly 15–20 focused hours per week, or about 360–480 hours overall. Its numbered days are progress markers, not dates or fixed-length sessions.

This document is an optional scope reference for work that may follow the core curriculum. Use its topics only when they support the next capability; do not treat its learning blocks as a deadline or a required sequence.

## What changed from the first roadmap

| Earlier approach | Correction in this plan | Reason |
|---|---|---|
| A fixed-duration sprint for frontend, backend, production, AI, and career preparation | A flexible core curriculum with optional advanced topics | Evidence and understanding matter more than an artificial deadline. |
| Several separate applications | One evolving flagship product | A single product creates connected evidence of architecture, delivery, debugging, and iteration. |
| Next.js near the end, after a separate React application | React fundamentals first, then Next.js during the main frontend phase | Avoids a late rewrite of routing, data fetching, and deployment work. |
| Node/Express plus a possible full Python backend | TypeScript remains the product backend; Python/FastAPI is a limited AI-service layer | Avoids learning two general-purpose backend stacks at once. |
| AI topics gathered into a large late phase | LLM API → structured output → one safe tool → retrieval → evaluation → reliability | Each layer needs the previous one to be trustworthy. |
| Separate daily recall, practice, and DSA blocks | Recall and practice are tied to the current feature; DSA is small and spread across the plan | Keeps effort connected to actual engineering work instead of creating a second curriculum. |
| Tool coverage as the goal | Depth, evidence, and readiness gates as the goal | Knowing when not to use a technology is part of engineering judgement. |

## Scope: what is in and what is deliberately out

### The learning stack

- HTML, CSS, accessibility, Git, and GitHub
- JavaScript and TypeScript
- React and Next.js
- HTTP, REST, Node.js, and a TypeScript API
- PostgreSQL, SQL, schema design, indexes, and transactions
- Authentication, authorisation, validation, testing, and debugging
- Docker, CI, deployment, logs, health checks, and basic monitoring
- Product discovery, PRD-lite documents, ADRs, trade-offs, and incident communication
- Python and FastAPI for a bounded AI service
- LLM APIs, structured outputs, safe tool calling, embeddings, retrieval, RAG evaluation, AI security, latency, and cost

### Not yet

- Kubernetes, EKS, Helm, Terraform, and GitOps
- Kafka, RabbitMQ, Spark, Hadoop, Hive, Airflow, dbt, and data-engineering platforms
- Multi-region cloud architecture and advanced distributed-systems theory
- Fine-tuning, model quantisation, advanced ML mathematics, and multi-agent systems
- Multiple competing backend frameworks

These are not bad technologies. They are simply not the highest-return work before one application has been built and operated well.

## The flagship project: ClientFlow Assist — Client Onboarding & Delivery Intelligence

The whole plan centres on one evolving product instead of a parade of tutorial applications.

**ClientFlow Assist** helps a small service team turn a client brief, meeting notes, and onboarding documents into a human-reviewed delivery plan. It is a multi-tenant workspace for the client-onboarding and project-delivery workflow—not a generic CRM.

It will eventually support:

- users and workspaces;
- clients, onboarding briefs, projects, tasks, notes, and activity;
- search, filtering, and permissions;
- authentication and workspace-level authorisation;
- document upload, processing, and source references;
- AI-assisted extraction of requirements, risks, tasks, and owners into a review screen;
- source-grounded document questions and explicitly approved task creation;
- tested, deployed, observable workflows.

### Architecture at the end

```text
Next.js / React frontend
          |
TypeScript product API
          |
PostgreSQL + pgvector when retrieval needs it
          |
Small Python / FastAPI AI service
          |
LLM provider, retrieval, and one explicitly authorised tool
```

Start as a modular monolith. A separate Python service is added only when the AI feature gives it a real reason to exist.

## How each four-hour day works

Learning, building, and review are deliberately separated into different kinds of days. This prevents a new concept from being copied straight into the flagship product before it is understood.

| Day type | Four-hour focus |
|---|---|
| Learn | Study one bounded topic, make small isolated examples, and explain the concept in notes. Do not add a flagship feature. |
| Build | Implement a feature using concepts already studied. Use documentation for reference and debug real problems, but do not start a new tutorial. |
| Review | Rebuild a small part from memory, test failure cases, inspect/debug, document decisions, and identify the next gap. Do not add a new feature. |
| Ship | Package a finished slice: Git workflow, deployment, README, demo, or release checks. This may include light fixes, not a new learning topic. |

The overall plan still aims for roughly 20% learning, 60% building, and 20% debugging/review across a block—not inside every individual day.

There is no separate daily “recall” project and no forced LeetCode block. Recall happens on review days. Practice is tied to the current work:

- early weeks: rebuild HTML/CSS/JavaScript concepts from memory;
- backend weeks: SQL, API, validation, and testing exercises;
- later weeks: focused DSA/interview practice twice weekly;
- AI weeks: labelled evaluation cases, unsafe-input tests, and failure handling.

### If available time changes

| Available time | Use it for |
|---:|---|
| 2 hours | Keep the lesson's single purpose; continue it in another session rather than combining learning and building. |
| 3 hours | One bounded learn/build/review/ship session; this is the sustainable minimum. |
| 4 hours | The default single-purpose session above. |
| 5 hours | Add a deeper implementation or review pass; do not add a second topic. |

## Rules for using AI while learning

1. I design and attempt the solution before asking for implementation help.
2. I can use AI to explain, review, debug, generate test cases in some cases after I know what is going on, or point me to relevant documentation.
3. I do not merge code I cannot explain or validate.
4. For core exercises and major project features, I write the implementation myself first.
5. Every AI-assisted feature needs explicit validation, error handling, and a documented decision.

## Working rhythm

The current learning block—not a day-of-week template—decides what each study session is for. A learning week is a curriculum grouping, not a literal calendar week. Some sessions are concept-heavy; others are almost entirely implementation, debugging, or review.

- Plan roughly five focused sessions per learning week when practical.
- Use the single-purpose day structure above within each session.
- Use any remaining time for rest, light catch-up, or no work; it is not a required study session.
- End each learning block with the stated checkpoint and a short retrospective: what shipped, what can be explained without notes, what remains unclear, and what the next block should address.

If a checkpoint fails, repair the missing skill before choosing the next block. Evidence overrules sequence speed.

## Rolling planning system

The long-term scope, learning stack, flagship project, resource map, and career checkpoints remain the direction of travel. Detailed daily tasks exist only for the next three weeks.

At the end of each learning block, review the checkpoint and plan the next block from the active learning stack. Do not advance because a sequence marker says so. Extend a topic that remains weak; move forward when the evidence is real.

### How to plan the next block

1. Choose one capability from the learning stack that unlocks the next product slice.
2. Choose the minimum chapters, lessons, and exercises from the resource map; never assign an entire course by default.
3. Define one small working deliverable and one checkpoint that tests whether it is understood.
4. Use the final study day to rebuild, debug, document, and decide what comes next.

### Long-term direction, without a fixed pace

| Phase | Capability to earn | Evidence before moving on |
|---|---|---|
| 1. Web foundations | Semantic HTML, CSS, accessibility, responsive layout, Git, and browser debugging | A deployed static page rebuilt and explained without a tutorial |
| 2. Product frontend | JavaScript, TypeScript, React, Next.js, client-side state, and frontend tests | A typed, accessible product frontend with clear loading and error states |
| 3. Full-stack delivery | HTTP, TypeScript API, PostgreSQL, SQL, authentication, authorisation, and tests | An authenticated browser-to-database workflow that survives refresh and failure cases |
| 4. Production and product delivery | Docker, CI, deployment, logs, health checks, security, requirements, and architecture decisions | A deployed product with operational evidence and concise product/technical documents |
| 5. Practical AI | Python, FastAPI, structured outputs, one safe tool, retrieval, evaluation, and AI security | A human-reviewed document-to-delivery workflow with measured quality and safe action boundaries |
| 6. Evidence and career readiness | Hardening, system explanation, portfolio case study, interview practice, and release | A shareable project and a clear defence of its trade-offs |

### Block 1 — Web foundations and a static product page (Learning Weeks 1–3)

This block builds enough HTML, CSS, accessibility, Git, and browser-debugging skill to make and deploy a simple, responsive ClientFlow Assist landing/onboarding page. It does not attempt to finish HTML, CSS, or visual design.

#### Learning Week 1 — Semantic HTML and accessible forms

**Use this week:** [MDN Structuring content with HTML](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content), [MDN Web forms](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms), [GitHub Skills](https://skills.github.com/), and the [Pro Git book](https://git-scm.com/book/en/v2).

| Day | Work |
|---:|---|
| 1 | Set up the repository, Git identity, lesson format, and first commit. Use `status`, `add`, `commit`, `log`, and `push`. **Completed.** |
| 2 — Learn | Study HTML document structure and semantic landmarks in small isolated examples: `header`, `nav`, `main`, `section`, and `footer`. |
| 3 — Learn | Study content and form semantics: headings, links, lists, images/alternative text, `form`, `label`, `input`, `textarea`, `select`, and `button`. Build only disposable examples. |
| 4 — Build | Build the unstyled ClientFlow Assist page: landmarks, meaningful content, links, lists, and one image with accurate alternative text. |
| 5 — Build | Add a client-request form with name, email, project type, and message. Use native input types and validation; test it with only a keyboard. |
| 6 — Review | Rebuild one semantic content section and the form from a blank file. Record what you could not recall and commit the evidence. |

**Checkpoint:** Explain why the page uses landmarks, headings, labels, and buttons; navigate and complete the form with only a keyboard.

#### Learning Week 2 — CSS foundations, layout, and responsiveness

**Use this week:** [MDN CSS styling basics](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics), [MDN Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox), [MDN Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout), and [web.dev responsive design](https://web.dev/learn/design/).

| Day | Work |
|---:|---|
| 1 — Learn | Study selectors, inheritance, cascade, specificity, box model, and spacing in isolated examples. |
| 2 — Learn | Study typography, colour, interactive states, and Flexbox. Build small throwaway layout examples only. |
| 3 — Build | Style the existing page with a readable type scale, spacing, colour, borders, and visible focus states. |
| 4 — Build | Build the header/navigation and a row of delivery-workflow cards with Flexbox. |
| 5 — Learn | Study mobile-first responsiveness, media queries, and Grid in isolated examples. Decide which existing layout should use each tool. |
| 6 — Review | Rebuild one Flexbox layout from memory, test at narrow and wide widths, and note when Grid is a better choice. |

**Checkpoint:** The page remains usable on phone and desktop widths; you can explain the box model, cascade, Flexbox, and when Grid is a better choice.

#### Learning Week 3 — Build, debug, review, and deploy

**Use this week:** the resources from Weeks 1–2; [web.dev accessibility](https://web.dev/learn/accessibility/); [MDN browser developer tools](https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Tools_and_setup/What_are_browser_developer_tools); and [GitHub Pages documentation](https://docs.github.com/en/pages).

| Day | Work |
|---:|---|
| 1 — Plan | Choose one simple page reference or make a low-fidelity wireframe. Define the content and layout before coding. |
| 2 — Build | Build the full static ClientFlow Assist page: hero, workflow explanation, delivery-plan cards, and request form. |
| 3 — Build | Apply responsive behaviour from the approach already studied. Do not begin a new CSS topic. |
| 4 — Review | Run keyboard/accessibility checks and use DevTools to diagnose three HTML/CSS problems. Document the diagnosis and fix. |
| 5 — Ship | Create an issue and branch for one improvement, open a pull request, merge it, deploy the page, and verify the deployed version. |
| 6 — Review | Rebuild one section without copying, write a short README/retrospective, and decide the exact JavaScript outcome for the next block. |

**Checkpoint:** A public static page works at multiple widths, supports keyboard navigation, has a clear Git history, and can be explained without following a tutorial.

<!-- Historical fixed 35-week schedule retained only as a source reference. It is not an active instruction set; the rolling three-week system above governs the plan. -->

<!--

## Superseded fixed 35-week schedule

### Phase 1 — Web and product foundations (Learning Weeks 1–2)

#### Learning Week 1 — Git, semantic HTML, and CSS foundations

| Day | Work |
|---:|---|
| 1 | Set up the repository, Git identity, lesson format, and first commit. Use `status`, `add`, `commit`, `log`, and `push`. |
| 2 | Build a semantic ClientFlow Assist landing page for the onboarding-to-delivery workflow, with headings, landmarks, links, lists, and meaningful image alternatives. |
| 3 | Build an accessible contact/request form with labels, native validation, keyboard navigation, and helpful input types. |
| 4 | Apply CSS selectors, cascade, spacing, box model, colours, and typography to the page. |
| 5 | Build a header/navigation and card layout using Flexbox. |
| 6 | Review from a blank file: rebuild one semantic section and one Flexbox layout; commit the first foundation evidence. |

**Checkpoint:** Explain why `header`, `main`, `section`, `label`, and `button` are used; navigate the page with only a keyboard.

#### Learning Week 2 — Grid, responsive design, accessibility, and delivery

| Day | Work |
|---:|---|
| 1 | Build a responsive dashboard shell with CSS Grid: header, navigation, content, and activity panel. |
| 2 | Make the shell mobile-first and usable at phone, tablet, and desktop widths. |
| 3 | Audit heading order, focus visibility, colour contrast, alt text, and form error behaviour. Fix what fails. |
| 4 | Learn the browser inspector and DevTools; diagnose three deliberately introduced HTML/CSS problems. |
| 5 | Use an issue, branch, pull request, and merge for one accessibility or layout improvement. |
| 6 | Deploy the static foundation and write a short README explaining how it was built and reviewed. |

**Checkpoint:** A public page works at three widths, passes keyboard-only navigation, and has a clean GitHub workflow.

### Phase 2 — JavaScript, TypeScript, React, and Next.js (Learning Weeks 3–11)

#### Learning Week 3 — JavaScript runtime refresh

| Day | Work |
|---:|---|
| 1 | Review values, types, `const`, `let`, operators, coercion, and equality through small domain calculations. |
| 2 | Implement task-status and project-priority decisions with conditions and loops. |
| 3 | Write pure functions for dates, statuses, totals, and validation results. |
| 4 | Model clients, projects, and tasks with arrays and objects; practise immutable updates. |
| 5 | Use modules and npm scripts to organise the domain utilities. |
| 6 | Test utilities manually and with a small test runner; explain scope, parameters, return values, and references. |

**Checkpoint:** Build a small domain-utility module from a blank file and predict its output before running it.

#### Learning Week 4 — Browser programming and persistence

| Day | Work |
|---:|---|
| 1 | Render a task list from JavaScript data using DOM APIs. |
| 2 | Add create, update-status, and delete interactions through event handlers. |
| 3 | Build browser-side form validation with accessible error messages. |
| 4 | Persist a small task list with `localStorage`; handle missing or invalid stored data. |
| 5 | Use DevTools breakpoints, network inspection, and console logging to repair five bugs. |
| 6 | Write tests for the pure task utilities and document what DOM code is harder to test. |

**Checkpoint:** Refreshing the page preserves valid local tasks; bad stored data does not crash the page.

#### Learning Week 5 — Async JavaScript and HTTP

| Day | Work |
|---:|---|
| 1 | Review callbacks, promises, `async`/`await`, and the event loop using small controlled examples. |
| 2 | Fetch and render data from one public API with loading, error, empty, and success states. |
| 3 | Learn HTTP methods, JSON, status codes, request headers, and browser network tooling. |
| 4 | Add cancellation or stale-response protection to an asynchronous search interaction. |
| 5 | Build a small mock service or static JSON adapter for onboarding briefs, delivery plans, and tasks. |
| 6 | Explain the request lifecycle and write one failure-state test or reproducible debugging note. |

**Checkpoint:** The UI remains understandable when the request is slow, fails, or returns no usable data.

#### Learning Week 6 — TypeScript fundamentals in the real project

| Day | Work |
|---:|---|
| 1 | Add TypeScript tooling and strict configuration to the project. |
| 2 | Type Client, OnboardingBrief, DeliveryPlan, Task, and Workspace domain objects. |
| 3 | Model loading, success, empty, and error states with discriminated unions. |
| 4 | Type functions, API-shaped data, and validation results without `any`. |
| 5 | Use generics only for one genuine reusable collection/helper need. |
| 6 | Fix compiler errors deliberately and document one type error that prevented a runtime bug. |

**Checkpoint:** Strict TypeScript builds cleanly and the application has no unexplained `any` types.

#### Learning Week 7 — React fundamentals

| Day | Work |
|---:|---|
| 1 | Build React components from the existing dashboard shell and explain component boundaries. |
| 2 | Use props, state, events, lists, keys, and conditional rendering for client, brief, and delivery-plan data. |
| 3 | Build controlled forms for creating a client and task. |
| 4 | Lift state only where two components genuinely need it. |
| 5 | Use effects only for external synchronisation; implement one fetch flow with cleanup/error handling. |
| 6 | Rebuild one small component from memory and test its key behaviour. |

**Checkpoint:** Explain props versus state, controlled inputs, keys, and when an Effect is needed.

#### Learning Week 8 — Next.js as the product frontend

| Day | Work |
|---:|---|
| 1 | Create the Next.js application structure, layout, navigation, and route conventions. |
| 2 | Move the dashboard shell and typed components into Next.js. |
| 3 | Build client, onboarding-brief, delivery-plan, and task-detail routes. |
| 4 | Learn server versus client components by making one deliberate split. |
| 5 | Add route-level loading, empty, error, and not-found states. |
| 6 | Deploy a preview and explain the rendering/data-boundary choices. |

**Checkpoint:** The application has clear routes and no accidental client component where a server component is sufficient.

#### Learning Week 9 — Frontend product workflows

| Day | Work |
|---:|---|
| 1 | Build typed create/edit client forms with validation feedback. |
| 2 | Build project and task lists with filters, sorting, and URL query state. |
| 3 | Add pagination UI against mock data and preserve filter state on navigation. |
| 4 | Add optimistic or pending UI for one safe update. |
| 5 | Improve accessible table/list interactions and keyboard behaviour. |
| 6 | Test the highest-value frontend workflows. |

**Checkpoint:** A user can create, find, edit, and review an onboarding brief and delivery plan without losing state.

#### Learning Week 10 — Frontend architecture and quality

| Day | Work |
|---:|---|
| 1 | Decide what belongs in local component state, URL state, and server data. Record the decision. |
| 2 | Extract one useful custom hook or helper only where duplication exists. |
| 3 | Add a reusable error display and accessible notification pattern. |
| 4 | Measure and fix one needless re-render or poor loading experience. |
| 5 | Run an accessibility pass on primary flows. |
| 6 | Record a short frontend architecture decision record (ADR). |

**Checkpoint:** Explain why each major state category lives where it does.

#### Learning Week 11 — Frontend consolidation and DSA baseline

| Day | Work |
|---:|---|
| 1 | Review Big O, arrays, strings, hash maps, and sorting/searching through JavaScript implementations. |
| 2 | Solve two practical problems involving arrays/objects and explain complexity. |
| 3 | Review recursion, stacks, queues, and linked-list concepts; implement a small stack/queue. |
| 4 | Build a lightweight algorithm visualisation or domain simulation only if it supports learning. |
| 5 | Finish frontend tests, fix bugs, and improve README screenshots/demo instructions. |
| 6 | Demonstrate the frontend from memory and identify backend requirements before building the API. |

**Checkpoint:** Explain Big O for common operations and demonstrate a typed frontend feature without a tutorial.

### Phase 3 — Backend, PostgreSQL, and trustworthy vertical slices (Learning Weeks 12–18)

#### Learning Week 12 — Node, HTTP, and API boundaries

| Day | Work |
|---:|---|
| 1 | Review Node runtime, environment variables, modules, and package scripts. |
| 2 | Build a small raw HTTP handler to understand request/response boundaries. |
| 3 | Create the TypeScript API service structure and health endpoint. |
| 4 | Define REST resources and status-code conventions for workspaces, clients, projects, and tasks. |
| 5 | Build the first typed route and connect it to the frontend through a clear API client. |
| 6 | Document the request path from browser to API and back. |

**Checkpoint:** Explain how one browser action becomes an HTTP request, route handler, response, and UI update.

#### Learning Week 13 — Express, validation, and error handling

| Day | Work |
|---:|---|
| 1 | Add Express routing, controllers, and service boundaries without needless abstractions. |
| 2 | Add runtime request validation for one create/update route. |
| 3 | Add central error mapping and stable error-response shapes. |
| 4 | Add structured request logging with safe fields only. |
| 5 | Build CRUD routes for clients and write API tests. |
| 6 | Intentionally send invalid input and verify the API rejects it clearly. |

**Checkpoint:** Invalid input, missing records, and unexpected errors return safe, predictable responses.

#### Learning Week 14 — PostgreSQL and relational modelling

| Day | Work |
|---:|---|
| 1 | Install/connect PostgreSQL and create the first database. |
| 2 | Model workspaces, users, clients, projects, and tasks with keys and constraints. |
| 3 | Write `SELECT`, `WHERE`, ordering, limits, and pagination queries. |
| 4 | Write joins that support the dashboard’s actual data needs. |
| 5 | Add migrations and repeatable seed data. |
| 6 | Draw the ERD and explain why each relationship and constraint exists. |

**Checkpoint:** Recreate the schema from migrations and write a query joining clients, projects, and tasks.

#### Learning Week 15 — SQL depth and persistence

| Day | Work |
|---:|---|
| 1 | Add aggregates, grouping, and dashboard summary queries. |
| 2 | Use transactions for one multi-step data change. |
| 3 | Add indexes based on an actual list/search query. |
| 4 | Compare `EXPLAIN ANALYZE` before and after the index; document the result. |
| 5 | Connect the API to PostgreSQL for onboarding briefs, delivery plans, and tasks. |
| 6 | Test a real browser → API → database vertical slice. |

**Checkpoint:** Explain what a transaction and index do, and show one query-plan comparison.

#### Learning Week 16 — Authentication and workspace authorisation

| Day | Work |
|---:|---|
| 1 | Choose session or token authentication and record the decision. |
| 2 | Implement registration, login, logout, and secure password hashing. |
| 3 | Add authenticated request handling and current-user identity. |
| 4 | Add workspace membership and role/ownership checks. |
| 5 | Test that one user cannot access or change another workspace’s records. |
| 6 | Review authentication versus authorisation and document the security model. |

**Checkpoint:** Cross-workspace reads and writes are denied by server-side tests.

#### Learning Week 17 — API quality, integration, and tests

| Day | Work |
|---:|---|
| 1 | Add server-driven filtering, sorting, and pagination. |
| 2 | Add consistent API documentation and examples. |
| 3 | Connect the Next.js forms and lists to live authenticated data. |
| 4 | Add integration tests for critical onboarding-brief, delivery-plan, and task flows. |
| 5 | Test error states in the browser and API. |
| 6 | Fix the highest-value failures and review coverage gaps. |

**Checkpoint:** A user can sign in, create a client, create a project/task, and see it after refresh.

#### Learning Week 18 — Full-stack release candidate

| Day | Work |
|---:|---|
| 1 | Finish the main dashboard and primary workflows. |
| 2 | Add activity/notes as a small secondary feature. |
| 3 | Improve performance and accessibility of the real data screens. |
| 4 | Complete a browser test for the core authenticated workflow. |
| 5 | Run a user walkthrough with one or two people and collect confusion points. |
| 6 | Fix the most important findings and create a release-candidate checklist. |

**Checkpoint:** The product demonstrates one complete, tested, authenticated workflow from browser to database.

### Phase 4 — Production engineering and product delivery (Learning Weeks 19–24)

#### Learning Week 19 — Docker and configuration

| Day | Work |
|---:|---|
| 1 | Learn image/container boundaries and write the API Dockerfile. |
| 2 | Containerise the frontend and configure development versus production commands. |
| 3 | Use Docker Compose for the application and PostgreSQL. |
| 4 | Separate environment configuration from committed code; create safe examples. |
| 5 | Start the product from a clean clone using documented commands. |
| 6 | Repair setup friction and update local-development documentation. |

**Checkpoint:** Another developer can start the project with one documented workflow and no committed secrets.

#### Learning Week 20 — CI, deployment, and operational signals

| Day | Work |
|---:|---|
| 1 | Add lint, type-check, unit tests, and integration tests to GitHub Actions. |
| 2 | Add a production build check and protect the main branch through workflow expectations. |
| 3 | Deploy frontend, API, and database using one cloud platform. |
| 4 | Add health/readiness endpoints and structured logs. |
| 5 | Add one error tracker or monitoring service; avoid duplicating tools. |
| 6 | Deliberately break a non-critical dependency and practise diagnosing it from signals. |

**Checkpoint:** A failing test prevents a green CI result, and one injected failure can be diagnosed using logs/health checks.

#### Learning Week 21 — Security, reliability, and performance

| Day | Work |
|---:|---|
| 1 | Review secrets, authentication, authorisation, input validation, and dependency hygiene. |
| 2 | Add rate/abuse protection appropriate for the chosen deployment boundary. |
| 3 | Measure one slow API/database path and improve it with evidence. |
| 4 | Create backup/recovery and rollback notes appropriate to the deployment. |
| 5 | Run a cross-browser and accessibility QA pass. |
| 6 | Write a short security/reliability checklist and fix the highest-risk item. |

**Checkpoint:** You can name the system’s main trust boundaries and show a measured improvement rather than a guessed one.

#### Learning Week 22 — Product discovery and requirements

| Day | Work |
|---:|---|
| 1 | Write a one-page problem statement: user, workflow, pain, desired outcome, and constraints. |
| 2 | Write user stories and acceptance criteria for the next meaningful feature. |
| 3 | Create a lightweight PRD and define what is explicitly out of scope. |
| 4 | Compare two feasible technical approaches using an options matrix. |
| 5 | Create a risk register covering product, security, data, cost, and delivery risks. |
| 6 | Present the feature plan aloud as if to a stakeholder and revise unclear sections. |

**Checkpoint:** Another engineer could explain the problem, success criteria, and non-goals from the written documents.

#### Learning Week 23 — Architecture decisions and system design

| Day | Work |
|---:|---|
| 1 | Write an ADR for one important existing choice: auth, API boundary, database, or deployment. |
| 2 | Draw the request path from browser through services to PostgreSQL. |
| 3 | Study caching through one repeated expensive-read scenario; decide whether it is needed now. |
| 4 | Study queues/background jobs through document processing; define why synchronous handling is insufficient. |
| 5 | Study realtime delivery through one notification/streaming scenario; decide whether polling, SSE, or WebSockets is justified. |
| 6 | Explain the trade-offs in plain language and add only the primitive the product truly needs. |

**Checkpoint:** Explain when to use an index, cache, background job, queue, SSE, and WebSocket—without claiming they all belong in the current app.

#### Learning Week 24 — FDE-style delivery simulation

| Day | Work |
|---:|---|
| 1 | Create a fictional client brief with a messy workflow and measurable business outcome. |
| 2 | Run a discovery script: questions, assumptions, unknowns, and data-access constraints. |
| 3 | Turn the discovery results into a scoped solution proposal and success metrics. |
| 4 | Integrate one external API or create a realistic connector boundary. |
| 5 | Simulate a production incident and write a short customer-facing RCA: impact, timeline, cause, fix, prevention. |
| 6 | Record a five-minute demo that connects the business problem, technical decision, and result. |

**Checkpoint:** Explain the project as an outcome for a user, not just as a list of technologies.

### Phase 5 — Practical AI engineering (Learning Weeks 25–31)

#### Learning Week 25 — Python rebuild and production basics

| Day | Work |
|---:|---|
| 1 | Rebuild Python fundamentals through typed domain utilities, data classes, exceptions, and modules. |
| 2 | Practise virtual environments, packaging, formatting, linting, and `pytest`. |
| 3 | Use Pydantic models for input/output validation. |
| 4 | Learn async Python only through one I/O-bound example. |
| 5 | Build a small document-text processing utility with tests. |
| 6 | Review Python/TypeScript similarities and boundaries; do not build a second general backend. |

**Checkpoint:** A small typed Python utility has tests, validation, clear errors, and a documented interface.

#### Learning Week 26 — FastAPI as a bounded AI service

| Day | Work |
|---:|---|
| 1 | Build a FastAPI health endpoint, request model, response model, and local test. |
| 2 | Add one document-processing endpoint with validation and error handling. |
| 3 | Add service-to-service authentication appropriate for the local/deployment environment. |
| 4 | Connect the TypeScript product API to the FastAPI service. |
| 5 | Add timeout, retry, and failure handling at the integration boundary. |
| 6 | Document why the Python service exists and what should remain in TypeScript. |

**Checkpoint:** The product safely calls a small Python capability, and the product remains usable if that service fails.

#### Learning Week 27 — LLM APIs and structured outputs

| Day | Work |
|---:|---|
| 1 | Learn tokens, context windows, model limits, latency, and cost as engineering constraints. |
| 2 | Call an LLM through the Python service for a narrow document/task workflow. |
| 3 | Define a strict structured-output schema for extracted tasks or project risks. |
| 4 | Validate the model response server-side and handle malformed/unsupported output. |
| 5 | Show the result in the UI as a proposal requiring user review, not an automatic action. |
| 6 | Create labelled examples for correct, uncertain, and bad outputs. |

**Checkpoint:** The AI feature returns validated structured data or a safe failure; it never silently treats free text as trusted state.

#### Learning Week 28 — Tool calling and AI security

| Day | Work |
|---:|---|
| 1 | Learn tool/function calling as an application-controlled loop, not autonomous authority. |
| 2 | Implement one read-only tool, such as retrieving authorised project context. |
| 3 | Add server-side authorisation, input validation, and workspace filtering to the tool. |
| 4 | Add an explicit confirmation screen before any write-capable action. |
| 5 | Test prompt injection, malicious document content, cross-workspace access, and malformed arguments. |
| 6 | Document the AI threat model and the limits of the feature. |

**Checkpoint:** The model cannot bypass application authorisation or write data without explicit, validated user approval.

#### Learning Week 29 — Document ingestion and retrieval

| Day | Work |
|---:|---|
| 1 | Add document upload metadata, workspace ownership, and safe storage choices. |
| 2 | Extract text, chunk it deliberately, and store ingestion status/errors. |
| 3 | Start with metadata and PostgreSQL full-text search; inspect the results manually. |
| 4 | Add embeddings and `pgvector` only if semantic retrieval improves the actual use case. |
| 5 | Ensure every retrieval query filters by workspace before ranking results. |
| 6 | Build a UI that shows retrieved sources and makes uncertainty visible. |

**Checkpoint:** A user can inspect why a document answer used particular sources, and cannot retrieve another workspace’s data.

#### Learning Week 30 — RAG evaluation and iteration

| Day | Work |
|---:|---|
| 1 | Create a small labelled evaluation set of real questions, expected sources, and unacceptable answers. |
| 2 | Measure retrieval relevance/hit rate before changing prompts or indexes. |
| 3 | Measure answer support, refusal behaviour, latency, and approximate cost. |
| 4 | Improve one weak retrieval or answer path and rerun the same evaluation. |
| 5 | Add regression tests for the most important cases. |
| 6 | Write an evaluation report: what improved, what did not, and what remains unsafe. |

**Checkpoint:** You can show evidence that retrieval changed quality; “the demo sounded right” is not the metric.

#### Learning Week 31 — AI reliability and operational trade-offs

| Day | Work |
|---:|---|
| 1 | Add timeouts, retry boundaries, idempotency, and user-visible fallback behaviour. |
| 2 | Record latency and cost for representative AI workflows. |
| 3 | Add a background job for document ingestion only if synchronous processing is a demonstrated problem. |
| 4 | Add logging that records safe AI request metadata without leaking sensitive content. |
| 5 | Add dashboards or simple queries for failure rate, latency, and processing status. |
| 6 | Simulate provider failure, malformed output, and slow processing; repair the user experience. |

**Checkpoint:** The AI workflow degrades safely and remains observable when a dependency fails.

### Phase 6 — Hardening, evidence, and career readiness (Learning Weeks 32–35)

#### Learning Week 32 — Integrated product hardening

| Day | Work |
|---:|---|
| 1 | Review the full authentication, authorisation, document, retrieval, and tool path. |
| 2 | Add end-to-end tests for the highest-risk full workflow. |
| 3 | Perform a performance review: queries, document ingestion, UI loading, and AI latency. |
| 4 | Complete accessibility and cross-browser QA for primary flows. |
| 5 | Resolve the highest-severity reliability/security defects. |
| 6 | Freeze features and publish a clear release checklist. |

**Checkpoint:** The application has no known critical cross-workspace, unsafe-tool, or data-loss issue.

#### Learning Week 33 — FDE portfolio evidence

| Day | Work |
|---:|---|
| 1 | Write the product case study: problem, users, constraints, approach, and outcome. |
| 2 | Publish the architecture diagram, ERD, request path, and key ADRs. |
| 3 | Publish the AI design: evaluation set, safety controls, cost/latency trade-offs, and limitations. |
| 4 | Publish the incident/RCA and what changed afterwards. |
| 5 | Improve the README: setup, screenshots, testing, deployment, security, and future scale. |
| 6 | Record a concise product/technical walkthrough. |

**Checkpoint:** A stranger can understand what the product does, how it works, and why the decisions were made.

#### Learning Week 34 — Interview practice and system explanation

| Day | Work |
|---:|---|
| 1 | Practise JavaScript/TypeScript explanations: closures, async flow, state, types, and errors. |
| 2 | Practise backend/database explanations: HTTP, REST, auth, joins, indexes, transactions, and query plans. |
| 3 | Practise product/system design: requirements, constraints, API/data model, scale, cache, queue, and failure modes. |
| 4 | Practise AI-system explanation: structured output, retrieval, evaluation, safety, latency, and cost. |
| 5 | Practise FDE scenarios: discovery questions, scope negotiation, risk communication, and incident response. |
| 6 | Run one full mock: coding or debugging, system design, and product walkthrough. |

**Checkpoint:** Explain the product clearly without slides, code search, or vague technology buzzwords.

#### Learning Week 35 — Release and next-step plan

| Day | Work |
|---:|---|
| 1 | Fix only release-blocking defects; do not add new features. |
| 2 | Tag and publish the stable release, deployment URL, and final documentation. |
| 3 | Update portfolio, résumé, GitHub profile, and project links. |
| 4 | Identify realistic roles and tailor application material to full-stack/product/AI implementation work. |
| 5 | Apply to a small, targeted set of roles or seek feedback from working engineers. |
| 6 | Write the final retrospective: capability gained, weak areas, next 90-day plan, and technologies deliberately deferred. |

**Checkpoint:** The project, documentation, demo, and career materials are complete enough to share without apology.

-->

## Free resource map

Use one primary source per topic. Add one or more supplemental resources only when each adds a distinct value: a second explanation, hands-on practice, or current field context. Read only the modules named in the weekly plan; this is a map, not a completion checklist.

| Topic | Primary resource | Supplemental resource |
|---|---|---|
| HTML, CSS, accessibility | [MDN Learn Web Development](https://developer.mozilla.org/en-US/docs/Learn_web_development) | [web.dev Learn](https://web.dev/learn); [The Odin Project](https://www.theodinproject.com/paths/full-stack-javascript); selected [freeCodeCamp](https://www.freecodecamp.org/learn/) practice |
| Git and GitHub | [Pro Git book](https://git-scm.com/book/en/v2) | [GitHub Skills](https://skills.github.com/) |
| JavaScript | [javascript.info](https://javascript.info/) | [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide); selected [freeCodeCamp](https://www.freecodecamp.org/learn/) labs |
| TypeScript | [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html) | [Full Stack Open TypeScript](https://courses.mooc.fi/org/uh-cs/courses/full-stack-open-typescript); [React TypeScript guide](https://react.dev/learn/typescript) |
| React | [React Learn](https://react.dev/learn) | [Using TypeScript with React](https://react.dev/learn/typescript) |
| Next.js | [Next.js Learn](https://nextjs.org/learn) | — |
| Node.js and HTTP | [Node Learn](https://nodejs.org/en/learn) | [MDN HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) |
| Express | [Express documentation](https://expressjs.com/) | [Full Stack Open](https://fullstackopen.com/en/) |
| PostgreSQL and SQL | [PostgreSQL Tutorial](https://www.postgresql.org/docs/current/tutorial.html) | [PGExercises](https://pgexercises.com/); [Full Stack Open relational databases](https://courses.mooc.fi/org/uh-cs/courses/full-stack-open-relational-databases) |
| Testing | [Vitest](https://vitest.dev/guide/) | [Playwright](https://playwright.dev/docs/intro) |
| Docker | [Docker Get Started](https://docs.docker.com/get-started/) | [Full Stack Open Containers](https://courses.mooc.fi/org/uh-cs/courses/full-stack-open-containers) |
| CI/CD | [GitHub Actions documentation](https://docs.github.com/en/actions) | [GitHub Skills](https://skills.github.com/) |
| Python | [Python Tutorial](https://docs.python.org/3/tutorial/) | [CS50P](https://cs50.harvard.edu/python/); [Kaggle Learn](https://www.kaggle.com/learn) only when data evaluation needs pandas |
| FastAPI | [FastAPI Tutorial](https://fastapi.tiangolo.com/tutorial/) | — |
| LLM APIs and structured output | [OpenAI API Quickstart](https://developers.openai.com/api/docs/quickstart) | [Structured Outputs guide](https://developers.openai.com/api/docs/guides/structured-outputs); selected [DeepLearning.AI short courses](https://learn.deeplearning.ai/) |
| Tool calling | [OpenAI function-calling guide](https://developers.openai.com/api/docs/guides/function-calling) | [Writing effective tools for agents](https://www.anthropic.com/engineering/writing-tools-for-agents); a selected [DeepLearning.AI short course](https://learn.deeplearning.ai/) |
| Retrieval and vectors | [pgvector documentation](https://github.com/pgvector/pgvector) | [PostgreSQL full-text search](https://www.postgresql.org/docs/current/textsearch.html); [DeepLearning.AI RAG course](https://corporate.deeplearning.ai/courses/retrieval-augmented-generation/) |
| Evaluation | [OpenAI evals guide](https://developers.openai.com/api/docs/guides/evals) | [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents); [DeepLearning.AI Evaluating AI Agents](https://corporate.deeplearning.ai/courses/evaluating-ai-agents) |
| AI security | [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) | [Simon Willison on LLMs](https://simonwillison.net/tags/llms/) for current examples and analysis |
| MCP | [MCP introduction and concepts](https://modelcontextprotocol.io/docs/getting-started/intro) | Read the [specification](https://modelcontextprotocol.io/specification/latest) only after ordinary tool calling is understood; selected [DeepLearning.AI short course](https://learn.deeplearning.ai/) |
| Algorithms | [NeetCode roadmap](https://neetcode.io/roadmap) for the ordered, selected interview-practice path | [Alg0](https://www.alg0.dev/) for visual intuition; [Open Data Structures](https://opendatastructures.org/) for deeper implementation and analysis |

### Ongoing engineering reading

This is optional context, not a second curriculum. Spend no more than one short weekly session here, and only follow topics already active in the roadmap.

- [Simon Willison on LLMs](https://simonwillison.net/tags/llms/) for practical LLM tooling, security, and deployment analysis.
- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) when designing the document, retrieval, or tool-action boundaries.
- Official release notes for the tools currently in use: [React](https://react.dev/blog), [Next.js](https://nextjs.org/blog), [Node.js](https://nodejs.org/en/blog/release), and [PostgreSQL](https://www.postgresql.org/docs/release/).

## Career milestones

| Milestone | Expected evidence | Roles to explore honestly |
|---|---|---|
| Frontend/product capable — after Learning Week 11 | Typed, accessible Next.js frontend with tested core interactions | Frontend engineer, React developer, product-engineer trainee |
| Junior full-stack capable — after Learning Week 18 | Authenticated browser-to-database vertical slice with tests | Junior full-stack engineer, application engineer, product engineer |
| Strong full-stack/product foundation — after Learning Week 24 | Deployed product, CI, logs, health checks, ADRs, incident simulation, external integration | Full-stack/product engineer, backend-leaning product engineer |
| AI-enabled full-stack engineer — after Learning Week 31 | Bounded AI workflow with structured output, secure tool boundary, retrieval, evaluation, and operational evidence | AI application engineer, applied AI engineer, AI product engineer |
| Entry-level FDE capability — after Learning Week 35 | Discovery artefacts, technical proposal, deployed integration, RCA, demo, and portfolio defence | FDE-adjacent, solutions, AI implementation, and applied AI/product roles |

These are capability checkpoints, not promises of a title or job. Strong applications will pair this evidence with professional experience, clear communication, and real feedback from users or other engineers.

## Final standard

At the end of this plan, success means I can say:

> I can understand a product problem, scope a reasonable first version, build the frontend and backend, design the database, secure and test the system, deploy and monitor it, add an AI feature with evaluation and safety controls, and explain the decisions I made.

It does **not** mean I have mastered every cloud service, every distributed-system pattern, or every AI framework. The next stage begins only after this foundation is real.
