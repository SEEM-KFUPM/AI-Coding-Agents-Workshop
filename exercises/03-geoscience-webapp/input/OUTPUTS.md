# Outputs

## Required

- A small Gradio app that can be launched locally.
- Source code separated into UI and reusable logic.
- A README with installation, launch command, app usage, assumptions, and known
  limitations.
- `pyproject.toml` and `environment.yml`.
- Tests for receiver parsing, geometry validation, toy mode selection, solver
  adapter behavior, and the app callback.
- A default example run using the model and geometry in `DATA.md`.
- A 2-D ray-path plot returned by the app.
- A travel-time table returned by the app.
- Notes on how the app differs from the Jiang et al. paper and from a full VTI
  wave-mode implementation.

## Expected Structure

One acceptable structure is:

```text
.
|-- README.md
|-- pyproject.toml
|-- environment.yml
|-- app.py
|-- src/
|   `-- vti_raytrace_app/
|       |-- __init__.py
|       |-- app_logic.py
|       |-- modes.py
|       |-- validation.py
|       `-- plotting.py
|-- tests/
|   |-- test_app_logic.py
|   |-- test_modes.py
|   `-- test_validation.py
`-- output/
```

If the Exercise 2 package is copied or vendored locally, document why. If it
is imported as a dependency, document the installation path or editable install
command.

## Minimum UI Contract

The app should provide:

- numeric input for source `x`
- numeric input for source `z`
- editable receiver input with at least `label`, `x_m`, and `z_m`
- wave-mode selector with qP, qSV, and qSH
- run button
- plot output
- table output
- concise validation or status message

The receiver editor may be a `gr.Dataframe` or a CSV-style text input. Choose
the option that keeps validation easiest to understand.

## Minimum Processing API

The non-UI code should expose functions similar to:

- `default_model()` or equivalent
- `mode_parameters(mode_name)`
- `parse_receivers(raw_receivers)`
- `validate_geometry(source, receivers, model)`
- `trace_receivers(source, receivers, mode, model)`
- `make_ray_plot(model, source, receivers, traced_rays)`

Names can differ if they are clear and documented.

## Required Validation

- Source depth is inside the model depth range.
- Receiver depths are inside the model depth range.
- Receiver rows with missing coordinates are rejected or ignored with a clear
  message.
- Wave mode must be one of qP, qSV, or qSH.
- The solver reports a small final offset residual for each traced receiver.
- If a ray cannot be solved, the app reports which receiver failed.

## Non-Goals

- Do not implement full Christoffel qP/qSV/qSH physics for the required app.
- Do not reproduce the paper figure exactly.
- Do not build a multi-page production dashboard.
- Do not add user accounts, databases, deployment pipelines, or cloud hosting
  unless everything required is already complete.
- Do not commit paper PDFs, copied figures, Gradio cache folders, or generated
  Python cache folders.

## Review Checklist

- Can a user tell which coordinates are horizontal distance and depth?
- Does the app still work with one receiver and with several receivers?
- Are qP, qSV, and qSH described as toy presets rather than validated physical
  wave modes?
- Are UI callbacks thin enough to test the underlying logic separately?
- Does the README explain how Exercise 2 code is reused?
- Are generated outputs either ignored or deliberately saved in `output/`?
