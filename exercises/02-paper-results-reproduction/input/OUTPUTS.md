# Outputs

## Required

- A small Python package named `vti_raytrace`.
- Source code organized in `src/vti_raytrace/`.
- A project README with installation, quick start, assumptions, and known
  limitations.
- `pyproject.toml` and `environment.yml`.
- Tests for model handling, toy VTI equations, solver behavior, and analytical
  reference cases.
- An example script that runs the synthetic model from `DATA.md`.
- Generated outputs saved in `output/`:
  - one travel-time table
  - one direct-ray path figure
- Notes on how the toy implementation differs from the Jiang et al. paper.

## Expected Structure

```text
.
|-- README.md
|-- pyproject.toml
|-- environment.yml
|-- src/
|   `-- vti_raytrace/
|       |-- __init__.py
|       |-- model.py
|       |-- solver.py
|       |-- api.py
|       `-- plot.py
|-- examples/
|   `-- 01_synthetic_vti_direct.py
|-- tests/
|   |-- test_model.py
|   |-- test_solver.py
|   `-- test_examples.py
`-- output/
```

## Minimum Public API

The package should expose a small API suitable for examples and tests:

- a layered model class or function
- a function that solves direct rays for one source-receiver pair
- a function that computes travel time from a solved ray parameter
- a plotting helper for direct-ray paths

Names can differ if they are clear and documented.

## Required Validation

- Zero horizontal offset gives a vertical travel time equal to
  `sum(thickness / v_v)`.
- One homogeneous elliptical layer matches the analytical travel-time formula
  in `DATA.md`.
- With `epsilon = 0`, the equations reduce to the isotropic constant-velocity
  form.
- Offset increases monotonically with `q` over the valid interval.
- The final solved offset residual is small for each recommended receiver
  offset.

## Non-Goals

- Do not implement full qP/qSV/qSH Christoffel physics for the required
  exercise.
- Do not reproduce paper figures exactly.
- Do not start with Sphinx documentation, CI, release automation, or packaging
  polish beyond a minimal installable project.
- Do not commit paper PDFs or generated cache folders.

## Review Checklist

- Can another researcher see which pieces are paper-inspired and which are
  workshop simplifications?
- Are equations tested independently before they appear in examples?
- Are generated tables and figures saved in `output/`?
- Does the README avoid overclaiming scientific agreement with the paper?
- Is the package small enough that a participant can inspect every important
  line?
