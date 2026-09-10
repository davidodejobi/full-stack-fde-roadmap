# ClientFlow Assist — Product Requirements Document

## Status

Draft v0.1 — for product and UI review before implementation.

## 1. Product summary

ClientFlow Assist helps small service teams turn client onboarding material into a clear, human-reviewed delivery plan.

A team receives a brief, meeting notes, and supporting documents. Instead of manually turning that material into requirements, risks, tasks, and owners across disconnected tools, the team can organise it in one workspace, review a proposed delivery plan, and explicitly approve the tasks that should be created.

The product is not a general-purpose CRM, autonomous project manager, or document chatbot. Its focus is one workflow:

```text
Client onboarding material
        ↓
Review and clarify requirements
        ↓
Create a delivery plan
        ↓
Approve tasks and begin delivery
```

## 2. Problem

Small agencies, freelancers, and service teams often begin projects with scattered information: emails, calls, briefs, documents, and informal notes. Converting that information into an agreed scope and useful plan takes time, creates gaps, and makes it hard to see what was assumed or where a task came from.

The product should make the transition from **“we have received information”** to **“we have a reviewed delivery plan”** visible, traceable, and easier to manage.

## 3. Target users

### Primary user — service delivery lead

An agency owner, project lead, consultant, or freelancer who owns client onboarding and needs to translate client information into an actionable plan.

### Secondary user — delivery team member

A designer, engineer, or operations teammate who needs to understand the approved scope, tasks, risks, and supporting material.

### Not an initial user

The client does not need a self-service portal in the first release. Client-facing access is a later decision, after the internal workflow works.

## 4. Desired outcome

By the end of an onboarding session, a delivery lead can:

1. Create a client and onboarding record.
2. Add a brief, notes, and supporting documents.
3. Record or review requirements, assumptions, risks, and open questions.
4. Produce a delivery plan with proposed tasks and owners.
5. Review and explicitly approve the tasks that enter delivery.
6. Trace an important plan item back to its source material.

## 5. MVP scope

### Must have

- Workspace, user, and membership model.
- Client records.
- Onboarding briefs and notes.
- A document record with title, source, status, and extracted text or manually entered summary.
- Delivery plans containing requirements, risks, open questions, and proposed tasks.
- Task approval: proposed tasks remain drafts until a user approves them.
- Basic project/task view for approved work.
- Search and filtering over clients, briefs, plans, and tasks.
- Authentication and workspace-level authorisation.
- Clear empty, loading, error, and permission-denied states.
- Activity/audit entries for important actions: create, edit, approve, and source-link changes.

### AI-assisted feature, added only after the core workflow works

- Extract a structured proposal from an onboarding brief or document: requirements, risks, open questions, proposed tasks, and suggested owners.
- Let a user review, edit, reject, or approve every proposal.
- Answer narrow questions over documents and show the supporting source excerpts.
- Create tasks only from an approved delivery plan through one explicitly authorised action.

### Explicitly out of scope for the first release

- Payments, invoicing, contracts, and billing.
- Email inbox replacement or Gmail/Outlook integration.
- Slack, HubSpot, Notion, Jira, or other third-party integrations.
- Realtime multi-user editing, chat, notifications, or calendar scheduling.
- Autonomous task creation or a multi-agent system.
- Public client portal.
- Full CRM sales pipeline.
- Native mobile app.

## 6. Core user flow

### A. Start onboarding

1. User selects a workspace.
2. User creates or selects a client.
3. User creates an onboarding brief with a title, summary, and status.
4. User adds notes and documents.

### B. Build a delivery plan

1. User reviews source material.
2. User creates or edits requirements, assumptions, risks, and open questions.
3. User creates proposed tasks and assigns a tentative owner/priority.
4. User saves the plan as a draft.

### C. Review and approve

1. User compares the delivery plan with its source material.
2. User resolves or marks open questions.
3. User approves selected proposed tasks.
4. Approved tasks appear in the project/task view; rejected tasks remain visible with their reason.

### D. AI-assisted flow, later

1. User selects an onboarding brief or document.
2. The system returns a structured proposal, never an automatic change.
3. The user reviews every item and can edit, reject, or accept it.
4. Only an explicit approval changes the delivery plan or creates tasks.

## 7. Main screens for the Figma prototype

The Figma prototype should cover the whole internal product journey, using realistic sample content but not requiring every screen to be implemented immediately.

