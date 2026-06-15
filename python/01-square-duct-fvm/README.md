# 2D flow in a square duct — finite volume method

Numerical solution of fully-developed axial flow in a square duct using finite-volume discretisation of the 2D Poisson equation, with three iterative solvers implemented and compared.

## Problem setup

| Parameter | Value |
|-----------|-------|
| Duct cross-section | h × h = 0.1 × 0.1 m |
| Flow direction | Axial (z), fully-developed: ∂w/∂z = 0 |
| Wall BC | No-slip on all four walls |
| Pressure gradient | dp/dz = −3.2 Pa/m |
| Dynamic viscosity | μ = 0.001 Pa·s |
| Density | ρ = 1 kg/m³ |

## Governing equation

The steady, fully-developed assumption reduces the Navier-Stokes equation to a 2D Poisson problem for axial velocity w(x, y):

```
μ (∂²w/∂x² + ∂²w/∂y²) = dp/dz
```

FVM discretisation on a structured Cartesian grid with centred differences at cell faces yields the linear system:

```
aP wP = aE wE + aW wW + aN wN + aS wS − Su
aE = aW = μ Δy/Δx,   aN = aS = μ Δx/Δy,   aP = aE + aW + aN + aS,   Su = (dp/dz) ΔxΔy
```

## Iterative solvers

| Method | Description |
|--------|-------------|
| Jacobi | Simultaneous update of all nodes per iteration |
| Point Gauss-Seidel (PGS) | Sequential update using the latest available values |
| Point SOR (PSOR) | PGS with over-relaxation; ω = 0.1 for this problem |

PSOR is used for the production results due to faster convergence.

## Files

| File / Folder | Description |
|---------------|-------------|
| `main.py` | FVM solver with all three iterative methods |
| `Figures/` | Axial velocity contours and convergence histories |
| `Results/` | Additional output plots |
