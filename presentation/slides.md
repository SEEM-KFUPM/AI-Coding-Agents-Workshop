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
