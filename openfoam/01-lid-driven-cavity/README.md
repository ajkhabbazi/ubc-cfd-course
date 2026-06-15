# 2D lid-driven cavity flow

Transient laminar flow in a square cavity driven by a moving top wall, solved with OpenFOAM 9.

## Problem setup

| Parameter | Value |
|-----------|-------|
| Domain | 0.1 × 0.1 m square |
| Reynolds number | 100 (laminar) |
| Lid velocity | 1 m/s in x-direction |
| Kinematic viscosity | 0.001 m²/s |
| Bottom, left, right walls | No-slip (stationary) |
| Top wall | Moving lid |
| Analysis type | Transient |

## Solver

- **Solver:** icoFoam (laminar, incompressible, isothermal)
- **Mesh:** blockMesh
- **Platform:** Ubuntu / OpenFOAM 9

## Results

Velocity contours, streamlines, and pressure fields are captured at multiple time steps. The u-velocity profile along the vertical centreline is compared against the Ghia et al. benchmark for Re = 100.

## Files

| File / Folder | Description |
|---------------|-------------|
| `results.foam` | ParaView session file |
| `Figures/` | Velocity contours, streamlines, pressure contour, and centreline velocity profile |
| `2D-lid-driven-cavity-flow.PNG` | Domain schematic |
