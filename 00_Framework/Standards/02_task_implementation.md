# Protocol 02: Task Implementation (The "Anti-Slop" Protocol)

**Purpose:** This guide defines **HOW** to write code. It is not just about getting it done; it is about getting it done *right*. It prevents "Code Slop"—verbose, buggy, unmaintainable, or hallucinated code.

> **Input:** You must have a completed `01_task_definition.md` (The Spec) and `00_setup_project_context.md` (The Config).

---

## Phase 1: The "Stop & Think" (Before You Code)

**Agent: Do not generate a single line of code until you answer these questions internaly:**

1.  **Is this the simplest way?**
    *   *Slop:* Creating a `UserFactoryManager` to create a user.
    *   *Quality:* Just writing a `createUser` function.
2.  **Am I duplicating logic?**
    *   *Slop:* Re-implementing a date formatter because you didn't check `src/utils`.
    *   *Quality:* Check existing utils/components first.
3.  **Do I understand the Project Structure?**
    *   *Slop:* Putting API routes in `components/`.
    *   *Quality:* Checking `Protocol 00` for the correct directories.

---

## Phase 2: Implementation Standards (Zero Tolerance)

### 1. Code Hygiene (No "Slop")
*   **No Unused Imports:** Remove them immediately.
*   **No `console.log`:** Debugging leftovers must be deleted.
*   **No Verbose Comments:**
    *   *Bad:* `// This function adds two numbers` -> `const add = (a, b) => a + b`
    *   *Good:* `// Using Kahan summation to avoid floating point errors`
*   **No Magic Numbers:** Use named constants.

### 2. Type Safety (Strict)
*   **No `any`:** Ever. If you are stuck, ask the user or define a `unknown` with a Zod schema.
*   **No `as Type` assertions:** Unless absolutely necessary and documented why.
*   **Return Types:** Explicitly type the return values of public functions/APIs.

### 3. Error Handling (Robust)
*   **No Silent Failures:** `catch (e) { console.log(e) }` is forbidden.
*   **Fail Fast:** Validate inputs at the start of the function.
*   **User Visibility:** If an error impacts the user, ensure it propagates to the UI (e.g., toast, alert).

---

## Phase 3: The Build Loop

**Step 1: Scaffolding**
*   Create the files defined in `01_task_definition.md` (File Map).
*   *Verification:* Does the file structure match the plan?

**Step 2: Logic Implementation**
*   Write the core logic.
*   *Constraint:* Keep functions small (< 50 lines). If it grows, split it.

**Step 3: Verification (The "Does it actually work?" Check)**
*   **Run the Linter:** Execute the command from Protocol 00 (e.g., `pnpm lint`). Fix ALL warnings.
*   **Run Types:** Execute the command from Protocol 00 (e.g., `pnpm type-check`).
*   **Test:** Write the test *before* or *during* implementation, not after.

---

## Phase 4: Self-Correction (The "Agent Review")

**Before you tell the user you are "Done", review your own code against this checklist:**

*   [ ] **Did I follow the plan?** Compare result vs `01_task_definition.md`.
*   [ ] **Did I add "Code Slop"?** (Unnecessary files, over-engineering, comments).
*   [ ] **Did I break anything?** (Check existing tests).
*   [ ] **Is it clean?** (Formatting, naming conventions).

> **Final Rule:** If you are unsure about a pattern, **ASK**. It is better to wait for clarification than to generate 500 lines of garbage code.