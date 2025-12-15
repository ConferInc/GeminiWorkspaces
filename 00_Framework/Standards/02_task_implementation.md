# Protocol 02: Task Implementation (The "Anti-Slop" Protocol)

**Purpose:** This guide defines **HOW** to write code. It is not just about getting it done; it is about getting it done *right*.

> **Input:** You must have a completed `01_task_definition.md` (The Spec) and `00_setup_project_context.md` (The Config).

---

## Phase 1: The "Stop & Think" (Before You Code)

**Agent: Do not generate a single line of code until you answer these questions internaly:**

1.  **Where am I?**
    *   *Check:* Am I in the dedicated Task Folder (`User_Workspaces/...`)?
2.  **What is the Artifact?**
    *   *Check:* Is this a Code Module, Container, or BPMN File? (See Protocol 01 Section 3).
3.  **Is this the simplest way?**
    *   *Slop:* Creating a `UserFactoryManager` to create a user.
    *   *Quality:* Just writing a `createUser` function.

---

## Phase 2: Implementation Standards (Zero Tolerance)

### 1. Code Hygiene (No "Slop")
*   **No Unused Imports:** Remove them immediately.
*   **No `console.log`:** Debugging leftovers must be deleted.
*   **No Verbose Comments:** Only explain *why*.

### 2. Type Safety (Strict)
*   **No `any`:** Ever.
*   **No `as Type` assertions:** Unless absolutely necessary and documented why.

---

## Phase 3: The Build Loop

**Step 1: Scaffolding**
*   Create the files defined in `01_task_definition.md` (File Map).

**Step 2: Logic Implementation**
*   Write the core logic. Keep functions small (< 50 lines).

**Step 3: Verification (Based on Artifact Type)**
*   **If Code Module:** Run `pnpm lint` and `pnpm type-check`.
*   **If Container:** Run `docker build .` to verify it builds.
*   **If BPMN:**
    *   **XML Check:** Verify it is valid XML.
    *   **Logic Check:** Verify the flow is logical (Start -> End). No dead ends. No disconnected nodes.
    *   **Camunda Check:** Ensure all Service Tasks have a `zeebe:taskDefinition` type.

---

## Phase 4: Self-Correction (The "Agent Review")

**STOP.** Do not tell the user you are "Done." Do not ask the user to commit. Your task is not complete until a separate **Reviewer Agent** (using Protocol 03) has approved your work.

**Your instruction to the user (or the Reviewer Agent) is:**
*"I have completed the implementation of the task defined in `01_task_definition.md`. I am now ready for a review. Please use the **Reviewer Agent** (Protocol 03) to critique this code against the plan and quality standards."*

---
**The Loop:**
*   If the Reviewer Agent (Protocol 03) finds issues: Return to Protocol 02 and fix them.
*   If the Reviewer Agent (Protocol 03) approves: You are clear to proceed to **Protocol 04 (Ship Code)**.
