# Turbulent flow over a backward-facing step

Turbulent boundary-layer separation and reattachment over a backward-facing step at Re = 25 400, comparing four RANS turbulence models against the Pitz & Daily (1981) experimental benchmark.

## Problem setup

| Parameter | Value |
|-----------|-------|
| Step height | h = 25.4 mm |
| Inlet duct height | h |
| Step duct height | 2h, length 8.11h |
| Inlet velocity (U₀) | 10 m/s (uniform) |
| Outlet static pressure | 10 Pa gauge |
| Reynolds number | 25 400 |
| Fluid density | 1 kg/m³ |
| Flow | Unsteady, Newtonian, incompressible |
| Turbulence model | RANS |

## Turbulence models

| Sub-folder | Model | Type |
|------------|-------|------|
| `SA/` | Spalart-Allmaras | One-equation eddy viscosity |
| `ke/` | k-ε | Two-equation |
| `ko/` | k-ω | Two-equation, improved near-wall behaviour |
| `SST/` | k-ω SST | Blends k-ω (near wall) and k-ε (far field) |

**Inlet turbulence boundary conditions:**

| Quantity | Expression | Value |
|----------|------------|-------|
| Turbulence intensity | I = 0.05 U₀ | — |
| Length scale | l = 0.055h | — |
| Turbulent kinetic energy | k = (3/2)(UI)² | 0.375 m²/s² |
| Dissipation rate | ε ≈ Cμ k^(3/2) / l, Cμ = 0.09 | 14.855 m²/s³ |
| Specific dissipation | ω = √k / l | 440.15 s⁻¹ |

## Solver

- **Solver:** simpleFoam (steady-state RANS)
- **Mesh:** blockMesh
- **Platform:** Ubuntu / OpenFOAM 9

## Reference

R. Pitz and J. Daily, "Experimental study of combustion in a turbulent free shear layer formed at a rearward facing step," *19th Aerospace Sciences Meeting*, 1981. doi: [10.2514/6.1981-106](https://doi.org/10.2514/6.1981-106)

## Files

| File / Folder | Description |
|---------------|-------------|
| `SA/`, `ke/`, `ko/`, `SST/` | ParaView session files for each turbulence model |
| `Figures/` | Velocity profiles and reattachment length comparisons across all four models |
| `main.py` | Python post-processing script |
| `Backwards-facing-step.PNG` | Domain schematic |
