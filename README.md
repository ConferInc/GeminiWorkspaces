# Confer Solutions AI: Engineering Hub 🚀

**Welcome to the Team!**

This repository is your central hub. It contains **"The Framework"** (Standards) and **"The Work"** (Projects).

> **The Golden Rule:** We do not write code alone. We rely on a **Multi-Agent Workflow**. You act as the Orchestrator between a **Builder Agent** (writing code) and a **Reviewer Agent** (checking code).

---

## 📂 Repository Structure

*   **`00_Framework/`** (THE LAW) 🏛️
    *   **`Standards/`**: The "Numbered Protocols" (00-04). **These are your tools.**
    *   **`Templates/`**: Internal files for the Agents. (Ignore these).
*   **`Projects/`** (THE WORK) 🛠️
    *   **`Confer/`**, **`MoXi/`**, **`Odyssey/`**: Shared team projects.
*   **`User_Workspaces/`** (THE PLAYGROUND) 🎡
    *   Create your own folder here (e.g., `User_Workspaces/Anjali/`) to experiment safely.

---

## 🚦 The "Intern Survival Guide" (How to Work)

Follow this exact sequence for **every single task**. Do not skip steps.

### 🛑 Step 0: One-Time Setup
*   **File:** `00_Framework/Standards/00_setup_project_context.md`
*   **Action:** When you join a project, fill this out **once**.
*   **Why:** It teaches the Agents who you are and what tech stack we use.

---

### 1️⃣ Step 1: The Plan (Agent A)
*   **Goal:** Define *what* to build.
*   **File:** `01_task_definition.md`
*   **Action:** Open **Agent A** (e.g., Claude) and paste:
    > "I need to build [Feature Name]. Help me create a detailed plan using `01_task_definition.md`."
*   **Result:** You get a `task.md` file. **Save it.**

---

### 2️⃣ Step 2: The Build (Agent B)
*   **Goal:** Write the code.
*   **File:** `02_task_implementation.md`
*   **Action:** Open **Agent B** (e.g., Cursor/Gemini) and paste:
    > "Read this `task.md` plan. Implement the code following the strict rules in `02_task_implementation.md`."
*   **Result:** Agent B writes the code files.

---

### 3️⃣ Step 3: The "Fight" (The Loop) 🥊
**This is the most important step.** Do not trust Agent B.

*   **Goal:** Critique and Fix.
*   **File:** `03_code_review.md`
*   **Action:** Switch back to **Agent A** (The Reviewer) and paste:
    > "Act as the Senior Reviewer. Read the code Agent B just wrote. Critique it against `03_code_review.md`. Look for 'Code Slop' and inefficiency."

#### 🔄 The Loop Scenario (What happens next?)
*   **Scenario 1: Agent A says "❌ REJECT"**
    1.  Copy Agent A's feedback (the list of errors).
    2.  Paste it to **Agent B** (The Builder).
    3.  Say: *"The Reviewer found these issues. Fix them and show me the new code."*
    4.  **REPEAT** this loop until Agent A says "✅ APPROVE".

*   **Scenario 2: Agent A says "✅ APPROVE"**
    *   Great! You are ready to ship.

---

### 4️⃣ Step 4: The Ship (Agent A or B)
*   **Goal:** Commit and Push.
*   **File:** `04_ship_code.md`
*   **Action:** Paste:
    > "I am ready to ship. Run the pre-commit checks in `04_ship_code.md`."
*   **Result:** The Agent verifies everything one last time, you commit, and you push!

---

## ❓ FAQ for Interns

**Q: Can I use just one Agent?**
A: No. Using two Agents (e.g., Claude for Planning/Reviewing, Cursor for Building) forces a "second opinion" and catches hallucinations.

**Q: What is "Code Slop"?**
A: Bloated code. Comments that say `// adds 1`. Imports you don't use. **Protocol 03** teaches the Reviewer to hate this.

**Q: Where do I put my personal files?**
A: In `User_Workspaces/[YourName]/`. Do not clutter the `Projects/` folder with experiments.
