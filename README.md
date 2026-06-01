# Project Initialization Documentation

This repository is a reusable instruction pack for setting up early project structure, project documentation, and agent-facing skills before active development begins.

It is not meant to be copied into a final project unchanged. Use it as a starter kit for an AI agent: the agent runs intake, selects relevant skills with user approval, generates canonical project docs under `docs/`, creates lightweight agent pointer files, then cleans up setup-only files.

## What This Repository Contains

- `initialize.md`: the main setup playbook an AI agent should follow.
- `read-yaml.py`: helper script that scans available `SKILL.md` files and prints their names/descriptions.
- `repo-structure/`: repository layout standards and structure references.
- `website-architecture/`: web app/site architecture planning, stack selection, route maps, data flow, and design-system requirements.
- `ui-frontend/`: UI design, frontend implementation rules, component references, and anti-generic design quality checks.
- `accessibility-mobile/`: mobile-responsive and touch-friendly web requirements.
- `ada-compliance/`: WCAG/ADA accessibility requirements.
- `plan/`: planning and implementation handoff guidance.

## How To Use It In A New Project

1. Make this repository's setup files available in the root of the new project.

   At minimum, the agent needs access to:

   - `initialize.md`
   - `read-yaml.py`
   - the skill directories relevant to the project
   - `pyproject.toml` and `uv.lock` if you want to use the included Python helper as-is

2. Ask the agent to follow `initialize.md`.

   The agent should not start scaffolding immediately. It must first ask enough questions to understand the project goal, runtime, framework, target users, validation workflow, supported agent tools, and cleanup expectations.

After that, the AI agent is responsible for the rest of the initialization workflow. The human should answer the agent's intake questions and approve important choices, but the agent should perform the repository setup work.

## What The Agent Must Do

1. Run skill discovery.

   ```powershell
   uv run read-yaml.py
   ```

   This prints the available skills so the agent can propose which ones apply.

2. Propose the relevant skills and get user confirmation.

   Common selections:

   - General project: `repo-structure`, `plan`
   - Website or web app: `repo-structure`, `website-architecture`, `ui-frontend`, `accessibility-mobile`, `ada-compliance`
   - Frontend-heavy app: add `ui-frontend` and use `ui-frontend/ui/design-quality.md`

3. Generate canonical project documentation.

   The target project should use `docs/` as the source of truth:

   ```text
   docs/
   |-- skills/
   |   |-- global-project-rules/
   |   |   `-- SKILL.md
   |   |-- <selected-skill>/
   |   `-- ...
   |-- plans/
   |-- checklist.md
   |-- documentation.md
   |-- structure.md
   `-- workflow.md
   ```

   For web projects, also create:

   - `docs/architecture.md`
   - `docs/routes.md`
   - `docs/component-map.md`
   - `docs/data-flow.md`
   - `docs/deployment.md`
   - `docs/design-system.md`
   - `docs/api-contract.md` when an API/backend exists

4. Create agent pointer files.

   Agent-specific folders should not duplicate full instructions. They should point to `docs/skills/global-project-rules/SKILL.md` and the relevant canonical skill files under `docs/skills/`.

   Typical project-scoped paths:

   | Tool | Path |
   |---|---|
   | OpenAI Codex | `.agents/skills/<skill-name>/SKILL.md` |
   | Claude Code | `.claude/skills/<skill-name>/SKILL.md` |
   | Cursor | `.cursor/rules/<rule-name>.mdc` |
   | Gemini CLI | `.gemini/skills/<skill-name>/SKILL.md` |
   | Antigravity | `.agent/skills/<skill-name>/SKILL.md` |

5. Clean up setup-only files.

   After selected skills are migrated into `docs/skills/`, remove starter directories and helper files that are no longer needed. The final project should not have competing sources of truth.

## Expected Final Pattern

The initialized project should end up with:

- A clear `docs/` directory that explains the project, structure, workflow, and active checklist.
- A mandatory `docs/skills/global-project-rules/SKILL.md` file that all agents are told to read.
- Canonical selected skills under `docs/skills/`.
- Minimal pointer files in `.agents/`, `.claude/`, `.cursor/`, `.gemini/`, or `.agent/`.
- Project code in the structure chosen during setup.
- Setup-only starter directories removed or explicitly documented as intentionally retained.

## Web Project Notes

For websites, dashboards, and web apps, always run `website-architecture` before UI generation. The architecture phase should decide the framework and optional libraries, such as Next.js, React/Vite, SvelteKit, Astro, Flask, Django, FastAPI, Tailwind, shadcn/ui, Radix UI, TanStack tools, React Hook Form, Zod, Framer Motion/Motion, GSAP, or another explicit stack.

The UI phase should also use `ui-frontend/ui/design-quality.md` so generated sites avoid generic AI-looking patterns, vague copy, fake metrics, decorative filler, and repeated card grids.

## Completion Standard

Initialization is not complete until the Definition of Done in `initialize.md` is satisfied. In particular, the agent must verify that:

- required intake questions are answered
- canonical docs exist
- selected skills exist under `docs/skills/`
- agent pointer files point to real docs
- cleanup happened
- validation commands were run or explicitly deferred
- remaining gaps are listed in `docs/checklist.md`
