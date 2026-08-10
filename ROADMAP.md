# 120-Day Roadmap

Each day has one learning target and one piece of evidence. The exact course lesson may change; the outcome should not.

## Phase 1 — Foundations, Days 1–10

| Day | Learn | Ship |
|---:|---|---|
| 1 | Environment, terminal, Git basics | Repository, mission, first lesson, first commit |
| 2 | Web and HTTP at a high level; semantic HTML | Semantic profile page |
| 3 | Forms, labels, tables, validation, keyboard access | Accessible contact form |
| 4 | CSS selectors, cascade, box model, units | Styled profile page |
| 5 | Flexbox | Two recreated layouts |
| 6 | CSS Grid | Responsive dashboard grid |
| 7 | Mobile-first media queries | Phone, tablet, desktop layouts |
| 8 | Accessibility, focus, contrast, alt text | Accessibility pass |
| 9 | Branches, issues, pull requests | Issue → branch → PR → merge |
| 10 | Consolidation and deployment | **Portfolio v1 deployed** |

## Phase 2 — JavaScript, Days 11–30

| Day | Learn | Ship |
|---:|---|---|
| 11 | Values, types, variables, coercion | 20 console exercises |
| 12 | Conditions, loops, truthiness | Input/decision exercises |
| 13 | Functions, scope, returns | Refactored function exercises |
| 14 | Arrays | Manual array operations |
| 15 | Objects, references, destructuring | Inventory app |
| 16 | `map`, `filter`, `reduce`, `find` | Data transformation exercises |
| 17 | DOM and events | Interactive page |
| 18 | Forms and browser validation | Dynamic validated form |
| 19 | Modules, npm, package scripts | Modularised project |
| 20 | DevTools and debugging | Five repaired exercises |
| 21 | Callbacks and Promises | Async exercises |
| 22 | `async`/`await` and `fetch` | Public API client |
| 23 | HTTP, JSON, status codes, UI states | Loading/error-aware API UI |
| 24 | Closures and execution model | Written closure explanations |
| 25 | Prototypes, classes, `this` | Small object model |
| 26 | `localStorage` and persistence | Refresh-safe app state |
| 27 | Testing fundamentals | Utility tests |
| 28 | DevDash architecture and API integration | Working dashboard skeleton |
| 29 | DevDash features and responsive UI | Feature-complete DevDash |
| 30 | Refactor, test, deploy | **DevDash v1 deployed** |

## Phase 3 — TypeScript and deeper JavaScript, Days 31–40

| Day | Learn | Ship |
|---:|---|---|
| 31 | Types and inference | Typed JS exercises |
| 32 | Object types, aliases, interfaces | Typed domain objects |
| 33 | Unions and narrowing | Explicit UI state model |
| 34 | Function typing and generics | Generic helpers |
| 35 | `tsconfig`, strict mode, modules | Strict project with no accidental `any` |
| 36 | TypeScript migration | Typed DevDash module |
| 37 | Scope and closures review | Predict-before-run exercises |
| 38 | Event loop and microtasks | Execution-order notes |
| 39 | Prototypes and composition | Cleaner object model |
| 40 | Independent assessment | Rebuild one feature from memory |

## Phase 4 — React, Days 41–60

| Day | Learn | Ship |
|---:|---|---|
| 41 | Vite, JSX, components | Multi-component app |
| 42 | Props and state | Interactive components |
| 43 | Events and controlled forms | Form UI |
| 44 | Lists, keys, conditional rendering | Searchable list |
| 45 | Effects and API data | Loading/error-aware component |
| 46 | Custom hooks | Extracted reusable logic |
| 47 | Client-side routing | Multi-route SPA |
| 48 | Context and reducers | Shared state without prop drilling |
| 49 | Server state and caching | Cached API workflow |
| 50 | React testing | Behaviour-focused tests |
| 51 | Typed React props and state | Typed components |
| 52 | Typed hooks, forms, responses | Feature without uncontrolled `any` |
| 53 | IssueBoard architecture | UI and project skeleton |
| 54 | Mocked sessions and protected routes | Sign-in/logout flow |
| 55 | Tables, search, filters | Functional issue dashboard |
| 56 | Form handling and validation | Create/edit workflow |
| 57 | Responsive design and accessibility | Keyboard-usable primary flow |
| 58 | Testing highest-value behaviours | Test suite for core flows |
| 59 | Production build and deployment | Public IssueBoard URL |
| 60 | Refactor and explain architecture | **IssueBoard v1 + demo** |

## Phase 5 — Node, APIs, and PostgreSQL, Days 61–80

