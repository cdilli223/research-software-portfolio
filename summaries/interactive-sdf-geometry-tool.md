# Interactive Signed-Distance-Field Geometry and Visualization Tool

## Summary

Graphics/simulation tool for drawing geometric primitives and freehand closed curves, computing signed distance fields, visualizing distance-based behavior, and debugging sign and aggregation behavior across multiple objects.

This project demonstrates interactive tool design, geometry processing, signed-distance evaluation, rendering, cursor probing, and debugging instrumentation.

## Context

Signed distance fields are useful in graphics and simulation because they encode distance to geometry with an inside/outside sign convention. The tool allowed interactive drawing of circles and closed freehand curves, then computed and visualized the resulting signed distance field.

The core challenge was maintaining correct sign behavior across multiple objects of the same type.

## Technical Problem

The main correctness issue was sign aggregation across multiple shapes. Early versions could handle simple one-object cases but produced incorrect signs when several circles or several polygons were present.

The software needed to evaluate the closest boundary while preserving the correct inside/outside sign for the object that determined the final distance.

## My Contributions

I implemented:

- circle drawing interactions
- closed freehand curve input
- shape storage
- distance-to-segment calculations
- winding-style inside/outside tests
- Catmull-Rom-style curve smoothing
- signed-distance evaluation
- rendering and visualization
- cursor probing
- debugging counters and instrumentation

## Validation and Evidence

I validated the tool through:

- visual inspection
- cursor-probe values near known geometry
- multiple-object cases
- nested and adjacent shapes
- boundary tests
- debugging counters
- sign checks for circles and polygonal curves

## What I Would Improve

If revisiting the project, I would add automated geometry tests with known signed-distance values and split rendering, input handling, and geometry logic into clearer modules. I would also build a small regression suite for multiple-object sign aggregation cases.
