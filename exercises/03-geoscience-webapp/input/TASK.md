# Task

Build a small Gradio web app for interactive 2-D direct-ray plotting in
layered vertical transversely isotropic (VTI) media.

The app should build on the Exercise 2 VTI ray-tracing framework where
possible. The goal is not to implement the full Jiang et al. paper. The goal is
to wrap a small, tested solver in an interface that lets users explore the
paper-style geometry interactively.

## Scientific Target

Create an app that plots direct rays through a 1-D layered VTI model in a
2-D vertical section.

The first-pass app should support:

- numeric inputs for source horizontal position `x` and depth `z`
- an editable receiver table with many receiver positions
- receiver columns for horizontal position `x` and depth `z`
- selection of one toy wave mode: qP, qSV, or qSH
- ray tracing for every valid source-receiver pair in the table
- a 2-D plot showing layer boundaries, the source, receivers, and direct rays
- a table of travel times, solved ray parameters, offsets, and residuals
- clear validation messages for invalid geometry or unsupported solver cases

The 2-D section uses `x` for horizontal distance and `z` for positive-down
depth. If an early UI sketch uses `y` for the receiver vertical coordinate,
treat it as depth and relabel it to `z` before finalizing the app.

## Technical Approach

- Use `DATA.md` as the source of the synthetic layered model, default
  geometry, and toy wave-mode parameters.
- Prefer importing the package created in Exercise 2, for example
  `vti_raytrace`, instead of rewriting the solver.
- If the Exercise 2 package is unavailable, create a small app-local solver
  using the same toy equations from Exercise 2 and document that fallback.
- Use Gradio for the app UI.
- Keep Gradio event callbacks thin. Put parsing, validation, mode selection,
  solver calls, and plotting in reusable Python functions.
- Prefer a simple editable `gr.Dataframe` for receivers. A pasted CSV text box
  is acceptable if it is easier to validate robustly.
- Use Matplotlib or another lightweight plotting library already used by the
  Exercise 2 solution.

## Success Criteria

- Running the app locally opens a Gradio interface.
- The default inputs from `DATA.md` produce a paper-style 2-D ray plot with
  multiple receiver rays.
- The user can change source `x`, source `z`, receiver rows, and wave mode
  without editing code.
- The app returns an interpretable travel-time table.
- qP, qSV, and qSH are available as toy mode presets, with documentation that
  they are simplified elliptical approximations rather than full Christoffel
  wave physics.
- Invalid inputs produce clear errors instead of tracebacks.
- Core non-UI functions are covered by small tests.
- The README explains how to install, run, test, and interpret the app.

## Scope Notes

- First pass: direct rays only, 1-D layered model, toy elliptical mode
  presets, one app screen, one ray plot, and one results table.
- Good stretch goals: multi-mode overlay, downloadable CSV results, an
  editable layer table, a screenshot in `output/`, or app deployment notes.
- Out of scope: full qP/qSV/qSH Christoffel equations, reflected rays,
  triplications, 3-D geometry, exact reproduction of paper figures, cloud
  deployment, and authentication.
- Do not commit paper PDFs, copied paper figures, Gradio cache folders, or
  generated temporary files.
