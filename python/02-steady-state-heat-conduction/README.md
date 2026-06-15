# Steady-state temperature distribution in a 2D plate

Numerical solution of the 2D steady-state heat conduction equation using iterative finite-difference methods, with parametric studies on grid size and relaxation factor.

## Problem setup

| Parameter | Value |
|-----------|-------|
| Plate dimensions | 5 m × 4 m |
| Boundary conditions | Dirichlet (constant temperature) on all edges |
| BC values | AB = 92 °C, CD = 3 °C, EF = 32 °C, G = 32 °C |
| Grid step size | Δx = Δy = 0.05 m (aspect ratio β = 1) |
| Initial temperature | 0 °C throughout domain |

## Numerical methods

| Method | Description |
|--------|-------------|
| Point Jacobi | Simultaneous update of all nodes; slowest convergence |
| Point Gauss-Seidel | Sequential update using the latest values |
| Point SOR (PSOR) | Gauss-Seidel with over-relaxation factor ω |

Parametric studies examine the effect of grid size, convergence tolerance (ε), and relaxation factor (ω) on iteration count.

## Tools

- **Language:** Python
- **Libraries:** NumPy, Matplotlib

## Files

| File / Folder | Description |
|---------------|-------------|
| `main.py` | Solver implementations and sensitivity studies |
| `Figures/` | Convergence histories for grid-size, ε, and ω sweeps |
| `Results/` | Temperature contour plots |
| `SS-T-distribution.JPG` | Problem schematic and boundary condition labels |
