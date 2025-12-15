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
project_context_ref: "../../../00_Framework/Standards/00_setup_project_context.md" # Relative path check
---

# Protocol 01: Task Definition

**Purpose:** This is the **Master Plan**. Do not write code until this document is filled out and approved.

> **Instructions for Agents:**
> 1. Read `00_setup_project_context.md` (The Golden Path).
> 2. Fill out every section.
> 3. **Verify Location:** Ensure you are working in a dedicated Task Folder (e.g., `User_Workspaces/Name/Task-X/`).

---

## 0. Grounding (MUST READ FIRST)

**Source of Truth:** Refer to `00_setup_project_context.md`.

**Workspace Verification:**
*   [ ] I am working in a dedicated folder: `User_Workspaces/{{developer}}/Task-{{id}}/`
*   [ ] I will NOT modify files outside this folder without explicit permission.

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

## 3. Universal Artifact Definition (What are we building?)

**Select the Primary Deliverable Type:**

*   [ ] **A. Code Module (Integrated):** Features merged into the main codebase (e.g., Next.js Page, Server Action).
    *   *Validation:* Lint, Build, Test.
*   [ ] **B. Standalone Container (Isolated):** Independent Agent or Service.
    *   *Validation:* `Dockerfile` exists, `docker build` succeeds.
*   [ ] **C. Business Process (File-Based):** BPMN, DMN, or Config files.
    *   *Validation:* Valid XML/JSON, Importable into Camunda/Temporal.
*   [ ] **D. Documentation/Analysis:** Markdown reports, Architecture Diagrams.
    *   *Validation:* Peer Review, Clarity check.

---

## 4. Problem & Success Criteria

**Problem:** [What is broken or missing?]

**Success Criteria (Definition of Done):**
- [ ] [Functional Requirement 1]
- [ ] [Functional Requirement 2]
- [ ] Artifact passes its specific validation (Docker build, Lint, etc.).
- [ ] No "Slop" (Clean, minimal implementation).

---

## 5. Functional Requirements

**User Scenarios:**
- "When user does X → system should Y"

**System Behaviors:**
- "On event Z, trigger job Q"

---

## 6. Plan & Phases

| Phase | Description | Est. Time |
|-------|-------------|-----------|
| 1 | Setup & Definition | |
| 2 | Implementation | |
| 3 | Validation | |

---

## 7. File Map (The Blueprint)

**Exact files to create/modify INSIDE this Task Folder:**
*(Agent: Be specific.)*

*   `[New]` `./Dockerfile` (if Track B)
*   `[New]` `./process.bpmn` (if Track C)
*   `[New]` `./src/agent.ts`

---

## 8. AI Agent Guardrails

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