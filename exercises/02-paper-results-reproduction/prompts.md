# Prompt Suggestions

## Planning

`Read the files in input/. Propose the smallest package design that satisfies TASK.md and OUTPUTS.md. Separate paper-derived ideas from workshop simplifications.`

## Specification

`Before coding, write a short implementation brief for the toy VTI direct-ray solver. Include equations, assumptions, expected modules, and tests.`

## Package Scaffold

`Create the minimal package scaffold described in input/OUTPUTS.md. Add pyproject.toml, src/vti_raytrace/, tests/, examples/, output/, and a README. Do not implement the solver yet.`

## First Solver

`Implement only the model representation and direct-ray offset/travel-time equations from input/DATA.md. Add tests for vertical rays, the isotropic limit, and monotonic offset with q.`

## Example Output

`Add an example that uses the synthetic model in input/DATA.md, saves a travel-time table, and plots direct ray paths for several offsets.`

## Review

`Review the package for scientific overclaims, missing tests, unclear assumptions, and generated files that should not be committed. Make focused cleanup changes only.`
