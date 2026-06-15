# Converging-diverging nozzle

Steady compressible flow through an axisymmetric converging-diverging nozzle at three back-pressure ratios, producing subsonic, normal-shock, and fully supersonic flow regimes.

## Problem setup

| Parameter | Value |
|-----------|-------|
| Geometry | Axisymmetric C-D nozzle |
| Inlet total pressure (p₀) | 10 kPa |
| Simulation time | 0.7 s |
| Time step | 0.001 s |
| Fluid | Air (M = 29 kg/kmol, γ = 1.4, cₚ = 1005 J/kg·K, μ = 0, Pr = 1) |
| Flow type | Inviscid, laminar, steady, non-conducting |

## Pressure ratio cases

| Sub-folder | pₑ/p₀ | Flow regime |
|------------|--------|-------------|
| `p89/` | 0.89 | Subsonic isentropic |
| `p75/` | 0.75 | Supersonic with normal shock in diverging section |
| `p16/` | 0.16 | Fully supersonic isentropic |

For `p75/` and `p16/`, initial pressure distributions are prescribed upstream (p₀ = 10 kPa) and downstream (7.5 kPa and 1.6 kPa respectively) of the throat to accelerate convergence toward the choked solution.

## Solver

- **Solver:** rhoCentralFoam
- **Mesh:** blockMesh
- **Platform:** Ubuntu / OpenFOAM 9

## Files

| File / Folder | Description |
|---------------|-------------|
| `p89/`, `p75/`, `p16/` | Case folders for each back-pressure ratio |
| `Figures/` | Pressure and Mach number profiles for all three cases |
| `main.py` | Python post-processing script |
| `Converging-diverging-nozzle.PNG` | Geometry schematic |
