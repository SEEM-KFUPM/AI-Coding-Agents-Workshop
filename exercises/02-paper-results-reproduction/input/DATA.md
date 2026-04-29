# Data

## Suggested Paper Reference

Jiang, X., Pan, X., Yang, H., Zhang, W., & Chen, X. (2024). A fast and
robust two-point ray tracing method in layered vertical transversely isotropic
media with strong anisotropy. *Geophysical Prospecting*, 73(3), 861-873.
https://doi.org/10.1111/1365-2478.13585

## Public Paper Context

The paper develops a fast two-point ray tracing method for layered VTI media
with strong anisotropy. It uses the Christoffel slowness equation and a
generalized dimensionless ray parameter to compute ray paths and travel times
for direct and reflected quasi-P, quasi-SV, and quasi-SH waves. The published
method uses Newton optimization, analytical derivatives, and initial-value
rules designed to remain stable at large offsets and in strongly anisotropic
models.

For this workshop exercise, use the paper as motivation only. The coding target below is intentionally much smaller.

## Local Paper File

A copy of the paper PDF may be placed in this `input/` folder for local reading.
Repository rules should keep PDFs untracked (for license and size reasons).

So do not commit the PDF. Use this file as the public, commit-safe description of the target instead.

## Exercise Simplification

Implement a toy direct qP-style solver using an elliptical VTI approximation.
This is not the full Jiang et al. method. It preserves the main software shape:

- a layered VTI model
- a normalized dimensionless ray parameter
- a nonlinear offset equation
- travel-time and path reconstruction after solving the parameter
- tests that separate mathematical behavior from plotting

The full Christoffel-equation formulation, qSV/qSH waves, reflections,
triplications, and exact paper examples are out of scope for the required
exercise.

## Synthetic Layered Model

Use this small synthetic model for the required example. Depth is positive
downward.

| Layer | Top depth (m) | Bottom depth (m) | Vertical qP velocity `v_v` (m/s) | `epsilon` | Horizontal velocity `v_h` (m/s) |
| --- | ---: | ---: | ---: | ---: | ---: |
| 1 | 0 | 800 | 2200 | 0.10 | 2410.0 |
| 2 | 800 | 1800 | 2800 | 0.20 | 3313.3 |
| 3 | 1800 | 3000 | 3600 | 0.35 | 4696.8 |

Recommended source and receiver geometry:

| Quantity | Value |
| --- | ---: |
| Source horizontal position | 0 m |
| Source depth | 100 m |
| Receiver depth | 2600 m |
| Receiver offsets | 0, 500, 1000, 2000, 3000 m |

The traversed vertical thicknesses for this geometry are 700 m in layer 1,
1000 m in layer 2, and 800 m in layer 3.

## Toy Equations

Use the following simplified equations unless you decide to implement a better
documented approximation.

Horizontal velocity:

```text
v_h = v_v * sqrt(1 + 2 * epsilon)
```

Let `p` be horizontal slowness and choose:

```text
v_ref = max(v_h across traversed layers)
q = p * v_ref
p = q / v_ref
0 <= q < 1
```

For a traversed thickness `h_i` in layer `i`:

```text
x_i(q) = h_i * p * v_h_i^2 / (v_v_i * sqrt(1 - (p * v_h_i)^2))
t_i(q) = h_i / (v_v_i * sqrt(1 - (p * v_h_i)^2))
```

The direct-ray offset equation is:

```text
sum_i x_i(q) = target_offset
```

After solving for `q`, reconstruct a 2-D ray path by accumulating the
per-layer horizontal offsets `x_i` and the layer-boundary depths.

## Sanity Values

These values are approximate checks for the model and geometry above. They are
useful for tests, but exact tolerances should account for numerical precision.

| Target offset (m) | Approx. `q` | Approx. travel time (s) |
| ---: | ---: | ---: |
| 0 | 0.0000 | 0.89755 |
| 500 | 0.2165 | 0.90917 |
| 1000 | 0.4130 | 0.94295 |
| 2000 | 0.7021 | 1.06439 |
| 3000 | 0.8561 | 1.23238 |

## Provenance and Licensing Notes

- The synthetic model is invented for the workshop and is safe to commit.
- The paper citation and public abstract-level method description are safe to
  include.
- Do not commit the article PDF, full paper text, or copied figures unless
  licensing has been checked separately.
