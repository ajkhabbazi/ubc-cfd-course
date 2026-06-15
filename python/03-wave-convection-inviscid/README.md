# Wave convection in an inviscid medium

Numerical solution of the 1D inviscid Burgers' equation using three explicit finite-difference schemes, demonstrating shock formation and scheme-dependent diffusion and dispersion behaviour.

## Problem setup

| Parameter | Value |
|-----------|-------|
| Domain | 0 ≤ x ≤ 2π m |
| Boundary conditions | Periodic |
| Initial condition | u(x, 0) = sin(x) + 0.5 sin(0.5x) |
| Time step | Δt = 0.01 s |
| Courant number | ν = 0.5 |
| Maximum velocity (u_max) | 1.31 m/s |

## Governing equation

Inviscid Burgers' equation in conservation form:

```
∂u/∂t + ∂F/∂x = 0,   F = u²/2
```

## Numerical schemes

| Scheme | Order | Characteristics |
|--------|-------|-----------------|
| Lax | 1st (time & space) | Diffusive; stable but smears shocks |
| Lax-Wendroff | 2nd | Reduced diffusion; introduces oscillations near shocks |
| MacCormack | 2nd (predictor-corrector) | Better shock resolution than Lax-Wendroff |

## Tools

- **Language:** Python
- **Libraries:** NumPy, Matplotlib
- **Animation:** MP4 via Matplotlib animation

## Files

| File / Folder | Description |
|---------------|-------------|
| `main.py` | Solver with all three schemes and animation export |
| `animation.mp4` | Time evolution of the wave showing shock formation |
| `Figures/` | Snapshot comparisons between schemes at selected times |
| `Results/` | Additional output plots |
