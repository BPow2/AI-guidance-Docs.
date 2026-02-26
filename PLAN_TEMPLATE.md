# PLAN.md — [Project Name] Step-by-Step Build Roadmap

<!--
  HOW TO USE THIS TEMPLATE:
  1. Each step should map to a feature or module from PRD.md
  2. Steps should be ordered so each one builds on the last
  3. AI agents should complete each step fully before moving on
  4. Replace [bracketed placeholders] and delete guidance comments before use
-->

> **RULE: Complete each step fully before moving to the next. Do not skip ahead.**
> After completing each step, verify it works by testing, then check off the tasks and move on.

<!--
  STEP WRITING GUIDELINES:
  
  Each step needs three things:
  - GOAL: One sentence — what are we trying to achieve?
  - TASKS: 4-8 checkboxes — concrete, specific actions (not vague)
  - DONE WHEN: How do you know this step is finished?
  
  Ordering principles:
  1. Foundation first — config, utilities, project structure
  2. Core modules — build and test each one before integrating
  3. Integration — connect modules together, wire into UI if applicable
  4. Polish — docs, testing, cleanup
  5. Stretch goals — enhancements in a separate phase
  
  Keep tasks testable. "Implement the parser" is vague. 
  "Implement parse_response() that extracts X, Y, Z from the API response" is testable.
-->

---

## Phase 1: MVP

### Step 1: [Project Scaffolding & Config]
**Goal:** [Set up the project structure and verify it runs.]

- [ ] [Create config/constants file — load env vars, define settings]
- [ ] [Create utils/helpers — shared functions needed across modules]
- [ ] [Create minimal entry point that runs without errors]
- [ ] [Verify it runs — e.g., "Run the app and confirm no errors"]

**✅ Done when:** [Project runs, structure is in place, no errors.]

---

### Step 2: [Core Module / Feature 1]
**Goal:** [Build and test the first core piece of functionality.]

- [ ] [Implement primary function]
- [ ] [Implement supporting/helper functions]
- [ ] [Handle errors and edge cases specific to this module]
- [ ] [Test with real input — verify output matches expected format]

**✅ Done when:** [Module produces correct output for 2-3 test inputs.]

---

### Step 3: [Core Module / Feature 2]
**Goal:** [Build the next piece, integrating with Step 2's output.]

- [ ] [Implement primary function — takes Step 2's output as input]
- [ ] [Handle edge cases: malformed input, API failures, etc.]
- [ ] [Test standalone and then end-to-end with Step 2]

**✅ Done when:** [Steps 2 → 3 work together end-to-end with correct output.]

---

### Step 4: [Integration, Polish & Documentation]
**Goal:** [Connect everything, clean up, and verify the full workflow.]

- [ ] [Wire all modules together into the complete workflow]
- [ ] [Review code for consistency, docstrings, and clean formatting]
- [ ] [Write README.md — overview, setup, how to run, known limitations]
- [ ] [Test the full end-to-end flow with multiple real inputs]

**✅ Done when:** [Complete workflow runs reliably and project is documented.]

---

## Phase 2: Enhancements

<!--
  Only start Phase 2 after Phase 1 is fully working.
  Order by priority — most impactful first.
  Each enhancement should be independently valuable.
  Include time estimates if helpful for planning.
-->

### Step 5: [Enhancement 1] (~[time estimate])
[Why this matters: one line justifying the value.]

**Goal:** [What this enhancement achieves.]

- [ ] [Task]
- [ ] [Task]
- [ ] [Test the enhancement end-to-end]

**✅ Done when:** [Clear completion criteria.]

---

### Step 6: [Enhancement 2] (~[time estimate])
[Why this matters: one line justifying the value.]

**Goal:** [What this enhancement achieves.]

- [ ] [Task]
- [ ] [Task]
- [ ] [Test the enhancement end-to-end]

**✅ Done when:** [Clear completion criteria.]
