# Finite Element Analysis of a Soda Can  
**ME-373 – Finite Element Modeling and Simulation (EPFL)**

## Overview

This project investigates the structural behavior of an aluminum soda can under:

1. Internal pressure (static analysis)  
2. Axial compression (elastic buckling analysis)

The study was performed using Abaqus, with detailed mesh convergence and comparison with experimental results.

## Static Analysis – Internal Pressure

### Objective
Evaluate stress distribution and maximum displacement when the can is subjected to internal pressure (~2 atm).

### Modeling Choices
- Shell model (thickness = 0.22 mm)
- Two aluminum alloys:
  - 3104-H19
  - 5182-H19
- Linear elastic behavior
- Half-model using symmetry
- Quadratic triangular shell elements

### Results (converged mesh)
- Maximum displacement ≈ 2.32 mm (bottom center)
- Maximum Von Mises stress ≈ 1.77 GPa (bottom edge)

After modifying bottom thickness to better match reality:
- Stress reduced significantly (~350 MPa range)
- Results became physically consistent

Mesh convergence error < 0.5%

## Elastic Buckling Analysis

### Objective
Determine the critical axial load causing instability.

### Method
- Linear eigenvalue buckling analysis
- Full model (no symmetry to preserve asymmetric modes)
- Applied 1 N reference load → eigenvalue gives critical load multiplier

### Converged Results
- First critical load: ≈ 1595 N
- Relative mesh error ≈ 0.16%

## Experimental Comparison

A physical test was performed by progressively loading a real can.

Estimated real buckling load:
- ≈ 600–800 N

Conclusion:
- Linear buckling analysis overestimates critical load (~factor 2)
- Strong sensitivity to geometric imperfections
- Real collapse governed by plasticity + imperfections

## Tools

- Abaqus
- Fusion 360
