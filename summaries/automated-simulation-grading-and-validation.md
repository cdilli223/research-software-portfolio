# Automated Simulation Grading and Validation Infrastructure

## Summary

Private institutional/course repository for validating computer animation simulation submissions. I describe my role, architecture, testing strategy, and validation approach in the representative software contributions document.

The project involved Python infrastructure for running, validating, and comparing numerical simulation submissions against expected behavior using controlled execution, folder-structure checks, oracle comparison, tolerance-based diagnostics, and failure classification.

## Context

Simulation assignments can fail in many ways. A submission may have the wrong file structure, fail to import, crash at runtime, produce malformed state data, time out, or run successfully while diverging numerically from the expected behavior.

The tool was designed to distinguish those cases rather than returning a generic correct/incorrect result.

## Technical Problem

The software needed to validate that each submission matched the expected directory and file structure before execution, run the simulation in a controlled way, extract comparable state data, and compare student outputs against an oracle simulation that represented the expected behavior.

The key challenge was that successful execution alone did not imply correctness. A simulation could run without crashing while producing incorrect trajectories, unstable dynamics, malformed state data, or divergent numerical behavior over time.

## My Contributions

I worked on:

- expected folder and file structure validation
- execution workflow
- simulation state extraction
- oracle/reference comparison
- tolerance-based numerical diagnostics
- malformed-output validation
- timeout handling
- failure classification
- debugging ambiguous grading cases

## Validation and Evidence

The tool was tested against:

- known-good submissions
- intentionally broken submissions
- malformed folder structures
- malformed outputs
- timeout cases
- simulations designed to diverge from the oracle
- cases near numerical tolerance thresholds

## What I Would Improve

If revisiting the project, I would formalize regression tests for each failure category earlier, document the submission data contract more clearly, and add CI checks so later changes to parsing, timeout handling, tolerance thresholds, or oracle comparison logic could not silently alter grading behavior.
