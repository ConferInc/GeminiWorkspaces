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

**Purpose:** This is the **Master Plan**. Do not write code until this document is filled out and approved.

> **Instructions for Agents:**
> 1. Read `00_setup_project_context.md` (The Golden Path).
> 2. Fill out every section.
> 3. **Constraint:** You MUST use the Golden Path stack (Next.js, Temporal, Camunda, Drizzle).

---

## 0. Grounding (MUST READ FIRST)

**Source of Truth:** Refer to `00_setup_project_context.md` for the stack.

**Alignment Checklist:**
- [ ] Task uses **pnpm**.
- [ ] Task uses **TypeScript** (Strict).
- [ ] Task uses **Drizzle ORM** (if DB involved).
- [ ] Task uses **Temporal/Camunda** (if Workflow involved).

---

## 1. Task Overview

**Title:** [Short, Action-Based Title]
**Branch Name:** `{{developer_name}}/[type]-{{short-title}}` (e.g., `anjali/feat-auth-login`)
**Goal:** [What does success look like? Why does this matter?]

| Priority | Type |
|----------|------|
| ☐ Critical  ☐ High  ☐ Normal  ☐ Low | ☐ Feature  ☐ Enhancement  ☐ Bugfix  ☐ Refactor |

---

## 2. Context Capsule

*(Extract these from Protocol 00)*
- **Project:** [Name]
- **Developer:** [Your Name]
- **Stack:** Next.js 14+, Temporal, Camunda 8.5, Drizzle.

---

## 3. Golden Path Compliance (Architecture)

**How does this task fit into the Confer Stack?**

*   **Logic:**
    *   [ ] Simple UI Interaction (Use React State)
    *   [ ] Data Mutation (Use Server Actions + Drizzle)
    *   [ ] Long-Running Process (Use Temporal Workflow)
    *   [ ] Business Logic Flow (Use Camunda BPMN)

*   **Breaking Changes?** [Yes/No]

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
*(Agent: Be specific. Use the correct project structure.)*

*   `[New/Mod]` `src/app/actions/...`: [Server Actions]
*   `[New/Mod]` `src/workflows/...`: [Temporal Workflows]
*   `[New/Mod]` `src/components/...`: [UI Components]

---

## 9. AI Agent Guardrails

**When implementing this task (using Protocol 02):**
1.  **No Slop:** Do not generate unused code.
2.  **Strict Typing:** No `any`.
3.  **Scoped Commits:** One commit per logical change.
4.  **Update Status:** Keep this file updated (`status: in_progress`).

---

## Next Steps for the AI Agent:

1.  Ensure this `01_task_definition.md` file is fully populated and saved.
2.  **Your Job is Done Here.** Now, provide this file to the **Builder Agent** (or the user instructing the Builder Agent) with the instruction:
    *"**Execute Protocol 02** using this plan. Focus on quality and efficiency."*
