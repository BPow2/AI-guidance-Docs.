# AI_RULE.md — [Project Name] Non-Negotiable Rules & Constraints

<!--
  HOW TO USE THIS TEMPLATE:
  1. Fill in your tech stack, dependencies, and project structure
  2. Customize the code rules to match your standards
  3. Include only the optional sections relevant to your project
  4. The "Scope Boundaries" section is critical — it prevents the AI from over-building
  5. Delete all guidance comments before feeding to an AI agent
-->

## Tech Stack (LOCKED — do not deviate)

<!--
  List every major technology choice. Use the "Notes" column to say 
  what's NOT allowed — AI agents love to substitute alternatives.
-->

| Component       | Tool                          | Notes                                      |
|-----------------|-------------------------------|---------------------------------------------|
| Language        | [e.g., Python 3.10+]         | [e.g., Only language allowed]               |
| [Component]     | [Tool]                        | [Constraints / what NOT to use]             |
| [Component]     | [Tool]                        | [Constraints / what NOT to use]             |
| [Component]     | [Tool]                        | [Constraints / what NOT to use]             |

---

## Allowed Dependencies

<!--
  Explicitly list every package the AI is allowed to install.
  Prevents the AI from pulling in heavy or unnecessary frameworks.
-->

```
[package-1]
[package-2]
[package-3]
```

**Do NOT add any additional packages without explicit user approval.**

---

## Project Structure

<!--
  Define the exact file structure. AI agents tend to create extra files 
  or merge everything into one. Be explicit.
-->

```
[project-root]/
├── [file 1]          # [Purpose]
├── [file 2]          # [Purpose]
├── [file 3]          # [Purpose]
├── .env              # Secrets (never committed/shared)
└── README.md         # Documentation
```

- Each module is a separate file — do NOT combine modules
- Do NOT create files beyond those listed unless explicitly asked
- All configuration and constants go in [config file]
- All shared helpers go in [utils file]

---

## Code Rules

### Style & Quality

- Use clear, descriptive function names — no abbreviations
- Every function must have a docstring explaining what it does, its args, and return value
- Use type hints on all function signatures
- Keep functions short — one clear responsibility per function
- Handle errors with try/except — never let the app crash silently

### Error Handling

- Every external call ([list: API calls, file I/O, network requests, etc.]) must be wrapped in try/except
- Errors must show user-friendly messages — not raw tracebacks
- [Partial failure behavior — e.g., "If one item fails, continue processing the rest"]

### Secrets & Security

- NEVER hardcode API keys, passwords, or credentials anywhere
- All secrets load from .env via [config file]
- .env must never be shared or committed

---

<!--
  OPTIONAL SECTIONS — include only the ones relevant to your project.
  Delete any that don't apply.
-->

## AI/LLM Rules

<!--
  Include if your project uses AI/LLM APIs.
-->

- All prompts must use a consistent structure: [e.g., "Role → Context → Task → Format → Rules"]
- Prompts must request structured output (JSON/XML) with an explicit schema
- Always parse LLM responses through a dedicated parser — never assume clean output
- Never hardcode domain-specific content into prompts — pass it dynamically
- Include guardrails in every prompt: [e.g., "Base analysis on actual content provided. Do not fabricate."]

## UI Rules

<!--
  Include if your project has a user interface (web, desktop, CLI with menus, etc.)
-->

- [Workflow pattern — e.g., "Linear flow: Step A → Step B → Step C"]
- [Progressive disclosure — e.g., "Each step only appears after the previous completes"]
- [Loading states — e.g., "Every long-running operation shows a loading indicator"]
- [User control — e.g., "User must review output before any external action is taken"]

---

## Scope Boundaries — Do NOT Build Unless Asked

<!--
  THIS IS THE MOST IMPORTANT SECTION FOR AI AGENTS.
  List anything that's a natural extension of your project but out of scope.
  Be generous — better to list too many than too few.
-->

- [e.g., Batch/multi-item processing]
- [e.g., Database or persistent storage beyond simple file logging]
- [e.g., User authentication or login system]
- [e.g., Analytics, tracking, or dashboards]
- [e.g., Unit test suites unless explicitly requested]
- Any feature not listed in PRD.md
