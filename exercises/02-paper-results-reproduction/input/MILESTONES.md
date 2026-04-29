# Milestones

1. Inspect the paper context in `DATA.md` and write a short implementation
   brief from the simplified method.
2. Create the package skeleton with `pyproject.toml`, `environment.yml` or
   `requirements.txt`, `src/vti_raytrace/`, `examples/`, `tests/`, and
   `output/`.
3. Implement the layered VTI model representation, including extraction of
   traversed layer thicknesses between source and receiver depths.
4. Implement the toy equations: `epsilon -> v_h`, `q <-> p`, per-layer offset,
   per-layer travel time, and total offset.
5. Implement the direct two-point solver for a target horizontal offset using
   bisection or Newton iteration with a robust fallback.
6. Add tests for vertical rays, homogeneous elliptical media, the isotropic
   limit, `q` range handling, offset monotonicity, and solver residuals.
7. Add ray path reconstruction from per-layer horizontal offsets.
8. Add a plotting helper for 2-D direct ray paths over the layered VTI model.
9. Create `examples/01_synthetic_vti_direct.py` to run the model in `DATA.md`,
   save a travel-time table, and save the first figure in `output/`.
10. Refactor names, public API exports, and README instructions so another
    researcher can understand and run the package.
11. Record assumptions, limitations, and differences from Jiang et al. in the
    README.

## Iteration Rules

- Keep each agent prompt focused on one conceptual improvement.
- Prefer validating equations with small analytical cases before attempting
  plots.
- When the agent makes a scientific assumption, ask it to document the
  assumption and add or update a test.
- Do not overwrite generated figures silently; use clear names or numbering.
- Keep `input/` unchanged after the exercise begins.

## Suggested Participant Commits

- `Initialize VTI raytrace package scaffold`
- `Implement layered model and toy q equations`
- `Add direct solver and analytical tests`
- `Add synthetic VTI example outputs`
- `Document assumptions and finalize exercise`
