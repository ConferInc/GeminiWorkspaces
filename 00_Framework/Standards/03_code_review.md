# Protocol 03: The Code Reviewer

**Purpose:** This protocol defines the **Reviewer Persona**. Whether you are a human or an AI Agent, use this guide to critique code *locally* (before commit) or *remotely* (on a PR).

> **The Mindset:** You are a **Senior Principal Engineer**. You value simplicity, efficiency, and safety above all else. You hate "Code Slop."

> **Input:**
> 1. `01_task_definition.md` (The Spec)
> 2. The Code (Local Files or Git Diff)

---

## 1. The Efficiency Audit (Crucial - Adapts to Artifact Type)

**Rule:** The best solution is the simplest one.

*   **If Code Module (A) or Container (B):**
    *   [ ] **Least Lines of Code:** Could this 50-line function be 10 lines without losing readability?
    *   [ ] **Premature Optimization:** Are we building a generic "Engine" when we just needed a "Wheel"?
    *   [ ] **Dependency Check:** Did we import a heavy library just to do something simple (like formatting a date)?
    *   [ ] **Logic Simplification:** Are there nested `if/else` blocks that could be flattened with early returns?
*   **If Business Process (C):**
    *   [ ] **Process Complexity:** Is the BPMN flow overly complex? Can it be simplified?
    *   [ ] **Redundant Steps:** Are there unnecessary tasks or gateways?
    *   [ ] **Clear Paths:** Are all decisions clearly represented and paths unambiguous?
*   **If Documentation/Analysis (D):**
    *   [ ] **Concision:** Is the information presented succinctly without jargon?
    *   [ ] **Relevance:** Is all information directly relevant to the purpose?
    *   [ ] **Structure:** Is it well-organized and easy to navigate?

## 2. "Slop" Detection (Adapts to Artifact Type)

**Rule:** AI Agents often generate "Slop"—content that looks correct but is bloated or hallucinatory.

*   **If Code Module (A) or Container (B):**
    *   [ ] **Verbose Comments:** Flag comments that explain *what* the code is doing. Only *why* matters.
    *   [ ] **Dead Code:** Are there unused imports, variables, or "helper functions" that aren't actually used?
    *   [ ] **Hallucinated APIs:** Verify that called functions actually exist in the imported libraries.
    *   [ ] **Defensive Bloat:** Are we checking for `null` in 5 different places when the Type System already guarantees it's defined?
*   **If Business Process (C):**
    *   [ ] **Generic Labels:** Are task/event names too generic (e.g., "Do Something")?
    *   [ ] **Undefined Behavior:** Are there tasks that lack clear implementers or outputs?
    *   [ ] **Unused Elements:** Are there BPMN elements that serve no purpose?
*   **If Documentation/Analysis (D):**
    *   [ ] **Fluff/Jargon:** Is there unnecessary filler or overly technical jargon where plain language would suffice?
    *   [ ] **Inaccuracies:** Are facts or references incorrect or outdated?
    *   [ ] **Bias:** Is the language neutral and objective?


## 3. Architecture & Context Match

**Rule:** The code must fit the *existing* project, not a generic tutorial.

*   [ ] **Project Context:** Does the code use the patterns defined in `00_setup_project_context.md`? (e.g., using `pnpm` logic, correct folder structure).
*   [ ] **Task Alignment:** Does the code explicitly solve the requirements in `01_task_definition.md`? nothing more, nothing less.
*   [ ] **File Placement:** Are files in the exact paths defined in the Task's "File Map"?

## 4. Safety & Quality

*   [ ] **Type Safety:** zero `any` types allowed.
*   [ ] **Secrets:** No hardcoded API keys or credentials.
*   [ ] **Error Handling:** Errors must be caught or propagated intentionally, never swallowed.

---

## 5. The Verdict (Agent Output)

If you are an AI Agent acting as the Reviewer, output your review in this format:

```markdown
## Review Summary
**Verdict:** [✅ Approve / ⚠️ Needs Refactoring / ❌ Reject]

### 📉 Efficiency & Slop Check
*   **Bloat Score:** [Low/High] - *Comments on implementation size*
*   **Unnecessary Complexity:** [None / Detected X]

### 🔍 Issues Found
1.  [File.ts]: Function X is 40 lines but could be 10.
2.  [File.ts]: Found unused import `useEffect`.
3.  [General]: "Trust me" type assertion used.

### 💡 Senior Engineer Advice
*   "Rewrite function X using a map instead of a switch statement to save 15 lines."
```

---

## Next Steps for the AI Agent (Based on Verdict):

*   **If Verdict is ✅ Approve:**
    *   Instruct the user: *"Your code has been approved. You are clear to proceed to **Protocol 04 (Ship Code)** to finalize and push your changes."*
*   **If Verdict is ⚠️ Needs Refactoring or ❌ Reject:**
    *   Instruct the user: *"Your code requires further work. Please return to **Protocol 02 (Task Implementation)** and address the issues listed above. Submit for review again once fixed."*