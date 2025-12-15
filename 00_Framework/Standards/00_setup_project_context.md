# Protocol 00: Project Context Setup

**Purpose:** This document defines the specific operational context for a project. It must be filled out *once* when adopting the `ConferSolutionsAI` standards.

**The Golden Rule:** We follow the **Confer Golden Path**. Do not deviate from these standards without a Principal Engineer's written approval.

---

## 1. Project Identity
*   **Project Name:** [e.g., MoXi Loan Originator]
*   **Repository Type:** [Monorepo / Single Repo]
*   **Package Manager:** **pnpm** (Strictly required)

## 2. Developer Identity (YOU)
*   **Name:** [Choose one: yatin, anjali, kanan, divyani, harshit, vanshika]
*   **Git User Configured?** [Yes/No - Run `git config user.name` to check]

---

## 3. The Confer "Golden Path" Stack (Read-Only)

**All projects must use this stack unless explicitly exempt.**

### Frontend
*   **Framework:** Next.js 14+ (App Router)
*   **Library:** React 18+
*   **Styling:** Tailwind CSS + Shadcn UI
*   **State:** React Context (Local) / Zustand (Global - if needed)

### Backend & Logic
*   **Language:** TypeScript (Strict Mode)
*   **API Pattern:** Server Actions (for mutations) / Route Handlers (for external APIs)
*   **Workflow Engine:** **Temporal.io** (For durable execution/long-running processes)
*   **Process Orchestration:** **Camunda 8.5** (BPMN for business logic flow)

### Data Layer
*   **Database:** PostgreSQL
*   **ORM:** Drizzle ORM
*   **Auth:** Supabase Auth / Clerk (Check project-specific implementation)

---

## 4. Project-Specific Configuration (Fill This Out)

**Documentation Source of Truth:**
| Concept | File Path |
|---------|-----------|
| **System Overview / PRD** | `[e.g., docs/architecture/system_overview.md]` |
| **Task Tracker** | `[e.g., tasks/detailed_task_list.md]` |
| **DB Schema** | `[e.g., docs/database/current_schema_architecture.md]` |

**Verification Commands:**
| Check | Command |
|-------|---------|
| **Lint** | `pnpm lint` |
| **Type Check** | `pnpm type-check` |
| **Test** | `pnpm test` |
| **Build** | `pnpm build` |

**Dangerous Zones (Do Not Delete):**
*   `docs/`
*   `.env.example`
*   `[e.g., legacy/]`

---
*Status: [Active]*
*Last Updated: [Date]*