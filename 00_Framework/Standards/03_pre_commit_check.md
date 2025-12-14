# Protocol 03: Pre-Commit Check

**Purpose:** The final gatekeeper. This protocol ensures that nothing leaves the local environment without passing verification, documentation checks, and proper commit formatting.

> **Prerequisite:** Ensure `00_setup_project_context.md` is filled out. This protocol executes the commands defined there.

---

## 0. Grounding Documents (VERIFY BEFORE COMMITTING)

Before committing, verify changes align with the project's Source of Truth defined in `setup_project_context.md`.

**Documentation Sync Requirements:**
- [ ] If feature completed → Update status in your **Task Tracker**.
- [ ] If architecture changed → Update your **System Overview** or **Architecture Guide**.
- [ ] If schema/API changed → Update relevant **API/Schema Docs**.
- [ ] If breaking changes → Note in commit AND relevant docs.

**Commit should NOT proceed if:**
- Documentation is out of sync with code changes.
- Changes violate established architecture.
- Work is outside current scope without approval.

---

## 1. Safety Checks (DELETIONS & CONFIG)

**STOP before committing any file deletions or configuration changes:**

| Check | Verification |
|-------|--------------|
| **User approved deletion?** | Explicit confirmation required for meaningful files. |
| **Dangerous Zone?** | Check `setup_project_context.md` Section 5. |
| **Broken References?** | Ensure no other code/docs link to deleted files. |

**Red Flags (DO NOT DELETE without explicit approval):**
- Architecture decisions or PRDs.
- Configuration files (`.env.example`, `tsconfig.json`, etc.).
- Any file > 6 months old (may have historical value - consider archiving).

---

## 2. Pre-Commit Checklist

### 2.1 Code Verification

Execute the commands defined in `setup_project_context.md` (Section 4).

- [ ] **Type Check:** No errors.
- [ ] **Lint:** No errors or warnings.
- [ ] **Tests:** All tests pass.
- [ ] **Build:** Successful build (if applicable).

### 2.2 Documentation Verification

**CRITICAL:** Check documentation is up-to-date before committing.

| Change Type | Action |
|-------------|--------|
| New Feature/Package | Update **System Overview**. |
| New Env Variable | Update `.env.example` (NEVER commit `.env`). |
| Dependencies | Update `README.md` or installation docs. |
| Workflow Change | Update process documentation. |

### 2.3 File Cleanup

Before staging files, verify:

- [ ] No `console.log` or debug statements left.
- [ ] No commented-out code blocks.
- [ ] No `TODO` or `FIXME` comments (unless intentional and tracked).
- [ ] No `.env` or secret files staged.
- [ ] No build artifacts (`dist/`, `build/`) or `node_modules`.

---

## 3. Commit Message Standards

### 3.1 Format

We follow the **Conventional Commits** specification.

```
<type>(<scope>): <subject>

<body>

<footer>
```

### 3.2 Type (Required)

| Type | Use When |
|------|----------|
| `feat` | New feature for users. |
| `fix` | Bug fix for users. |
| `docs` | Documentation only. |
| `style` | Formatting, no code change. |
| `refactor` | Code change, no feature/fix. |
| `perf` | Performance improvement. |
| `test` | Adding/updating tests. |
| `chore` | Build, config, tooling. |

### 3.3 Scope (Optional)

Use the module, folder, or feature name affected (e.g., `api`, `auth`, `ui`).

### 3.4 Body (Required for Non-Trivial Changes)

The body should explain:
1. **What** was changed (summary).
2. **Why** the change was made (motivation).
3. **How** it affects the system (impact).

### 3.5 Example

```
feat(auth): add OAuth2 login flow

Implement Google and GitHub OAuth providers using NextAuth.

What:
- Added OAuth providers to auth configuration
- Created new login UI component
- Updated user schema to support external IDs

Why:
- Simplifies user onboarding
- requested in Q3 roadmap

Closes #123
```

---

## 4. Git Workflow Execution

### 4.1 Pre-Push Verification

```bash
# 1. Verify location and branch
git branch --show-current
# Expected: Your feature branch (NOT main/master)

# 2. Check status
git status
# Review all changes carefully
```

### 4.2 Staging & Committing

```bash
# Stage specific files (Preferred over 'git add .')
git add path/to/file

# Commit with message
git commit -m "type(scope): subject"
```

### 4.3 Pushing Changes

```bash
# Push to your feature branch
git push origin <your-branch-name>
```

---

## 5. Post-Commit

1.  **Verify Push:** Ensure `git status` is clean and changes appear on the remote.
2.  **Update Task:** Mark your task as `done` or `in-progress` in the project's **Task Tracker**.
3.  **Deployment:** If `setup_project_context.md` requires manual sync or deployment steps, perform them now.

---

## AI Agent Instructions

### Commit Creation Protocol

1.  **Context First:** Read `setup_project_context.md` to understand the environment.
2.  **Never Auto-Commit:** Always show `git status` and `git diff` first. Get user confirmation.
3.  **Detailed Messages:** Follow the Conventional Commits format exactly.
4.  **Docs First:** Check what docs need updating and include them in the same commit.
5.  **Verification:** Run the project-specific lint/test commands before asking to commit.

### Error Recovery

*   **Committed wrong files?** `git reset --soft HEAD~1` (Undo commit, keep changes).
*   **Wrong branch?** Push to correct branch, then clean up.
*   **Forgot file?** `git add <file>` then `git commit --amend`.
