# Repository Initialization & Skill Setup

Hello! I am your AI assistant. My goal is to help you initialize this repository and set up your agentic programming skills based on your project's needs. We will do this in 6 easy steps.
**Important:** We will **always** use `uv` as our package manager for Python environments.

## Step 1: Define Project Goals
**AI Agent Instruction:** Ask the user the following question: 
*"What is the primary goal and purpose of this current repository? What kind of features, tools, or systems are you building?"*
-> **Wait for the user's response before proceeding.**

## Step 2: Skill Discovery and Selection
**AI Agent Instruction:** 
1. Run `uv run read-yaml.py` to recursively scan and read the YAML frontmatter of all `SKILL.md` files in this repository.
2. Cross-reference the parsed skills with the user's goals provided in Step 1.
3. Propose a curated list of the skills/directories that will be most useful for their specific task.
-> **Wait for the user to confirm or modify the list before proceeding.**

## Step 3: Sub-directory Checklists (SETUP)
**AI Agent Instruction:**
For each of the selected sub-directories (e.g., `repo-structure`, `ui-frontend`), locate and read their contained `SETUP.md` files. Ask the user the questions detailed in those setup files to further define the requirements. (For example, if `repo-structure` is selected, ask whether they are using Flask, Django, Node, etc., and populate `repo-structure/web-interfaces/` accordingly).
-> **Wait for the user's response before proceeding.**

## Step 4: Environment Selection
**AI Agent Instruction:** Ask the user the following question:
*"Which IDEs or Agentic Programming software do you intend to use for this project? (Options covered: Claude Code, OpenAI Codex, Antigravity, Gemini CLI, Cursor)."*
-> **Wait for the user's response before proceeding.**

## Step 5: First-Time Setup
**AI Agent Instruction:** Using the approved skills from Step 2, the requirements from Step 3, and the requested environment(s) from Step 4, generate the appropriate directory structures and configuration files in this repository. Delete any unneeded sub-directories or structure files that were not selected for this project.

You **must** strictly adhere to the following rules for each respective software tool:

---

### Skill & Rule Formatting Guidelines

#### Directory Placement

| Tool | Project-Scoped Path | Global/User Path |
|---|---|---|
| **Claude Code** | `.claude/skills/<skill-name>/`  | `~/.claude/skills/<skill-name>/`  |
| **OpenAI Codex** | `.agents/skills/<skill-name>/`  | `~/.agents/skills/<skill-name>/`  |
| **Antigravity** | `.agent/skills/<skill-name>/`  | `~/.gemini/antigravity/skills/<skill-name>/`  |
| **Gemini CLI** | `.gemini/skills/<skill-name>/`  | `~/.gemini/skills/<skill-name>/`  |
| **Cursor** | `.cursor/rules/<rule-name>.mdc`  | `~/.cursor/rules/` (user-level)  |

***

#### Claude Code

Skills use a `SKILL.md` file with YAML frontmatter, and the body is loaded only when the skill activates. The YAML frontmatter requires exactly two fields:

```yaml
---
name: my-skill-name        # max 64 chars, lowercase + hyphens only
description: Use this skill when the user asks to... # semantic trigger
---
```

- `name`: Required. Lowercase, hyphens allowed, max 64 chars. Words "claude" or "anthropic" are reserved and forbidden.
- `description`: Required. This is what the model semantically matches against to decide if the skill is relevant.
- Optional subdirectories within the skill folder: `scripts/`, `references/`, `assets/`.

***

#### OpenAI Codex

Codex uses the same `SKILL.md` format and shares the open Agent Skills standard. Codex scans `.agents/skills` from your current working directory all the way up to the repo root, so multiple scopes can stack.

```yaml
---
name: skill-name
description: Explain exactly when this skill should and should not trigger.
---
```

An **optional** `agents/openai.yaml` file can be added inside the skill directory for richer UI metadata and behavior control:

```yaml
interface:
  display_name: "User-facing name"
  icon_small: "./assets/small-logo.svg"
  brand_color: "#3B82F6"
  default_prompt: "Optional default prompt"

policy:
  allow_implicit_invocation: false   # default: true

dependencies:
  tools:
    - type: "mcp"
      value: "someServer"
      transport: "streamable_http"
      url: "https://example.com/mcp"
```

***

#### Google Antigravity

Antigravity uses the same `SKILL.md` format, but with a subtle difference: `name` is **optional** and defaults to the directory name if omitted. The `description` is the critical field, as it's the only thing semantically indexed by the agent's router.

```yaml
---
name: database-inspector          # optional; defaults to folder name
description: Use this skill when the user asks to query the database,
             check table schemas, or inspect user data.
---
```

Optional subdirectories within the skill folder include `scripts/`, `references/`, `assets/`, `examples/`, and `resources/`. The workspace-scoped path is `.agent/skills/` (note: singular `.agent`, not `.agents`).

***

#### Gemini CLI

Gemini CLI is also built on the open Agent Skills standard, using `SKILL.md` with the same two required frontmatter fields. The `name` field should match the directory name for consistency.

```yaml
---
name: my-skill-name        # should match directory name
description: Description of what the skill does and when to use it.
---
```

Precedence ordering when multiple scopes define the same skill name is: **Workspace > User > Extension**. Optional subdirectories follow the same pattern: `scripts/`, `references/`, `assets/`.

***

#### Cursor

Cursor diverges significantly from the others — it uses **`.mdc` files** (not directories) stored flat in `.cursor/rules/`. There is no `SKILL.md` and no subdirectory per-rule. The frontmatter has three fields that control *when* the rule fires:

```yaml
---
description: Brief explanation of when the rule applies
globs: ["**/*.ts", "**/*.tsx"]   # file patterns for auto-attachment
alwaysApply: false               # if true, rule is injected into every prompt
---
```

- `description`: Required. Used by the AI to judge relevance when `alwaysApply` is false.
- `globs`: Optional array. Triggers the rule automatically when matched files are in context.
- `alwaysApply`: Optional boolean. When `true`, the rule is always prepended regardless of context.

The four activation modes — **Always**, **Auto-Attached** (globs), **Agent-Requested** (description-based), and **Manual** — are controlled entirely by how you set these three fields.

## Step 6: Finalization & Cleanup
**AI Agent Instruction:** 
1. Create a `doc/` directory with a file named `documentation.md`. This file should detail the full finalized tech stack, the general structure of the repository, and any other relevant architectural notes.
2. Delete files that are no longer needed post-setup. This includes: `initialize.md`, `read-yaml.py`, and the original `README.md`.
3. Inform the user that the setup is complete and the repository is ready for active development.
