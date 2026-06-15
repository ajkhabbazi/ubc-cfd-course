# Supersonic flow over a forward-facing step

Supersonic inviscid flow over a forward-facing step at inlet Mach 3, capturing shock formation and wave structure with OpenFOAM's rhoCentralFoam solver.

## Problem setup

| Parameter | Value |
|-----------|-------|
| Inlet Mach number | 3 |
| Inlet velocity | 3 m/s |
| Speed of sound | 1 m/s |
| Inlet static pressure | 1 Pa |
| Outlet BC | Zero-gradient |
| Total temperature | 1 K (constant — adiabatic, inviscid walls) |

Fluid properties use a fictitious gas chosen so that the speed of sound equals 1 m/s, making Mach number numerically equal to velocity in m/s:

| Property | Value |
|----------|-------|
| Molar mass (M) | 11 640.3 kg/kmol |
| Specific heat (cₚ) | 2.5 J/kg·K |
| Dynamic viscosity (μ) | 0 (inviscid) |
| Specific heat ratio (γ) | 1.4 |
| Prandtl number (Pr) | 1 |

## Solver

- **Solver:** rhoCentralFoam
- **Mesh:** blockMesh
- **Platform:** Ubuntu / OpenFOAM 9

## Results

A detached bow shock forms upstream of the step. Mach number and pressure contours at steady state show the shock structure and post-shock subsonic region.

## Files

| File / Folder | Description |
|---------------|-------------|
| `result.foam` | ParaView session file |
| `Figures/` | Mach number and pressure contour plots |
| `Forward-step.PNG` | Domain schematic |
