# Flow over NACA 5012 airfoil

Subsonic laminar flow over a NACA 5012 airfoil at Re = 100 and Re = 1000, including a mesh refinement study and comparison of pressure distributions between the two Reynolds numbers.

## Problem setup

| Parameter | Value |
|-----------|-------|
| Airfoil | NACA 5012 |
| Reynolds numbers | 100, 1000 |
| Free-stream velocity | 1 m/s (zero angle of attack) |
| Chord length | c = 1 m |
| Fluid properties | Constant; initial gauge pressure = 0 Pa |
| Flow | Laminar, incompressible |
| Simulation time | 20 s per case |

Reynolds number is varied by adjusting kinematic viscosity: ν = Uc/Re.

## Solver

- **Solver:** icoFoam (laminar, incompressible)
- **Mesh generation:** GMSH, converted with `gmshToFoam`
- **Post-processing:** ParaView; plots generated with Python
- **Platform:** Ubuntu / OpenFOAM 9

## Results

A mesh refinement study confirms grid independence. Surface pressure distributions and wake structures are compared between Re = 100 and Re = 1000, showing stronger adverse pressure gradients and earlier separation at the higher Reynolds number.

## Files

| File / Folder | Description |
|---------------|-------------|
| `Re100/` | ParaView session for Re = 100 |
| `Re1000/` | ParaView session for Re = 1000 |
| `Figures/` | Pressure contours, surface pressure distributions, and Re comparison plots |
| `main.py` | Python post-processing and plotting script |
| `Flow-across-NACA5012.PNG` | Domain and airfoil schematic |
