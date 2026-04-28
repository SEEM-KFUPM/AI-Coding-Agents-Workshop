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
    position: relative;
    place-content: start center;
  }
  section::before {
    content: "";
    position: absolute;
    left: 25px;
    bottom: 25px;
    width: 120px;
    height: 40px;
    background: url("./assets/logos/logo.svg") no-repeat left bottom / contain;
    pointer-events: none;
  }
  section.lead,
  section.topic {
    place-content: safe center center;
    text-align: center;
  }
  section.refs {
    font-size: 22px;
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

### Dr. Denis Anikiev (CIPR, KFUPM)

---

# Agenda

**First hour:**
- **Introduction**: why, what, and how
- **Git & GitHub**: version control, reproducibility and collaboration
- **VS Code**: the IDE we will use in the workshop
--- *Short Break* ---

**Second hour:**
- **Codex**: the coding agent we will use in the workshop
- **Reproducibility, Validation & Documentation**: environments, testing, documentation, reporting
- **Demo projects**: use cases
--- *Long Break* ---

Rest of the time: **Hands on session** - take an exercise, a demo project or design your own project

---

<!-- _class: topic -->

# Introduction

## Why, what, and how

---

# Why This Workshop?

- Coding agents are powerful tools that can accelerate research and development, but they require careful guidance
- Share best practices for working with coding agents in a way that promotes reproducibility and scientific rigor
- Build transferable skills for structuring projects, making them reproducible, and develop a good habit of verifying and documenting your work

---

# What You Will Learn

- Learn how to collaborate with coding agents without over-trusting them
- Move from ad hoc scripts toward reproducible project structure
- Treat Git as part of scientific quality control
- Build habits that transfer to real research projects and products

---

# How To Approach Projects with AI Coding Agents

## The Core Workflow

1. Define the task and expected outputs
2. Plan the project structure
3. Break the project into small verifiable milestones
4. Use the agent for scoped implementation and review
5. Track progress with Git from the first step
6. Validate results, assumptions, and reproducibility

---

# Workshop Requirements 

<div class="columns">
<div class="card">

## Essential

- A computer with internet access
- A GitHub account
- A KFUPM ChatGPT account (for Codex)
- Python installed
- Git installed
- VS Code installed
- Codex extension installed in VS Code

</div>
<div class="card">

## Recommended

- Basic programming experience
- Familiarity with running scripts or working in an IDE
- Basic understanding of data handling
- Basic knowledge of version control (Git)
- Prior exposure to working with notebooks or small coding projects

</div>
</div>

---

<!-- _class: topic -->

# Git & GitHub

## Version control to track progress, ensure reproducibility and share your work

---

# What is Git?

- [Git](https://git-scm.com/) is a distributed version control system: it tracks snapshots of your project over time
- It helps answer three key questions: what changed, who changed it, and why
- Commits act like named checkpoints you can inspect, compare, and restore
- Git works locally, so you do not need GitHub or even internet access to start using it
- For coding, research, and reports, Git turns trial-and-error into traceable and reproducible work

---

# Git as a Teaching Tool

<div class="columns">
<div class="card">

### You practice

- initializing repositories
- making small commits
- inspecting history
- working in branches if needed

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

# Git Basics

<div class="columns">
<div class="card">

### Core ideas

- repository = project + history
- working tree = your current files
- staging area = what will go into the next commit
- commit = a saved checkpoint with a message
- branch = a separate line of work

</div>
<div class="card">

### Everyday workflow

```bash
git status
git add <file>
git commit -m "Describe the change"
git log --oneline
```

Small, frequent commits make your work easier to review, debug, and reproduce.

</div>
</div>

---

# Connection with GitHub

<div class="columns">
<div class="card">

### Git vs GitHub

- Git = the version control tool on your machine
- GitHub = a web platform for hosting and sharing Git repositories
- You can use Git without GitHub, but GitHub makes collaboration much easier

</div>
<div class="card">

### Typical connection

```bash
git remote add origin <repo-url>
git push -u origin main
```

- publish your local history
- back it up online
- open the door to pull requests, issues, and collaboration

</div>
</div>

---

# Cloning a Repository from GitHub

- `git clone <url>` creates a full local copy of a remote repository
- You get the project files together with the commit history, branches, and tags
- This is the standard way to start from an existing project or workshop repository
- Cloning is better than downloading a ZIP because you can pull updates and contribute changes back

```bash
git clone https://github.com/SEEM-KFUPM/AI-Coding-Agents-Workshop.git
cd AI-Coding-Agents-Workshop
git status
```

---

# Creating a Repository on GitHub

1. Click `New repository` on GitHub
2. Choose a clear name and short description
3. Decide whether it should be `Public` or `Private`
4. Add a `README`, `.gitignore`, and license when appropriate
5. Create the repo, then clone it or connect your existing local project

- A GitHub repository becomes the shared home for code, documentation, tasks, and results
- Creating the repository early makes it easier to organize work, onboard collaborators, and keep agents aligned with the same source of truth

---

# Git & GitHub: Summary

- Git is a powerful tool for tracking changes, collaborating, and ensuring reproducibility in coding projects
- Using Git from the start of your project helps you maintain a clear history of your work
- GitHub provides a platform to share your repository, collaborate with others, and manage your project online

---

# Git & GitHub: Next Steps

- In the workshop, we will use Git and GitHub to document our progress, review changes, and share our work
- Clone [the workshop repository](https://github.com/SEEM-KFUPM/AI-Coding-Agents-Workshop) if you haven't already:
```bash
git clone https://github.com/SEEM-KFUPM/AI-Coding-Agents-Workshop.git
cd AI-Coding-Agents-Workshop
```
- Create your own repository for your version of demo projects and clone it
- You will use your repository to track your work on the demos, and you can share it with others for feedback and collaboration

---

# Breakout Session: Git & GitHub Practice

- Clone the workshop repository
- Create a new repository on GitHub for your work on the exercises
- Clone your new repository to your local machine
- Make a short `README.md` file with a title of your project and commit it
- Push your commit to GitHub

---

<!-- _class: topic -->

# About the workshop repository

## Overview of materials for the workshop

---

# Repository Layout

```text
presentation/
docs/
demos/
exercises/
template/
```

- `presentation/` contains this slide deck
- `docs/` contains setup, agents, and reproducibility guidance
- `demos/` contains the three public demo projects
- `exercises/` contains exercise projects
- `template/` contains a template for creating new project specifications

---

# Guidelines in `docs/`

- `docs/setup/` - machine and account preparation
- `docs/agents/` - prompt hints, validation, troubleshooting
- `docs/reproducibility/` - Git, environments, project layout

---

# Demo Projects in `demos/`

## 1. Legacy figure reproduction
## 2. Published paper results reproduction
## 3. Geoscience web app

Each demo starts from a clear brief, expected outputs, milestones, and reproducibility notes.

---

# Exercise Projects in `exercises/`

- Smaller, more focused tasks
- Already have inputs, expected outputs, and milestones defined
- Practice specific skills with coding agents in a hands-on session
- Designed to be completed in 15-30 minutes
- Cover the same range of use cases as the demos

---

# Demo/Exercise Structure

Each public demo folder contains:

- `input/`
  - `DATA.md` describes the project inputs
  - `TASK.md` describes the project task
  - `OUTPUTS.md` describes the expected outputs and evaluation criteria
  - `MILESTONES.md` describes the project milestones
- `prompts.md` contains example prompts for working with the coding agent on this project
- `README.md` describes the demo, its purpose, and what participants will practice

*Note:* `.md` files are [Markdown](https://www.markdownguide.org/) documents, text files with simple formatting that can be rendered nicely on GitHub and in VS Code.

---

<!-- _class: topic -->

# Visual Studio Code (VS Code)

## Remarks on the IDE (Integrated Development Environment) we will use

---

# Why VS Code?

- Free, open-source, and widely used across industries
- Built-in Git integration for version control
- Extensions for coding agents like Codex, GitHub Copilot, or  Claude Code, making it easy to get AI assistance directly in your editor
- Customizable interface and support for many programming languages
- Standard choice for many developers, making it easier to share tips and troubleshoot together

---

# Install & Explore VS Code

- Download and install VS Code from [the official website](https://code.visualstudio.com/download)
- Open VS Code and explore the interface: file explorer, terminal, extensions, and settings
- Explore Extensions panel on the left sidebar
- Open your cloned repository folder in VS Code
- Explore the Source Control panel to see the commit history and changes

---

# Breakout Session: VS Code Practice

- Open your cloned repository in VS Code
- Open Source Control panel to see the commit history and changes
- Modify a file (e.g., add a line to `README.md`), then use the Source Control panel to stage, commit, and push your change
- Open the terminal in VS Code and run a simple command, e.g.
```bash
echo "Hello, VS Code!"
```
- Save the workspace for your project to keep your settings and open files organized

---

<!-- _class: topic -->

# Break

## See you in 5 minutes for the next section

---

<!-- _class: topic -->

# Codex

## A coding agent by OpenAI to help you write, review, and understand code

---

# Why Codex?

- Codex is powered by the same technology as ChatGPT, but fine-tuned for coding tasks
- Codex has many capabilities apart from code generation that are useful for research
- KFUPM students, researchers and faculty have free access to Codex by OpenAI using KFUPM credentials
- We will use Codex in the workshop as an **IDE extension for VS Code**

---

# Alternative Coding Agents

- For VS Code: [GitHub Copilot](https://code.visualstudio.com/docs/copilot/overview), [Claude Code](https://marketplace.visualstudio.com/items?itemName=anthropic.claude-code), [Kilo Code](https://marketplace.visualstudio.com/items?itemName=kilocode.Kilo-Code), etc.
- [Antigravity](https://antigravity.google/) as an alternative to VS Code (same platform), uses Gemini for coding assistance
- Separate apps: [Cursor](https://cursor.com/), [Claude Code](https://claude.com/product/claude-code), [Codex App](https://openai.com/codex/)
- Alternatives are **outside** of the scope of this workshop
- Worth exploring for your projects and research

---

# Breakout Session: Try Codex in VS Code

- Install the [Codex Extension for VS Code by OpenAI](https://marketplace.visualstudio.com/items?itemName=openai.chatgpt)
- Open VS Code and sign in with your KFUPM credentials to access Codex
- Try a simple prompt, e.g.
  ```text
  Create a template README.md for a research project
  ```
  and see how Codex generates the file

---

<!-- _class: topic -->

# AGENTS.md

## Best practices for guiding coding agents in your project

---

# What is `AGENTS.md`

- `AGENTS.md` is a simple open format for guiding coding agents in a project.
- Think of it as a README for agents, with instructions on project structure, conventions, and helpful commands.
- Used by many open source projects

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
- Workflow for implementing a feature
- Pointers to other task-specific guidance for the agent
- Safety constraints and guardrails
- Environment setup instructions

---

# Where do I get an `AGENTS.md` template?

- Create your own using `/init` command directly in the prompt
- See [OpenAI cookbook for examples](https://github.com/openai/openai-cookbook)
- Good option - take the `CLAUDE.md` from [this repository](https://github.com/forrestchang/andrej-karpathy-skills/tree/main) and adapt it to your project's `AGENTS.md`
- Best practices are constantly emerging

---

# Prompting Best Practices

- Point the agent to the relevant files, code, or error output.
- Ask for verification steps such as tests, linting, or manual checks.
- Start with small tasks, then build toward larger changes.
- Paste the full stack trace (e.g., all error messages) when debugging.
- Use `AGENTS.md` for persistent defaults and open-ended prompts for brainstorming.

---

# Prompt Examples for Starting a New Project

- `Turn this idea into a small reproducible project: <describe the goal>. Propose a minimal folder structure and expected outputs.`
- `Break this project into 4 small milestones with clear deliverables, checks, and likely risks.`
- `Create the initial scaffold: README, AGENTS.md, src/, tests/, and the smallest runnable entry point. Keep it simple.`
- `Implement only milestone 1, explain assumptions, and tell me exactly how to verify it before we continue.`

---

# Prompt Examples for Existing Project

- `Explain a codebase: summarize structure, key logic, and brittle areas`
- `Fix a bug from a full stack trace: <paste error output>`
- `Expand test coverage for a feature/class/directory @<path>`
- `Refactor repeated patterns across multiple files`

---

# Write Documentation with Codex

Prompt:

```text
Create a simple HTML page called assets.html that shows how files in this project are related to each other. 
I want a nice looking page that explains those concepts.
```

---

# Useful Tips

- Use `/` to bring up the command menu and explore available commands for your agent
- You can point the agent to a file with `@<filename>` in your prompt
- Create comments with `# TODO` in your code to explain the purpose of a function or block you want to do, and ask the agent to write the implementation with "Implement with Codex" menu option
- Use screenshots as a context inside the prompts

---

# Review your Code with Codex

- Use `/review` command in the prompt to ask for a code review
- You can review against the base branch or uncommitted changes

---

# Breakout Session: set up `AGENTS.md` and try some prompts

- Create an `AGENTS.md` file in your project root with instructions for the agent
- Try some of the prompts we discussed to explore the workshop repository and understand the demo projects
- Try to use `@<filename>` to point the agent to a specific file and use context
- Explore the command menu with `/` and try the `/review` command

---

<!-- _class: topic -->

# Reproducibility, Validation & Documentation

## Best practices for making research projects reproducible, reliable and reusable

---

# General Principles

## Build your project in a way that another researcher can **understand** it, **rerun** it, and **improve** it later.

- Document your project structure, inputs, outputs, and assumptions clearly
- Document your changes
- Use version control (Git) to track changes and enable rollback
- Set up a reproducible environment
- Add tests and validation checks to verify your results

## A Good Question to Ask

If I revisit this in three months, will I understand how it works?

---

# Ten Habits for Reproducible Computational Research

<div class="columns">
<div>

1. Track how each result was produced
2. Replace manual data edits with scripted steps
3. Record exact external tool versions
4. Put custom scripts under version control
5. Save intermediate outputs in standard formats

</div>
<div>

6. Record random seeds when randomness is involved
7. Keep the data behind every plot
8. Organize outputs from summary to detail
9. Link claims to the results supporting them
10. Share scripts, runs, data, and results publicly

</div>
</div>

Sandve et al. (2013), adapted for project work with AI coding agents.

Sandve, G. K., Nekrutenko, A., Taylor, J., & Hovig, E. (2013). Ten simple rules for reproducible computational research. *PLoS Computational Biology*, 9(10), e1003285. <https://doi.org/10.1371/journal.pcbi.1003285>

---

<!-- _class: topic -->

# Coding Environments

## Setting up a reproducible environment for your project

---

# What is a Coding Environment?

- A coding environment is a self-contained directory that contains a specific version of a programming language and a set of installed packages
- It allows you to manage dependencies and avoid conflicts between different projects.
- Common tools for managing Python coding environments include `conda`, `venv`, and `pip`:
  - `conda` is a popular package and environment management system that works across platforms
  - `venv` is a built-in module for creating lightweight virtual environments
  - `pip` is the standard package installer for Python, often used in conjunction with `venv`
- In this workshop, we will focus on using `conda` for managing Python environments.

---

# Python Environments with `conda`

- `conda` is a popular package and environment management system that works across platforms.
- Get `conda` from [miniconda](https://www.anaconda.com/docs/getting-started/miniconda/main) or [miniforge](https://github.com/conda-forge/miniforge) (recommended) and install it
- To create a new environment:
```bash
conda create -n myenv python=3.10
```
- To activate the environment:
```bash
conda activate myenv
```
- To install packages, e.g.:
```bash
conda install numpy pandas matplotlib
```

---

# Environment Files for Reproducibility

- You can export your environment to a file that others can use to recreate the same environment
- For `conda`, use:
```bash
conda env export > environment.yml
```
- Others can then create the same environment with:
```bash
conda env create -f environment.yml
```
- You can create environment files manually or with the help of coding agents by asking them to generate an `environment.yml` based on the packages you have installed or the code you have written

---

# Advantages of Using Coding Environments

- **Reproducibility**: ensures that you and others can recreate the same environment with the same dependencies (including specific versions)
- **Isolation**: prevents conflicts between different projects that may require different versions of packages
- **Portability**: you can share your environment configuration (e.g., `environment.yml` for `conda`) with others to help them set up the same environment

---

<!-- _class: topic -->

# Validation & Testing

## Setting up tests to verify your code works as expected

---

# What Validation Means

Validation is not only "the code runs."

<div class="columns">
<div class="card">

### Scientific validation

- Are the inputs correct?
- Are units stated and consistent?
- Are assumptions explicit?
- Is the result physically plausible?
- Does it agree with a known case?

</div>
<div class="card">

### Software validation

- Does the code handle expected inputs?
- Are edge cases checked?
- Can the workflow be rerun?
- Are outputs saved in predictable locations?
- Can another person review the result?

</div>
</div>

---

# Why Testing Matters with Coding Agents

- Agents can produce convincing code that is still wrong
- Tests turn expectations into executable checks
- Tests let you safely refactor or extend code later
- Tests make collaboration easier because failures are specific
- Validation checks document what you decided to trust

**Rule of thumb:** ask the agent to help write tests, but ask yourself whether the tests check the real scientific claim.

---

# A Practical Testing Ladder

Start simple, then add confidence where the risk is highest.

1. **Smoke check**: can the script run from a clean environment?
2. **Unit test**: does one function give the expected answer for a small example?
3. **Regression test**: does a known input still produce the same output?
4. **Scientific check**: are units, ranges, trends, and limiting cases sensible?
5. **Reproducibility check**: can the full workflow be rerun from the README?

---

# Minimal Python Test Example

```python
# tests/test_stats.py
from src.stats import mean_value

def test_mean_value_for_simple_list():
    assert mean_value([1, 2, 3]) == 2
```

Run tests:

```bash
python -m pytest
```

- Keep tests small and readable
- Prefer simple known examples before complex real data
- Add one test when you fix a bug so it does not return silently

---

# Validation Checklist Before Trusting Outputs

<div class="columns">
<div class="card">

### Inputs and assumptions

- Input files are the intended ones
- Units are stated
- Missing values are handled
- Random seeds are recorded
- Important assumptions are written down

</div>
<div class="card">

### Outputs and workflow

- Expected files are created
- Figures and tables have source data
- Results are plausible
- Environment is documented
- README rerun steps work

</div>
</div>

---

# Ask Codex to Help Validate

Useful prompts:

```text
Read this code and list assumptions, edge cases, and validation checks.
```

```text
Add minimal pytest tests for the core calculation. Use simple known inputs.
```

```text
Review these outputs for reproducibility risks and missing documentation.
```

```text
Create a smoke-test command that verifies the main workflow runs end to end.
```

---

# Breakout Session: Add a Validation Check

- Choose one demo, exercise, or your own project
- Identify the most important output it produces
- Write down one expected property of that output
- Ask Codex to create a small test or smoke check
- Run it, inspect the result, and commit the validation change

Example commit message:

```bash
git commit -m "Add validation check for main output"
```

---

<!-- _class: topic -->

# Documentation & Project Structure

## Best practices for organizing your project and documenting it clearly

---

# Project Structure Is Communication

A good structure helps both humans and agents answer:

- Where are the original inputs?
- Where is the code that produces the outputs?
- Which files are generated and which are source material?
- How do I rerun the project from scratch?
- What should I check before trusting the results?

If the structure is clear, prompts become shorter and agent mistakes become easier to notice.

---

# Recommended Project Shape

```text
README.md
AGENTS.md
environment.yml
input/
src/
tests/
output/
docs/
```

- `input/` - original data, task description, and expected outputs
- `src/` - reusable code and runnable entry points
- `tests/` - small tests and smoke checks
- `output/` - generated figures, tables, reports, or app artifacts
- `docs/` - notes, methods, troubleshooting, and extra explanations

---

# Keep Inputs and Outputs Separate

<div class="columns">
<div class="card">

### Keep stable

- original data
- task statement
- evaluation criteria
- references
- environment files

</div>
<div class="card">

### Regenerate when possible

- cleaned data
- figures
- tables
- reports
- app build files

</div>
</div>

Never silently edit raw inputs. If cleaning is needed, write a script and document the decision.

---

# What a README Should Answer

- What problem does this project solve?
- What are the inputs and where did they come from?
- What outputs should be produced?
- How do I set up the environment?
- How do I run the workflow?
- How do I run tests or validation checks?
- What assumptions, limitations, or known issues should I know?

A README is not decoration. It is the shortest path from clone to understanding.

---

# Documentation Close to the Work

- Put data descriptions in `input/DATA.md`
- Put task goals in `input/TASK.md`
- Put expected outputs and evaluation criteria in `input/OUTPUTS.md`
- Put milestones and checkpoints in `input/MILESTONES.md`
- Put agent instructions in `AGENTS.md`
- Put usage instructions in `README.md`
- Put methods, notes, and decisions in `docs/`

This turns project context into files the agent can read and the team can review.

---

# Project Documentation with Codex

Useful prompts:

```text
Read this repository and summarize the project structure.
```

```text
Create a README section explaining how to rerun the project and run tests.
```

```text
Check whether the folder structure separates inputs, code, tests, and outputs.
```

```text
Update AGENTS.md with the build, test, and validation commands for this project.
```

---

# Breakout Session: Improve Project Structure

- Open a demo, exercise, or your own project
- Check whether it has `README.md`, `input/`, `src/`, `tests/`, and `output/`
- Add or improve one missing documentation file
- Ask Codex to review the structure for reproducibility risks
- Commit the change with a clear message

Example commit message:

```bash
git commit -m "Document project structure and validation steps"
```

---

# Summary

- Coding agents are useful collaborators, but project structure, clear prompts, and human verification still matter
- Git & GitHub turn project progress into traceable, reviewable, and shareable work
- VS Code provides the shared workspace for files, terminal commands, source control, and the Codex extension
- `AGENTS.md` keeps project instructions, commands, conventions, and guardrails available across agent sessions
- Reproducible Python environments make research projects easier to rerun on another machine
- A good project has clear inputs, expected outputs, milestones, documentation, and validation checks

---

<!-- _class: refs -->

# References

- Sandve et al. (2013), [Ten simple rules for reproducible computational research](https://doi.org/10.1371/journal.pcbi.1003285)
- [Pro Git book](https://git-scm.com/book/en/v2) and [Git reference documentation](https://git-scm.com/docs)
- [GitHub Docs: Repositories](https://docs.github.com/en/repositories/creating-and-managing-repositories)
- [VS Code documentation](https://code.visualstudio.com/docs)
- [OpenAI Codex documentation](https://developers.openai.com/codex/) and [Codex IDE extension](https://developers.openai.com/codex/ide)
- [OpenAI Cookbook: Codex prompting guide](https://developers.openai.com/cookbook/examples/gpt-5/codex_prompting_guide)
- [OpenAI - Getting started with Codex](https://youtu.be/px7XlbYgk7I?si=HQJc3yuno-S9GhvZ)
- [Finally! A Standard for AI Coding Agents (Agents.md Explained)](https://youtu.be/XDP94mYMCzA?si=f5a0E9nRkAqtBzFi)
- [AGENTS.md open format](https://agents.md/) and [OpenAI AGENTS.md guide](https://developers.openai.com/codex/guides/agents-md)
- [Conda documentation: Managing environments](https://docs.conda.io/projects/conda/en/stable/user-guide/tasks/manage-environments.html)
- [Conda specification: environment.yml](https://conda.org/learn/specifications/exchange/environment-yml)
- [Markdown Guide: Basic syntax](https://www.markdownguide.org/basic-syntax/)

---

# Next: Demo Projects

## Legacy figure reproduction
- Reproduce a legacy figure (e.g. a scan) to have more control over how it is generated, and to be able to modify it for future research

## Published paper results reproduction

- Reproduce the results of a published paper to verify them, understand the methods better, and build on top of them in future research

## Geoscience web app

- Build a simple web app for a geoscience use case to learn how to create interactive tools that can be shared with others and used for research or education
