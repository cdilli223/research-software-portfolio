# Differentiable APIC-DFSPH Solver Blending

## Summary

Research/course project on learned coupling between APIC and DFSPH fluid solvers. The project explored whether a neural gate could learn per-particle blending weights between grid-based and particle-based velocity updates, replacing hand-coded solver switching with a continuous differentiable coupling.

The work gave me practical experience with numerical simulation, differentiable programming, particle-grid methods, SPH-style neighbor search, learned gating, and validation through training curves, gate visualizations, velocity statistics, and rollout comparisons.

## Context

APIC and DFSPH have complementary numerical behavior. APIC provides stable particle-grid updates and coherent large-scale motion. DFSPH preserves particle-level transport and incompressibility behavior, especially near boundaries and obstacles.

The project studied whether both solvers could be executed at each timestep and combined through a learned per-particle gate.

Preliminary results of output gates can be seen in this [gif](../materials/coupling_weights.gif).

## Technical Problem

The project addressed how to couple two fluid solvers with complementary numerical behavior without relying on brittle, hand-coded solver switching. The software problem was to turn solver choice into a continuous, trainable, and inspectable learning problem.

The system needed to compute both candidate updates at each timestep, predict per-particle blending weights, and use physics-informed targets and losses that encouraged meaningful solver preference while keeping rollout behavior stable and physically plausible.

## My Contributions

I worked on Taichi/Python components for:

- particle-grid transfer
- SPH-style neighbor search
- obstacle and boundary handling
- per-particle feature extraction
- adaptive physics-informed targets
- loss terms and diagnostics
- MLP and PointNet-style gate comparison
- visualization and rollout debugging

## Validation and Evidence

Validation used both numerical and visual diagnostics:

- training loss
- learned-versus-target gate behavior
- gate histograms
- velocity statistics
- rollout snapshots
- comparisons between blended, APIC-only, and DFSPH-only behavior

## What I Would Improve

If continuing the project, I would add explicit local-neighborhood context and a clearer suite of fixed evaluation scenes, including unobstructed tunnel flow, centered obstacles, near-wall obstacles, narrow gaps, and randomized obstacle positions. I would also run more systematic ablations of velocity-level and divergence-based losses.
