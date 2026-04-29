# Data

## Suggested Paper Reference

Jiang, X., Pan, X., Yang, H., Zhang, W., & Chen, X. (2024). A fast and
robust two-point ray tracing method in layered vertical transversely isotropic
media with strong anisotropy. *Geophysical Prospecting*, 73(3), 861-873.
https://doi.org/10.1111/1365-2478.13585

## Relation to Exercises 1 and 2

Exercise 1 used the paper's Figure 1 as a target for understanding a layered
VTI ray-path plot. Exercise 2 turned a simplified version of the paper's
direct-ray idea into a tiny Python package.

Exercise 3 should reuse that Exercise 2 software shape and add an interactive
Gradio interface. The app should help a participant change geometry and wave
mode, then immediately inspect the resulting 2-D ray plot.

## Public Paper Context

The paper develops a fast two-point ray tracing method for layered VTI media
with strong anisotropy. It treats direct and reflected quasi-P, quasi-SV, and
quasi-SH waves using a generalized ray parameter and Christoffel-based
slowness equations.

This workshop app is much smaller. It uses toy elliptical mode presets so the
UI can expose qP, qSV, and qSH choices without claiming to reproduce the full
paper method.

## Synthetic Layered Model

Use this public-safe synthetic model for the app defaults. Depth is positive
downward.

| Layer | Top depth (m) | Bottom depth (m) | qP `v_v` (m/s) | qP `epsilon` | qSV `v_v` (m/s) | qSV `epsilon_like` | qSH `v_v` (m/s) | qSH `gamma_like` |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| 1 | 0 | 800 | 2200 | 0.10 | 1250 | 0.04 | 1300 | 0.06 |
| 2 | 800 | 1800 | 2800 | 0.20 | 1550 | 0.08 | 1650 | 0.10 |
| 3 | 1800 | 3000 | 3600 | 0.35 | 2000 | 0.12 | 2150 | 0.15 |

For qP, use `epsilon` exactly as in Exercise 2. For qSV and qSH, the
`epsilon_like` and `gamma_like` values are app-training parameters only. They
let the same elliptical solver produce distinct S-mode-looking rays.

## Default Geometry

Recommended app defaults:

| Quantity | Value |
| --- | ---: |
| Source horizontal position `x` | 0 m |
| Source depth `z` | 100 m |
| Default receiver depth `z` | 2600 m |

Default receiver table:

| label | x_m | z_m |
| --- | ---: | ---: |
| R0 | 0 | 2600 |
| R1 | 500 | 2600 |
| R2 | 1000 | 2600 |
| R3 | 2000 | 2600 |
| R4 | 3000 | 2600 |

The app should allow users to add, remove, or edit receiver rows. Empty rows
may be ignored if the app reports how many valid receivers were traced.

## Toy Mode Equations

Reuse the Exercise 2 toy direct-ray equations. For a selected mode, each layer
has a vertical velocity `v_v` and an anisotropy-like factor `a`.

Horizontal velocity:

```text
v_h = v_v * sqrt(1 + 2 * a)
```

Mode mapping:

```text
qP:  v_v = qP v_v,  a = qP epsilon
qSV: v_v = qSV v_v, a = qSV epsilon_like
qSH: v_v = qSH v_v, a = qSH gamma_like
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
sum_i x_i(q) = abs(receiver_x - source_x)
```

After solving for `q`, reconstruct a 2-D ray path by accumulating per-layer
horizontal offsets from the source `x` toward the receiver `x`.

## Expected Plot Content

The ray plot should include:

- horizontal layer boundaries at 800 m, 1800 m, and 3000 m
- source marker
- receiver markers
- one direct ray per valid receiver for the selected mode
- a legend or labels that make receiver and mode visible
- horizontal distance on the x-axis and depth on the z-axis
- depth axis increasing downward

The plot should be inspired by the Figure 1 discussion from Exercise 1, but it
does not need to match the paper figure exactly.

## Provenance and Licensing Notes

- The synthetic model and toy S-mode parameters are invented for the workshop
  and are safe to commit.
- The paper citation and public method summary are safe to include.
- Do not commit the article PDF, full paper text, or copied figures unless
  licensing has been checked separately.
