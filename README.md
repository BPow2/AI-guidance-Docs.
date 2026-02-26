# AI Project Templates

Three markdown templates for structuring software projects built with AI coding agents.

If you've used Claude, Cursor, Copilot, or similar tools to build a project, you've probably hit the same problems: the AI adds libraries you didn't want, combines files when you wanted them separate, builds features you never asked for, or loses track of where it is in a multi-step build. These templates fix that by giving the AI clear requirements, a step-by-step plan, and hard constraints before it writes a single line of code.

## The Files

### `PRD_TEMPLATE.md` — Product Requirements Document

Defines **what** you're building. This is the source of truth for the project's scope.

- App overview and elevator pitch
- "What this app IS" and "IS NOT" — sets boundaries upfront
- Feature list with checkbox requirements
- Test data and success criteria

**Why it matters:** Without a PRD, AI agents tend to make assumptions about what you want. A clear PRD means fewer "that's not what I asked for" moments.

### `PLAN_TEMPLATE.md` — Step-by-Step Build Roadmap

Defines **how** to build it, in what order, and how to know when each step is done.

- Phase 1 (MVP) and Phase 2 (Enhancements) separation
- Each step has a goal, checkbox tasks, and a "Done when" criteria
- Forces the AI to complete and verify each step before moving on

**Why it matters:** AI agents love to jump ahead or build everything at once. The plan forces a sequential, testable workflow where you have a working project at every stage.

### `AI_RULE_TEMPLATE.md` — Non-Negotiable Rules & Constraints

Defines **what the AI is NOT allowed to do**. This is the guardrail file.

- Locked tech stack with explicit "do not use" alternatives
- Allowed dependencies list (prevents unnecessary installs)
- Exact project file structure
- Code style, error handling, and security rules
- Optional sections for AI/LLM-specific and UI-specific rules
- Scope boundaries — the most important section

**Why it matters:** This file prevents the most common AI coding mistakes. The "Scope Boundaries" section alone will save you hours of undoing unwanted features.

## Usage

1. Copy the three templates into your project root
2. Rename them to `PRD.md`, `PLAN.md`, and `AI_RULE.md`
3. Fill in the `[bracketed placeholders]` with your project-specific content
4. Read the `<!-- guidance comments -->` for tips on what to write in each section
5. Delete the guidance comments once you're done filling things in
6. Give all three files to your AI agent as context when starting a build

### Example Workflow

```
You: Here are my project docs. [attach PRD.md, PLAN.md, AI_RULE.md]
     Start with Step 1 from PLAN.md.

AI:  [reads all three files, builds Step 1, verifies it works]

You: Looks good. Move to Step 2.

AI:  [builds Step 2, tests it against Step 1's output]

...and so on until the project is complete.
```

## What These Templates Work For

These are project-type agnostic. They've been used for:

- Web applications (React, Streamlit, Flask, etc.)
- CLI tools and scripts
- API services and backends
- Python libraries and packages
- AI/LLM-powered applications
- Data pipelines and automation tools

## Setting Up AI Agent Rules in Your IDE

Most AI coding tools support a project-level instructions file that the agent reads before every interaction. Add one of these files to your project root so the AI automatically follows your templates without you having to remind it.

### Claude Code — `CLAUDE.md`

Create a `CLAUDE.md` file in your project root:

```markdown
Before writing ANY code, you MUST read and follow these project documents:

1. PRD.md — Contains all feature requirements and scope boundaries. Do not build features not listed here.
2. AI_RULE.md — Contains the locked tech stack, code style rules, and non-negotiable constraints. Follow every rule exactly.
3. PLAN.md — Contains the step-by-step build roadmap. Only work on the current step. Do not skip ahead. Mark tasks as complete when done.

If your planned action would conflict with any of these documents, stop and ask me before proceeding.
```

### Cursor — `.cursorrules`

Create a `.cursorrules` file in your project root with the same content:

```markdown
Before writing ANY code, you MUST read and follow these project documents:

1. PRD.md — Contains all feature requirements and scope boundaries. Do not build features not listed here.
2. AI_RULE.md — Contains the locked tech stack, code style rules, and non-negotiable constraints. Follow every rule exactly.
3. PLAN.md — Contains the step-by-step build roadmap. Only work on the current step. Do not skip ahead. Mark tasks as complete when done.

If your planned action would conflict with any of these documents, stop and ask me before proceeding.
```

### Windsurf — `.windsurfrules`

Create a `.windsurfrules` file in your project root with the same content as above.

### Google Gemini CLI — `GEMINI.md`

Create a `GEMINI.md` file in your project root with the same content as above.

### Other Tools (Copilot, Cline, Aider, etc.)

Most AI coding tools look for an instructions file in the project root. Check your tool's documentation for the exact filename — common patterns include `.instructions`, `.ai-rules`, or a setting in the tool's config. The content should be the same regardless of tool.

> **Tip:** You can customize the instructions per tool. For example, you might add "Always ask before creating new files" for agents that tend to scaffold aggressively, or "Run tests after every step" for agents that skip verification.

---

## Tips

- **Fill out PRD.md first** — you need to know what you're building before you plan how
- **Be specific in AI_RULE.md** — vague constraints get ignored. "No Flask" is better than "keep it simple"
- **The Scope Boundaries section saves the most time** — list everything you DON'T want built. AI agents are eager helpers; they'll build features you never asked for if you don't explicitly tell them not to
- **Keep PLAN.md steps small** — each step should be completable and testable in one session. If a step has 15+ tasks, break it into two steps
- **Use the checkbox format** — it gives you and the AI a clear way to track progress

## License

MIT — use however you want.
