# UBC computational fluid dynamics

**Course simulations and numerical methods projects — Computational Fluid Dynamics (CFD), University of British Columbia (UBC)**

*Mechanical Engineering — Computational Fluid Dynamics, University of British Columbia*

Arash J. Khabbazi

[![Language](https://img.shields.io/badge/language-Python-blue)](https://www.python.org/)
[![Solver](https://img.shields.io/badge/solver-OpenFOAM-green)](https://www.openfoam.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

> **TL;DR** OpenFOAM simulations and Python numerical implementations from a graduate CFD course at UBC — covering incompressible laminar flow, compressible nozzle dynamics, turbulence modelling, and finite-volume discretisation of elliptic and hyperbolic partial differential equations (PDEs).

---

## Overview

Coursework from the Computational Fluid Dynamics course at the University of British Columbia, organized into two tracks:

- **`openfoam/`** — Six simulation studies solved with OpenFOAM (icoFoam, rhoCentralFoam, simpleFoam), covering laminar and turbulent flows, compressible nozzle flow, and airfoil analysis. Post-processing is performed in ParaView with Python plotting scripts.
- **`python/`** — Three Python implementations of numerical methods: finite-volume method (FVM) discretisation of the 2D Poisson equation, iterative solvers (Jacobi, Gauss-Seidel, successive over-relaxation (SOR)) for steady-state heat conduction, and explicit finite-difference schemes for the inviscid Burgers' equation.

Each project includes a description, result figures, and ParaView `.foam` session files where applicable.

---

## Contents

### OpenFOAM projects (`openfoam/`)

| Folder | Problem | Solver | Key physics |
|--------|---------|--------|-------------|
| `01-lid-driven-cavity/` | 2D lid-driven cavity, Re = 100 | icoFoam | Laminar recirculation, transient vortex development |
| `02-converging-diverging-nozzle/` | Axisymmetric C-D nozzle, three back-pressure ratios | rhoCentralFoam | Subsonic, normal shock, and supersonic isentropic regimes |
| `03-naca5012-airfoil/` | Flow over NACA 5012 at Re = 100, 1000 | icoFoam | Mesh refinement study, pressure distribution, wake structure |
| `04-forward-facing-step/` | Supersonic flow over a forward-facing step, Ma = 3 | rhoCentralFoam | Shock formation, inviscid compressible dynamics |
| `05-incompressible-pipe-flow/` | Laminar pipe flow, Re = 200 | icoFoam | Velocity profile validation against analytical Poiseuille solution |
| `06-turbulent-backward-step/` | Turbulent backward-facing step, Re = 25 400 | simpleFoam | Reynolds-Averaged Navier-Stokes (RANS) turbulence models: Spalart-Allmaras, k-ε, k-ω, k-ω SST |

The converging-diverging nozzle project (`02-converging-diverging-nozzle/`) contains three sub-cases corresponding to back-pressure ratios p_e/p_0 = 0.89 (`p89/`), 0.75 (`p75/`), and 0.16 (`p16/`), which yield subsonic, normal-shock, and fully supersonic flow respectively.

### Python projects (`python/`)

| Folder | Problem | Method | Key implementation |
|--------|---------|--------|--------------------|
| `01-square-duct-fvm/` | 2D axial flow in a square duct (Poisson problem) | FVM on structured grid | Jacobi, point Gauss-Seidel (PGS), and point successive over-relaxation (PSOR) iterative solvers; convergence comparison |
| `02-steady-state-heat-conduction/` | Steady-state temperature distribution in a 2D plate | FVM with Dirichlet boundary conditions (BCs) | Grid-size and relaxation-factor sensitivity; SOR acceleration |
| `03-wave-convection-inviscid/` | 1D wave convection — inviscid Burgers' equation | Explicit finite differences | Lax, Lax-Wendroff, and MacCormack schemes; shock formation animation |

---

## How to run

### OpenFOAM simulations

Simulations were run under OpenFOAM 9 on Ubuntu. Open the `.foam` file in each project with ParaView for post-processing.

```bash
# Example: run lid-driven cavity
cd openfoam/01-lid-driven-cavity
icoFoam
paraFoam -case .
```

For compressible cases (`02` and `04`), use `rhoCentralFoam`. For the turbulent backward step (`06`), use `simpleFoam`.

### Python scripts

```bash
pip install numpy matplotlib
python main.py
```

Each `main.py` is self-contained and produces figures in `Figures/` and `Results/`.

---

## License

This project is released under the [MIT License](https://opensource.org/licenses/MIT).

---

## Contact

**Arash J. Khabbazi** — School of Mechanical Engineering, Purdue University  
[arashjkh@gmail.com](mailto:arashjkh@gmail.com)
