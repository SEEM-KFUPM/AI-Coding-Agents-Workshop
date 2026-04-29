# Milestones

1. Read `TASK.md`, `DATA.md`, and `OUTPUTS.md`; summarize the app workflow,
   scientific simplifications, and expected outputs.
2. Inspect the Exercise 2 `vti_raytrace` package or scaffold and identify the
   solver functions that can be reused.
3. Create the app project skeleton with `pyproject.toml`, `requirements.txt`
   or `environment.yml`, `app.py`, `src/`, `tests/`, and `output/`.
4. Add synthetic model and toy qP/qSV/qSH mode presets from `DATA.md`.
5. Implement receiver parsing and validation for source depth, receiver
   depths, required columns, and allowed wave modes.
6. Add a solver adapter that traces one source-receiver pair using the
   Exercise 2 framework or the documented fallback equations.
7. Extend the adapter to trace all valid receivers and return a tidy results
   table with label, mode, offset, `q`, travel time, and residual.
8. Add a plotting helper that draws layer boundaries, the source, receivers,
   and all traced rays in a depth-positive-down 2-D section.
9. Build the first Gradio interface with source controls, receiver editor,
   wave-mode selector, run button, plot output, table output, and status text.
10. Add tests for mode selection, receiver parsing, validation failures,
    solver adapter residuals, and the Gradio callback function.
11. Run the app locally with the default geometry and capture any manual
    validation notes in the README.
12. Review scientific wording, generated files, and Git status before the
    final commit.

## Iteration Rules

- Keep each agent prompt focused on one conceptual improvement.
- Prefer validating parsing and solver logic before polishing the interface.
- When the app makes a scientific simplification, document it in the README
  and keep the UI wording modest.
- Do not silently drop invalid receiver rows unless the status message says
  exactly what happened.
- Keep `input/` unchanged after the exercise begins.

## Suggested Participant Commits

- `Initialize Gradio VTI ray app scaffold`
- `Add toy VTI modes and receiver validation`
- `Connect Exercise 2 solver to app logic`
- `Build multi-receiver ray plot UI`
- `Add tests and document app assumptions`
