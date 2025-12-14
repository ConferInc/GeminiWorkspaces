# Protocol 00: Project Context Setup

**Purpose:** This document defines the specific operational context for a project. It must be filled out *once* when adopting the `ConferSolutionsAI` standards. All Agents (Gemini, Claude, Cursor) refer to this file to understand the specific rules of engagement (Tech Stack, Commands, Paths) for the repository.

---

## 1. Project Identity
*   **Project Name:** [e.g., MoXi Loan Originator]
*   **Primary Language(s):** [e.g., TypeScript, Python]
*   **Package Manager:** [e.g., pnpm, pip, npm]

## 2. Repository Architecture
*   **Type:** [Monorepo / Single Repo / Multi-Repo]
*   **Repo URL(s):**
    *   Primary: `[URL]`
    *   Secondary (if any): `[URL]`
*   **Branching Strategy:**
    *   Main/Production Branch: `[e.g., main]`
    *   Development Branch: `[e.g., develop]`
    *   Feature Branch Prefix: `[e.g., feature/, fix/]`

## 3. Documentation "Source of Truth"
Identify the specific file paths for these critical documents.

| Concept | File Path |
|---------|-----------|
| **System Overview / PRD** | `[e.g., docs/system_overview.md]` |
| **Task Tracker** | `[e.g., tasks/detailed_task_list.md]` |
| **Architecture Guide** | `[e.g., ARCHITECTURE.md]` |
| **API/Schema Docs** | `[e.g., docs/api/]` |

## 4. Verification Commands
What specific commands must pass before code is committed?

| Check | Command |
|-------|---------|
| **Type Check** | `[e.g., pnpm type-check]` |
| **Lint** | `[e.g., pnpm lint]` |
| **Test** | `[e.g., pnpm test]` |
| **Build** | `[e.g., pnpm build]` |

## 5. Dangerous Zones (Do Not Delete/Modify)
List files or folders that require explicit human approval to modify or delete.

*   `[e.g., .env.example]`
*   `[e.g., docs/architecture/]`
*   `[e.g., legacy/]`

## 6. Deployment / Sync (Optional)
If this project requires syncing to another repo or specific deployment steps (like Vercel).

*   **Sync Required?** [Yes/No]
*   **Instructions:** [Link to deployment doc or brief steps]

---
*Status: [Draft / Active]*
*Last Updated: [Date]*