| Day | Learn | Ship |
|---:|---|---|
| 61 | Node runtime, npm, modules, environment | Node CLI |
| 62 | Filesystem and async APIs | File-backed app |
| 63 | Raw HTTP request/response | Tiny Node HTTP server |
| 64 | Express routes and controllers | Express API |
| 65 | REST resources, verbs, status codes | CRUD endpoints |
| 66 | Middleware, errors, logs, validation | Consistent API responses |
| 67 | PostgreSQL databases and tables | Local database |
| 68 | `SELECT`, filters, sorting, limits | SQL exercise file |
| 69 | Joins | Multi-table queries |
| 70 | Aggregates and grouping | Analytics queries |
| 71 | Keys, constraints, schema design | ER diagram |
| 72 | Indexes and `EXPLAIN` | Query-plan comparison |
| 73 | Transactions | Commit/rollback exercises |
| 74 | Migrations and seed data | Reproducible database setup |
| 75 | Node/PostgreSQL integration | Database-backed API |
| 76 | Passwords, sessions/tokens, auth flow | Register/login/logout |
| 77 | Authorisation and ownership | Isolation between users |
| 78 | Integration/API testing | Endpoint test suite |
| 79 | Pagination, filtering, runtime validation | Production-style collection endpoint |
| 80 | Deployment and API documentation | **Deployed TypeScript API** |

## Phase 6 — ClientFlow capstone, Days 81–95

| Day | Learn | Ship |
|---:|---|---|
| 81 | Requirements, stories, ERD, API contract | `SPEC.md`, ERD, issues |
| 82 | Full-stack repo setup and schema | Clean application skeleton |
| 83 | End-to-end authentication | Working auth |
| 84 | Users and workspaces | Ownership model |
| 85 | Client CRUD | Create/read/update/archive |
| 86 | Projects and tasks | Related domain records |
| 87 | Search, filtering, sorting, pagination | Server-driven lists |
| 88 | Dashboard frontend | Authenticated dashboard |
| 89 | Forms and runtime validation | Clean invalid-input handling |
| 90 | Data fetching and failure states | Slow/failing requests handled |
| 91 | Authorisation rules | Protected records |
| 92 | Activity or notes feature | Secondary domain feature |
| 93 | One stretch feature | One finished extension |
| 94 | Critical workflow tests | Auth and core-flow coverage |
| 95 | User feedback | Alpha release tested by two people |

## Phase 7 — Production engineering, Days 96–105

| Day | Learn | Ship |
|---:|---|---|
| 96 | Docker images, containers, Dockerfiles | Containerised backend |
| 97 | Docker Compose | App + database one-command startup |
| 98 | Configuration and secret discipline | Safe environment setup |
| 99 | CI: lint, type-check, tests | Passing PR pipeline |
| 100 | Deployment workflow | Repeatable production deploy |
| 101 | Error monitoring | Sentry integrated |
| 102 | Structured logs and health endpoint | Production debugging signals |
| 103 | Security review | Auth, validation, secrets review |
| 104 | Performance measurement | One measured improvement |
| 105 | Cross-browser and accessibility QA | Bug-bash report and fixes |

## Phase 8 — Next.js and system design, Days 106–112

| Day | Learn | Ship |
|---:|---|---|
| 106 | Next.js App Router, layouts, navigation | Small Next.js app |
| 107 | Server/client components | Appropriate component split |
| 108 | Data fetching and route handlers | Database/API feature |
| 109 | Comparative implementation | One ClientFlow feature in Next.js |
| 110 | DNS, HTTP/TLS, proxies, processes | Production request-path diagram |
| 111 | Requirements, constraints, interfaces, modelling | URL shortener/file-sharing design |
| 112 | Caching, CDNs, queues, scaling trade-offs | ClientFlow scaling notes |

## Phase 9 — Interview and launch, Days 113–120

| Day | Learn | Ship |
|---:|---|---|
| 113 | Feature freeze and release planning | v1.0 checklist |
| 114 | Bug fixing and test strengthening | Release candidate |
| 115 | Portfolio case studies | Portfolio v2 |
| 116 | GitHub and README cleanup | Pinned, documented projects |
| 117 | Résumé and technical walkthrough | Two-page résumé + demo script |
| 118 | Full-stack mock interview | Recorded answers |
| 119 | Coding, SQL, system-design mock | Timed practice evidence |
| 120 | Ship and apply | **ClientFlow v1, portfolio, résumé, first applications** |

## Weekly review

Every seventh day, answer in the daily lesson:

- What can I build without notes?
- What still feels like magic?
- What bug taught me the most?
- What did I ship?
- What will I change next week?

