---
marp: true
theme: default
paginate: true
style: |
  :root {
    --bg: #373938;
    --fg: #d9dae4;
    --accent: #dac961;
    --accent-soft: #008540;
    --panel: #003e51;
    --border: #aa8a00;
  }
  section {
    background: var(--bg);
    color: var(--fg);
    font-family: 'Segoe UI', system-ui, sans-serif;
    padding: 48px 64px;
    font-size: 25px;
  }
  h1, h2 { color: var(--accent); }
  h3 { color: var(--accent-soft); }
  code {
    background: #0b1220;
    color: #f8fafc;
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 2px 6px;
  }
  pre {
    background: #0b1220;
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
  }
  .columns {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
  }
  .card {
    border: 1px solid var(--border);
    background: rgba(17, 24, 39, 0.85);
    border-radius: 10px;
    padding: 18px;
  }
---

<!-- _class: lead -->

# AI Coding Agents Workshop

## From idea to reproducible mini-projects

Public workshop materials repository

---

# Why This Workshop?

- Move from ad hoc scripts toward reproducible project structure
- Treat Git as part of scientific quality control
- Learn how to collaborate with coding agents without over-trusting them
- Build habits that transfer to real research projects

---

# Core Workflow

1. Define the task and expected outputs
2. Break the project into small verifiable milestones
3. Use the agent for scoped implementation and review
4. Track progress with Git from the first step
5. Validate results, assumptions, and reproducibility

---

# Repository Layout

```text
presentation/
docs/
shared/demo-spec-template/
demos/
```

- `presentation/` contains the Marp deck
- `docs/` contains setup, workshop, and reproducibility guidance
- `demos/` contains the three public demo briefs

---

# Demo Tracks

## 1. Legacy figure reproduction
## 2. Published paper results reproduction
## 3. Geoscience web app with Gradio

Each demo starts from a clear brief, expected outputs, milestones, and reproducibility notes.

---

# Git as a Teaching Tool

<div class="columns">
<div class="card">

### Participants practice

- initializing repositories
- making small commits
- working in branches
- inspecting history

</div>
<div class="card">

### Why it matters

- traceability
- reviewability
- rollback
- clearer collaboration with agents

</div>
</div>

---

# Demo Brief Contract

Each public demo folder contains:

- `README.md`
- `TASK.md`
- `DATA.md`
- `OUTPUTS.md`
- `MILESTONES.md`
- `prompts.md`

The public repo describes the work clearly without exposing full instructor implementations.

---

# Why do we need `AGENTS.md`?

- Coding agents do not retain project context between sessions.
- For agents that support it, `AGENTS.md` helps ensure your project's instructions are loaded automatically.
- Use it as a lightweight README so agents can quickly understand your project.

---

# Where should `AGENTS.md` go?

- Global: `~/.codex/AGENTS.md` for personal defaults and safety constraints.
- Project: put `AGENTS.md` at the repository root for repo-wide context, structure, and conventions.
- Directory: add another `AGENTS.md` in a subfolder when one part of the project needs more specific instructions.
- Agents typically load instructions from the current directory upward toward the Git root.

---

# What's included in an `AGENTS.md`?

Common sections:

- Project overview and structure
- Build and test commands
- Helpful CLI tools and MCP servers
- Workflow for implementing a feature
- Pointers to other task-specific guidance for the agent

---

# Where do I get an `AGENTS.md` template?

- See [OpenAI cookbook for examples](https://github.com/openai/openai-cookbook)
- Good option - take the `CLAUDE.md` from [this repository](https://github.com/forrestchang/andrej-karpathy-skills/tree/main) and adapt it to your project's `AGENTS.md`
- Best practices are still emerging, so adapt templates to your needs and share improvements with the community

---

# Prompting Best Practices

- Point the agent to the relevant files, code, or error output.
- Ask for verification steps such as tests, linting, or manual checks.
- Start with small tasks, then build toward larger changes.
- Paste the full stack trace (e.g., all error messages) when debugging.
- Use `AGENTS.md` for persistent defaults and open-ended prompts for brainstorming.

---

# Starter Task Examples

- `Explain a codebase: summarize structure, key logic, and brittle areas.`
- `Fix a bug from a full stack trace: <paste error output>`
- `Expand test coverage for a feature/class/directory @<path>.`
- `Refactor repeated patterns across multiple files.`

---

# Participant Guides

- `docs/setup/` - machine and account preparation
- `docs/workshop/` - agenda, prompt hints, troubleshooting
- `docs/reproducibility/` - Git, environments, project layout

Use the repo as a map, not just a file dump.

---

# Extension Path

- Start with the guided common project
- Extend into paper reproduction or application building
- Reuse the same structure for your own research ideas

---

# Closing Principle

Write the project so another researcher can understand it, rerun it, and improve it later.

---

# References

- [OpenAI - Getting started with Codex](https://youtu.be/px7XlbYgk7I?si=HQJc3yuno-S9GhvZ)
