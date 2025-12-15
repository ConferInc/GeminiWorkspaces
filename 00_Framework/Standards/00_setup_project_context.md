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

### Backend & Logic
*   **Language:** TypeScript (Strict Mode)
*   **API Pattern:** Server Actions (for mutations) / Route Handlers (for external APIs)
*   **Workflow Engine:** **Temporal.io** (For durable execution)
*   **Process Orchestration:** **Camunda 8.5** (BPMN)

### Data Layer
*   **Database:** PostgreSQL
*   **ORM:** Drizzle ORM
*   **Auth:** Supabase Auth / Clerk

---

## 4. Workspace Rules (CRITICAL)

**Rule: One Task = One Folder.**

When you start **ANY** new task (BPMN, Docker Agent, UI Component), you **MUST**:
1.  Create a new directory: `User_Workspaces/YourName/Task-[ID]-[Description]/`
2.  Copy `01_task_definition.md` into that new directory.
3.  Execute all work **inside that directory**.

*   ❌ `User_Workspaces/Anjali/my_file.bpmn` (Messy)
*   ✅ `User_Workspaces/Anjali/Task-101-Loan-Process/process.bpmn` (Clean)

---

## 5. Project-Specific Configuration (Fill This Out)

**Documentation Source of Truth:**
| Concept | File Path |
|---------|-----------|
| **System Overview / PRD** | `[e.g., docs/architecture/system_overview.md]` |
| **Task Tracker** | `[e.g., tasks/detailed_task_list.md]` |

**Verification Commands:**
| Check | Command |
|-------|---------|
| **Lint** | `pnpm lint` |
| **Type Check** | `pnpm type-check` |
| **Test** | `pnpm test` |
| **Build** | `pnpm build` |

---
*Status: [Active]*
*Last Updated: [Date]*
