# Prompt Suggestions

## Planning

`Read the files in input/. Propose the smallest Gradio app that satisfies TASK.md and OUTPUTS.md. Separate UI work from reusable ray-tracing logic.`

## Reuse Exercise 2

`Inspect the Exercise 2 package or scaffold. Decide which functions can be imported for layered VTI ray tracing and which thin adapter functions the app needs. Do not rewrite the solver unless it is missing.`

## App Contract

`Before coding the UI, write a short app contract: required inputs, validation rules, outputs, and how qP, qSV, and qSH toy modes map to the solver parameters in input/DATA.md.`

## First Gradio UI

`Create the minimal Gradio Blocks app with source x/z inputs, an editable receiver table, a wave-mode selector, a run button, one ray-path plot, and one travel-time table. Keep processing logic outside the UI callback where possible.`

## Solver Integration

`Connect the UI to the Exercise 2 ray-tracing framework. Use the default model and receiver geometry from input/DATA.md. Add validation for invalid depths, empty receiver rows, bad mode names, and failed solver residuals.`

## Multi-Receiver Plot

`Improve the app so multiple receivers can be traced in one run. Plot the layered model, source, receivers, and all direct rays with readable labels. Return a table with receiver label, mode, offset, q value, travel time, and residual.`

## Review

`Review the app for usability, scientific overclaims, missing validation, weak tests, and generated files that should not be committed. Make focused cleanup changes only.`
