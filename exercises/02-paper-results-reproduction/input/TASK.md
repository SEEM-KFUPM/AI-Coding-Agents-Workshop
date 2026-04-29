# Task

Build a very small Python package inspired by the Jiang et al. VTI
two-point ray tracing paper.

The aim is not to implement the full paper. The aim is to practice how an AI
coding agent can help translate a scientific method into a scoped, tested,
reviewable research-software artifact.

## Scientific Target

Implement a simplified direct-ray solver for 1-D layered vertical
transversely isotropic (VTI) media.

The first-pass package should support:

- defining a layered VTI model with layer thickness, vertical qP velocity, and
  Thomsen-style `epsilon`
- computing horizontal velocity with a simple elliptical approximation
- using a dimensionless normalized horizontal slowness parameter `q`
- solving the two-point direct-ray offset equation for a source and receiver
- computing travel time, per-layer horizontal offsets, and a 2-D ray path
- plotting direct ray paths over the layered model
- running a small synthetic paper-style example from `DATA.md`

## Technical Approach

- Use `DATA.md` as the source of paper context, model values, and toy
  equations.
- Use `OUTPUTS.md` for the expected package structure and deliverables.
- Use `MILESTONES.md` as the implementation sequence.
- Build a package named `vti_raytrace`.
- Prefer small, testable modules over one long script.
- Write tests before expanding examples or plotting.
- Keep assumptions and deviations from the paper explicit in the README.

## Success Criteria

- The package can trace direct rays and compute travel times for the synthetic
  layered VTI model in `DATA.md`.
- Analytical checks pass for zero-offset vertical rays, one-layer homogeneous
  elliptical media, and the isotropic limit.
- The normalized `q` solver is tested for valid range, monotonic offset, and
  small final residual.
- At least one example saves a table and a plot in `output/`.
- The README explains installation, usage, tests, assumptions, and known
  limitations.
- The implementation is derived from the exercise documents and paper
  description, not from an existing ray-tracing codebase.

## Scope Notes

- First pass: direct qP-style rays, 1-D layered VTI model, elliptical
  approximation, tests, one example, and one plot.
- Stretch: Newton iteration with bisection fallback, reflected rays, comparison
  with an isotropic model, or a second synthetic model.
- Out of scope: full Christoffel slowness equations, qSV/qSH waves, triplication
  handling, Monte Carlo validation, exact reproduction of paper figures, release
  automation, and documentation websites.
- A local paper PDF may be used for reading if available, but it must remain
  untracked and must not be committed.
