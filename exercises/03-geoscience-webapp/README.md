# Exercise 3: Interactive VTI Ray-Tracing Web App

This exercise is the third guided exercise for the workshop.

## Purpose

Participants turn the VTI ray-tracing mini-package from Exercise 2 into a
small Gradio web app. The app should let a user edit source and receiver
geometry, choose a wave mode, and plot 2-D ray paths through a layered VTI
model in the spirit of the Figure 1 reproduction task from Exercise 1.

## What Participants Practice

- wrapping scientific code in a lightweight interactive interface
- separating Gradio UI code from reusable ray-tracing logic
- validating user-provided geometry before running a solver
- presenting ray paths and travel-time tables clearly
- documenting where the app is paper-inspired and where it is simplified

## Starting Point

Use the files in `input/`:

- `TASK.md` defines the Gradio app task and success criteria
- `DATA.md` gives the synthetic layered VTI model, default geometry, and toy
  wave-mode parameters
- `OUTPUTS.md` defines the expected app structure and deliverables
- `MILESTONES.md` suggests an implementation sequence and Git checkpoints
