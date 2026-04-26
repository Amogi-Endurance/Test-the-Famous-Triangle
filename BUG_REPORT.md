Bug #1: Flat line rendered for boundary cases (Inequality Theorem)
Title: [BUG] #1: Invalid geometry (5, 5, 10) renders a flat line
Description:
**Summary:** 
The application violates the Triangle Inequality Theorem by attempting to render a shape when the sum of two sides equals the third.

**Steps to Reproduce:**
1. Enter values: Side A=5, Side B=5, Side C=10.
2. Observe the output.

**Expected Behavior:** 
Input should be rejected as "Invalid Triangle" with no graphical rendering.

**Actual Behavior:** 
The system displays "Not a triangle" but visually renders a flat horizontal line.

**Severity:** 🔴 High (Logical & Visual Inconsistency)
