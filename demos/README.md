# Workshop Demos

This folder contains participant-facing PDF decks with the demo projects for the AI Coding Agents Workshop. The demos show how to work with coding agents on scientific coding tasks while keeping the work reviewable, reproducible, and grounded in explicit assumptions.

These PDFs are exported teaching materials. They are meant to be read alongside the main workshop slides, setup notes, and agent guidance in the rest of the repository.

## Available Demo Decks

| File | Demo | Focus |
| --- | --- | --- |
| [demo1.pdf](demo1.pdf) | Legacy Figure Reproduction | Rebuild a scanned geophysics figure as a transparent, parameterized plotting project. |
| [demo2.pdf](demo2.pdf) | Paper Results Reproduction | Turn a published geoscience method into tested, documented research software. |

## Demo 1: Legacy Figure Reproduction

This demo starts from a historical scientific figure rather than from existing code. The goal is not to create a perfect pixel copy, but to make a reproducible geometric interpretation that another researcher can inspect, adjust, and improve.

Participants see how the task can be broken into small agent-guided iterations:

- describe the target figure and expected deliverables;
- generate an initial runnable plotting script;
- compare numbered image outputs against the target;
- revise geometry, camera angle, surfaces, grids, and shading through focused prompts;
- document assumptions and parameters instead of hiding them in one-off code.

## Demo 2: Paper Results Reproduction

This demo starts from a scientific paper and asks how to turn the method description into a small software project. The emphasis is on extracting equations, interfaces, validation checks, tests, examples, and documentation before trying to reproduce full paper-style outputs.

Participants see how agent work changes when the target is computational rather than visual:

- extract a software specification from a paper;
- define package structure and reproducibility files;
- implement a solver kernel in small pieces;
- validate equations with tests and simple analytical cases;
- add examples, plots, and documentation only after the core behavior is checkable.

## How To Use These Demos

1. Prepare your machine using [docs/setup/local-setup.md](../docs/setup/local-setup.md).
2. Keep [docs/agents/prompt-cheatsheet.md](../docs/agents/prompt-cheatsheet.md) nearby while watching or repeating the demos.
3. Use [docs/agents/validation-checklist.md](../docs/agents/validation-checklist.md) when reviewing generated code and results.
4. Follow the reproducibility practices in [docs/reproducibility/project-structure-guide.md](../docs/reproducibility/project-structure-guide.md), [docs/reproducibility/environment-management.md](../docs/reproducibility/environment-management.md), and [docs/reproducibility/git-workflow.md](../docs/reproducibility/git-workflow.md).
