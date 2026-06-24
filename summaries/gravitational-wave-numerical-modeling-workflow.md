# Gravitational-Wave Numerical Modeling Workflow

## Summary

Research software work involving Python and Mathematica scripts for modeling compact-object gravitational-wave quantities, frequency thresholds, signal-strength estimates, and detectability behavior.

The project focused on producing tentative observable estimates based on constituent black hole size, orientation, and proximity in a merger scenario. The code evaluated how predicted signal behavior changed as a function of proximity, angle, and black hole size.

## Context

The research translated mathematical expressions from general relativity and statistical detectability assumptions into reproducible numerical calculations. The goal was to study how merger geometry and constituent properties could affect potentially observable signal behavior.

Rather than computing isolated values, the workflow supported parameter sweeps and comparison across physical configurations.

## Technical Problem

The project addressed how to turn a theoretical merger model into an inspectable computational workflow. The software needed to evaluate signal behavior across ranges of black hole size, angular configuration, and separation/proximity assumptions while preserving the physical assumptions behind each run.

A key challenge was making the dependence on input parameters clear, rather than treating each calculation as a one-off script.

## My Contributions

I worked on:

- translating theoretical expressions into numerical calculations
- evaluating frequency thresholds
- estimating signal-strength behavior
- running parameter sweeps across size, angle, and proximity
- generating plots and tables for analysis
- inspecting trends across physical configurations
- checking intermediate quantities for physical consistency

## Validation and Evidence

Validation involved:

- checking limiting cases
- comparing trends across parameter sweeps
- inspecting whether outputs changed smoothly and physically with parameter choices
- comparing independent calculations where possible
- reviewing consistency with the underlying model assumptions

## What I Would Improve

If revisiting the project, I would separate model definitions from plotting and analysis code more cleanly, add regression tests for known reference cases, and document the assumptions behind each computational experiment more explicitly. I would also package the workflow so parameter sweeps could be rerun from a single configuration file.
