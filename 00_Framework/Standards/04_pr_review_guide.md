# Protocol 04: PR Review Guide

**Purpose:** A standardized framework for reviewing code. Whether you are a human or an AI Agent, use this guide to critique Pull Requests effectively, ensuring they match the task definition and project standards.

> **Input:** You need the `01_task_definition.md` (the Spec) and the **Diff/PR** to perform this review.

---

## 1. Context Match (The "Did we build the right thing?" Check)

Compare the PR against the `01_task_definition.md` file.

*   [ ] **Scope:** Does the PR implement the *exact* Requirements defined in the Task?
*   [ ] **Scope Creep:** Does the PR include "extra" features not requested? (Flag as warning).
*   [ ] **Completeness:** Are all "Success Criteria" from the Task met?

## 2. Architecture & Patterns (The "Did we build it right?" Check)

Reference `00_setup_project_context.md` for approved patterns.

*   [ ] **Pattern Consistency:** Does the code follow the Project's architectural patterns (e.g., Repository pattern, Component structure)?
*   [ ] **Tech Stack:** Did we use *only* approved libraries? (No new random npm packages without approval).
*   [ ] **File Placement:** Are files in the correct directories? (e.g., Server Actions in `app/actions`, not `components/`).

## 3. Code Quality (The "Is it clean?" Check)

*   [ ] **Type Safety:** Are there `any` types? Are assertions used safely?
*   [ ] **Readability:** Is the logic easy to follow? Are variables named descriptively?
*   [ ] **Simplicity:** Is there over-engineering? (e.g., creating a factory pattern for a single button).
*   [ ] **Error Handling:** Are errors caught and handled gracefully, or just swallowed?

## 4. Security & Safety (The "Is it safe?" Check)

*   [ ] **Secrets:** Are there any API keys or credentials hardcoded? (IMMEDIATE BLOCKER).
*   [ ] **Input Validation:** Is user input validated (e.g., Zod schemas)?
*   [ ] **Authorization:** Does the code check if the user *can* perform this action?

## 5. Documentation (The "Is it maintainable?" Check)

*   [ ] **Docstrings:** Do public functions have JSDoc/comments explaining *why*?
*   [ ] **Updates:** Did the author update `README.md` or Architecture docs if necessary?

---

## 6. The Verdict

Conclude the review with one of the following statuses:

*   **✅ Approve:** The code is solid, safe, and meets requirements.
*   **⚠️ Request Changes:** There are specific issues (bugs, safety, logic) that must be fixed.
*   **❌ Reject:** The approach is fundamentally wrong or violates core architecture.

**Review Comment Template:**

```markdown
## Review Summary
**Status:** [Approve / Request Changes]

### 🔍 findings
- [Critical/Minor] Issue description...
- [Suggestion] Improvement idea...

### 🛡️ Safety Check
- Secrets: [Pass/Fail]
- Validation: [Pass/Fail]

### 📋 Requirement Check
- Matches Protocol 01 Spec: [Yes/No]
```
