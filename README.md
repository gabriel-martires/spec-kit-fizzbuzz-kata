# spec-kit-fizzbuzz-kata

Built on top of **GitHub Spec Kit**: https://github.com/github/spec-kit

Learn GitHub Spec Kit by building the classic **FizzBuzz** kata end-to-end using a **spec-driven workflow**:
**constitution → spec → plan → tasks → implement** (C# / .NET 10).

## Goal of the kata

Implement FizzBuzz in a way that is:
- **Test-first** (TDD with xUnit)
- **Simple** (minimal design, no overengineering)
- **Spec-driven** (specs are the source of truth, code serves the spec)

FizzBuzz rules (for input `N`):
- Print numbers from `1` to `N`
- For multiples of 3 print `Fizz`
- For multiples of 5 print `Buzz`
- For multiples of both print `FizzBuzz`

---

## Prerequisites

- A project initialized with Spec Kit (so `/speckit.*` slash commands are available in your AI assistant/chat).
- .NET 10 SDK installed (to run tests/build locally).

> Tip: You typically run these commands inside your AI assistant (e.g., Copilot Chat) while your workspace is open.

---

## Workflow (step-by-step)

Below is the suggested flow for this kata. Each step includes:
1) what it does, and
2) an example of what to type.

### 1) `/speckit.constitution` — Define non-negotiables (guardrails)

**What it does:**  
Creates or updates the project “constitution”: the principles that must be followed in all later steps (testing standards, simplicity rules, conventions, etc.).

**Example command:**
```text
/speckit.constitution Create a lightweight constitution for a FizzBuzz coding kata in .NET 10 (C#). Principles: TDD-first with xUnit; keep design minimal (no overengineering), clear naming and small functions.
```

### 2) `/speckit.specify` — Write the spec (WHAT/WHY, not HOW)

**What it does:**
Generates a structured feature specification describing requirements, edge cases, and acceptance criteria. Keep this step free of implementation details.

**Example command:**
```text
/speckit.specify Implement the FizzBuzz kata. The user provides an integer N. For each integer from 1 to N return a sequence of outputs where multiples of 3 are "Fizz", multiples of 5 are "Buzz", multiples of both are "FizzBuzz", otherwise the number itself.
```

### (Optional) 3) `/speckit.clarify` — Resolve ambiguities before planning

**What it does:**
Asks clarifying questions / flags assumptions so you can fix gaps in the spec before generating a plan.

**Example command:**
```text
/speckit.clarify
```

Typical things to clarify for FizzBuzz:
- Should the solution print or return a list?
- What should happen when `N <= 0`? (empty list vs error)
- Do we need a CLI, or only a library + tests?

### 4) `/speckit.plan` — Convert spec into a technical plan (HOW)

**What it does:**
Creates a technical implementation plan aligned with the constitution and the spec: architecture choices, testing approach, project layout, and validation scenarios.

**Example command:**
```text
/speckit.plan Use .NET 10 with a small library project and an xUnit test project. Implement FizzBuzz as a pure function that returns IReadOnlyList<string>. Keep it minimal. Add unit tests covering core rules.
```

### (Optional) 5) `/speckit.checklist` — “Unit tests for English” (coverage check)

**What it does:**
Generates a checklist to verify you didn’t miss important requirements categories (UX, error handling, testing, etc.).

**Example command:**
```text
/speckit.checklist
```

### (Optional) 6) `/speckit.analyze` — Consistency check across artifacts

**What it does:**
Checks if spec/plan/tasks are consistent with each other and the constitution (catch contradictions early).

**Example command:**
```text
/speckit.analyze
```

### 7) `/speckit.tasks` — Break the plan into small, executable tasks

**What it does:**
Produces a task list (small steps, usually 1–2 files per task) derived from your plan and supporting docs.

**Example command:**
```text
/speckit.tasks
```

### 8) `/speckit.implement` — Implement the tasks (guided by the spec)

**What it does:**
Executes the task list to generate/update code consistent with the spec, plan, and constitution.

**Example command:**
```text
/speckit.implement
```

## What files should appear?

Depending on your Spec Kit setup, you’ll typically see:
- A constitution file under `.specify/...` (project principles)
- A feature folder (often under `specs/<feature-branch>/`) containing:
  - `spec.md` (requirements)
  - `plan.md` (technical plan)
  - `tasks.md` (task breakdown)
  - possibly extra supporting docs (research, quickstart, contracts, etc.)

## Contributing / Learning Notes

This repo is intentionally small and educational.
If you change requirements, update the spec first, then regenerate plan and tasks to keep everything aligned.