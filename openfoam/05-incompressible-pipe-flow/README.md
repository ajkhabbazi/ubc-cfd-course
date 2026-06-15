# Incompressible pipe flow

Laminar, incompressible flow in a circular pipe at Re = 200, validated against the analytical Hagen-Poiseuille velocity profile.

## Problem setup

| Parameter | Value |
|-----------|-------|
| Pipe radius | 1 m |
| Pipe length | 25 m (25R) |
| Inlet velocity | 0.1 m/s (uniform) |
| Outlet BC | Zero gauge static pressure |
| Wall BC | No-slip |
| Kinematic viscosity | 0.001 m²/s |
| Reynolds number | 200 (laminar) |

## Solver

- **Solver:** icoFoam (laminar, incompressible)
- **Mesh:** blockMesh
- **Post-processing:** ParaView; velocity profile plots generated with Python
- **Platform:** Ubuntu / OpenFOAM 9

## Results

The simulated outlet velocity profile matches the analytical Hagen-Poiseuille parabolic solution, confirming that fully-developed flow is established within the 25R pipe length.

## Files

| File / Folder | Description |
|---------------|-------------|
| `results.foam` | ParaView session file |
| `Results/` | Velocity profile and convergence plots |
| `main.py` | Python post-processing and validation script |