| Screen | Primary purpose | Initial priority |
|---|---|---|
| Sign in | Enter a workspace securely | Medium |
| Workspace dashboard | See active clients, onboarding status, open questions, and proposed work | High |
| Client list | Find, filter, and create clients | High |
| Client overview | See client details, active onboarding briefs, plans, and projects | High |
| Onboarding brief | Capture a brief, notes, status, and associated documents | High |
| Document detail | Read document metadata, summary/source excerpts, and processing state | High |
| Delivery-plan review | Review requirements, risks, open questions, and proposed tasks side by side | Highest |
| Task/project view | View approved tasks by status, owner, and priority | High |
| AI review panel | Review structured AI proposals before they change anything | Later |
| Search results | Search across workspace records | Later |
| Workspace settings/members | Manage membership and roles | Medium |
| Empty, loading, error, and access-denied states | Make normal failure and first-use states understandable | High |

## 8. Information architecture

Primary navigation:

```text
Dashboard
Clients
Onboarding
Delivery plans
Tasks
Documents
Search
Settings
```

The design should make the workflow state obvious. A user should always know whether work is still being collected, is under review, is approved for delivery, or is blocked by unanswered questions.

Suggested onboarding states:

```text
Draft → Collecting information → In review → Ready for approval → Active delivery → Archived
```

## 9. Core domain model

| Entity | Purpose | Important fields |
|---|---|---|
| Workspace | Tenant boundary | name, owner, created date |
| User | Authenticated person | name, email, profile |
| Membership | User access within a workspace | role, workspace, user |
| Client | Organisation or person receiving the service | name, contact details, status |
| Onboarding brief | Central record for incoming project information | client, title, summary, state, owner |
| Note | Structured or free-form onboarding detail | brief, content, author, timestamp |
| Document | Uploaded or linked supporting material | brief, title, source, processing status |
| Delivery plan | Reviewable version of intended delivery | brief, state, author, approved date |
| Requirement | Need or constraint in the plan | plan, description, priority, source reference |
| Risk | Potential delivery issue | plan, description, severity, mitigation, source reference |
| Open question | Unknown needing resolution | plan, question, owner, status |
| Proposed task | Work suggested before approval | plan, title, owner, priority, source reference, approval state |
| Task | Approved delivery work | project, title, owner, status, priority |
| Activity entry | Audit record | actor, action, entity, timestamp |

## 10. Roles and permissions

| Capability | Workspace owner | Delivery lead | Team member |
|---|---:|---:|---:|
| View workspace records | Yes | Yes | Yes, where assigned/permitted |
| Create/edit clients and briefs | Yes | Yes | Limited later if needed |
| Create/edit delivery plans | Yes | Yes | Draft contribution later |
| Approve proposed tasks | Yes | Yes | No |
| Manage members and roles | Yes | No | No |
| Use AI review feature | Yes | Yes | Read-only later if needed |

The server, not only the interface, must enforce workspace boundaries and approval permissions.

## 11. AI boundaries and safety requirements

AI is an assistant for reviewable work, not an authority.

- AI output must use a validated structured shape.
- AI proposals must identify source excerpts when derived from documents.
- Users can edit, reject, or approve every suggested requirement, risk, question, or task.
- The system must not let a model directly write database records or perform unrestricted actions.
- Retrieval is scoped to the current workspace and user permissions.
- Documents and user-provided text are untrusted input; they must not override system rules or permissions.
- Evaluation cases must include both useful examples and unsafe/misleading document content.

## 12. Success criteria

The MVP is successful when a user can complete a full onboarding-to-delivery flow without external tools for the core records:

- Create a client, brief, notes, and a delivery plan.
- Create and approve tasks from that plan.
- Find a requirement or task and see its origin.
- See clear feedback for loading, invalid input, unavailable data, and denied access.
- Explain why an item is proposed, approved, or blocked.

For the later AI feature, success is not “the model answered.” It is that a labelled evaluation set shows acceptable structured-output validity, source grounding, and human-review usefulness before the feature is relied upon.

## 13. Design principles

- **Workflow first:** show the next useful step, not every possible feature.
- **Review before action:** proposed work is visibly distinct from approved work.
- **Traceability:** important plan items link back to their source.
- **Calm density:** the interface should support focused review, not resemble a crowded CRM.
- **Accessible by default:** semantic structure, keyboard support, focus states, contrast, and understandable form errors are required.
- **Progressive disclosure:** advanced metadata and AI details appear when useful, not everywhere at once.

## 14. Figma prototype brief

Create a responsive desktop-first internal web application called **ClientFlow Assist** for small service teams. The app turns client onboarding briefs, notes, and documents into human-reviewed delivery plans.

Design the dashboard, client list, client overview, onboarding brief, document detail, delivery-plan review, task/project view, and core empty/loading/error states. The delivery-plan review screen is the key workflow: show source material alongside requirements, risks, open questions, and proposed tasks. Make proposed tasks visually distinct from approved tasks, and include an explicit approval action. Use a calm, professional, accessible interface with clear hierarchy, realistic sample content, reusable components, and responsive behaviour. Avoid a generic CRM aesthetic, excessive dashboards, gradients, chatbots, autonomous-agent controls, billing, and third-party integrations.