# Confer Solutions AI: Engineering Standards

**Welcome to the Team.**

This folder contains the **Standard Operating Protocols (SOP)** for our engineering workflow. Whether you are using **Gemini**, **Claude**, **Cursor**, or any other AI tool, you **MUST** follow these protocols to ensure consistency and quality.

## The Numbered Workflow

We use a strict **Numbered Protocol**. Do not guess what to do next; follow the numbers.

**Only the following numbered files (00-04) are for your direct interaction.** Other files in this `00_Framework` directory (e.g., in `Templates/`) are used by the AI Agents for their internal operations and do not require your direct attention.

### Step 0: One-Time Setup
*   **File:** `00_setup_project_context.md`
*   **Action:** When you start a new project (or join one), fill this file out **once**.
*   **Why:** It tells your AI Agent about our specific tech stack, commands, and rules.

### Step 1: Define the Work
*   **File:** `01_task_definition.md`
*   **Action:** Before you write a single line of code, create a copy of this file and fill it out with your Agent.
*   **Prompt:** *"Help me create a task plan for [Feature Name] using `01_task_definition.md`."*

### Step 2: Build It
*   **File:** `02_task_implementation.md`
*   **Action:** Use this guide to execute the task you defined in Step 1.
*   **Prompt:** *"Implement the code for [Task Name] following the rules in `02_task_implementation.md`."*

### Step 3: Review It (The Gatekeeper)
*   **File:** `03_code_review.md`
*   **Action:** Use this guide to critique code *locally* before you even think about pushing.
*   **Prompt:** *"Act as the Reviewer. Critique this code against `03_code_review.md`. Look for Slop and Inefficiency."*

### Step 4: Ship It
*   **File:** `04_ship_code.md`
*   **Action:** If Step 3 approved your work, use this to commit and push.
*   **Prompt:** *"I am ready to commit. Run the verification steps in `04_ship_code.md`."*

---

## Why we do this
By forcing every AI Agent to read the same "Rules of the Road," we ensure that **Gemini** code looks like **Claude** code, which looks like **Cursor** code. This makes our codebase maintainable, predictable, and high-quality.
