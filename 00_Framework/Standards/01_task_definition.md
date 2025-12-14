---
task_id: "uuid-here"
created_by: "agent-name-or-user"
created_at: "{{AUTO:DATE:America/Chicago}}"
updated_at: "{{AUTO:DATETIME_ISO:America/Chicago}}"
status: "draft"        # draft | in_progress | review | done
priority: "high"       # critical | high | normal | low
type: "feature"        # feature | enhancement | bugfix | research | refactor
labels: ["general"]
version: "1.0.0"
project_context_ref: "./00_setup_project_context.md"
---

# Protocol 01: Task Definition

**Purpose:** This is the **Master Plan**. Do not write code until this document is filled out and approved. It forces you to think about Architecture, Dependencies, and Quality *before* implementation.

> **Instructions for Agents:**
> 1. Read `00_setup_project_context.md` to understand the tech stack.
> 2. Fill out every section of this template based on the user's request.
> 3. If you lack information, ask the user. **Do not hallucinate requirements.**

---

## 0. Grounding (MUST READ FIRST)

**Source of Truth:** Refer to `00_setup_project_context.md` for:
*   Approved Tech Stack (Frameworks, Libraries)
*   Architecture Patterns (Repo structure, API patterns)
*   Verification Commands (Lint, Test, Build)

**Alignment Checklist:**
- [ ] Task uses *only* approved tech from Protocol 00.
- [ ] Task does not duplicate existing functionality.
- [ ] Task aligns with the project's architectural patterns.

---

## 1. Task Overview

**Title:** [Short, Action-Based Title]
**Goal:** [What does success look like? Why does this matter?]

| Priority | Type |
|----------|------|
| ☐ Critical  ☐ High  ☐ Normal  ☐ Low | ☐ Feature  ☐ Enhancement  ☐ Bugfix  ☐ Refactor |

---

## 2. Context Capsule & Constants

*(Extract these from `00_setup_project_context.md`)*
- **Project:** [Name]
- **Language:** [e.g., TypeScript]
- **Frameworks:** [e.g., Next.js, FastAPI]
- **Database:** [e.g., Postgres + Drizzle]
- **Auth:** [e.g., Clerk]

---

## 3. Architectural Decisions (CRITICAL)

**Stop & Think:** How will we solve this?
*(Agent: Define the approach here. Do not default to "standard" code if it doesn't fit the project.)*

*   **Pattern Selection:** [e.g., "Using Server Actions for mutations," "Using React Context for state"]
*   **Trade-offs:** [e.g., "Optimizing for read speed, so denormalizing data X"]
*   **New Dependencies?** [List any new libs. **Must be approved.**]
*   **Breaking Changes?** [Yes/No. If Yes, describe mitigation.]

---

## 4. Problem & Success Criteria

**Problem:** [What is broken or missing?]

**Success Criteria (Definition of Done):**
- [ ] [Functional Requirement 1]
- [ ] [Functional Requirement 2]
- [ ] Code compiles and passes all linters.
- [ ] Tests written and passing.
- [ ] Documentation updated.

---

## 5. Functional Requirements

**User Scenarios:**
- "When user does X → system should Y"

**System Behaviors:**
- "On event Z, trigger job Q"

---

## 6. Data & API Changes

**Schema Updates (SQL/ORM):**
```sql
-- Example changes
```

**API Contracts / Server Actions:**
*   `POST /api/resource`: Inputs/Outputs
*   `updateResource` (Action): Inputs/Outputs

---

## 7. Plan & Phases

| Phase | Description | Est. Time |
|-------|-------------|-----------|
| 1 | Setup & Schema Changes | |
| 2 | Core Logic & API | |
| 3 | UI & Integration | |
| 4 | Testing & Refinement | |

---

## 8. File Map (The Blueprint)

**Exact files to create/modify:**
*(Agent: Be specific. Don't say "Update utils". Say `src/utils/format.ts`)*

*   `[New/Mod]` `src/path/to/file.ts`: [Description of change]
*   `[New/Mod]` `src/path/to/test.ts`: [Description of test]

---

## 9. AI Agent Guardrails

**When implementing this task (using Protocol 02):**
1.  **No Slop:** Do not generate unused code, comments explaining "what" instead of "why", or verbose implementations.
2.  **Strict Typing:** No `any`. No "trust me" assertions.
3.  **Scoped Commits:** One commit per logical change.
4.  **Update Status:** Keep this file updated as you progress (`status: in_progress`).