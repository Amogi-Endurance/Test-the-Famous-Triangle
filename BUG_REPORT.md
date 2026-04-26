# Consolidated Bug Report: Triangle Application v1.3.1

### Bug #1: Flat line rendered for boundary cases
- **Summary:** The system violates the Triangle Inequality Theorem by rendering a shape when $a + b = c$.
- **Steps:** Input (5, 5, 10).
- **Expected:** Input rejection; no rendering.
- **Actual:** "Not a triangle" message appears, but a flat line is drawn.
- **Severity:** 🔴 High

---

### Bug #2: Negative inputs produce "Red Wedge"
- **Summary:** Non-physical negative side lengths are accepted and rendered as artifacts.
- **Steps:** Input (-5, -5, -5).
- **Expected:** Validation error blocking negative numbers.
- **Actual:** A red wedge shape is rendered on the canvas.
- **Severity:** 🔴 High

---

### Bug #3: Acceptance of Alphanumeric characters
- **Summary:** Input fields lack numeric sanitization, allowing letters to be processed.
- **Steps:** Input "10A" into any field.
- **Expected:** Form should block non-numeric input.
- **Actual:** System accepts and attempts to process the string.
- **Severity:** 🟡 Medium

---

### Bug #4: Zero-length side yields inconsistent UI
- **Summary:** A side length of zero is not properly rejected by the validation logic.
- **Steps:** Input (5, 5, 0).
- **Expected:** Immediate "Invalid Input" error.
- **Actual:** System renders a flat line instead of an error state.
- **Severity:** 🟡 Medium

---

### Bug #5: Floating-point precision mismatch
- **Summary:** Rounding issues cause a discrepancy between the text classification and the visual drawing.
- **Steps:** Input (5, 5, 4.9999999999).
- **Expected:** Visual and text both reflect "Isosceles."
- **Actual:** Text says "Isosceles," but the shape appears "Equilateral."
- **Severity:** 🟢 Low
---

Bug #6: Large Numerical Overflow
- **Summary:** The application fails to scale the graphical canvas when extremely large values are entered, causing the   triangle to render off-screen or the UI to freeze.
- **Steps:** Input (999999999, 999999999, 999999999).
- **Expected:** The UI should scale the rendering to fit the visible canvas area.
-**Actual:** The triangle renders off-canvas or the browser becomes unresponsive.
- **Severity:** 🟡 Medium
---

Bug #7: Leading/Trailing Whitespace Acceptance
- **Summary:** The input fields do not "trim" whitespace. Entering a space before or after a number causes a validation error.
- **Steps:** Input " 5" (with a leading space) in any field.
-**Expected:** The system should sanitize the input and treat " 5" as "5".
-**Actual:** System rejects the input as a malformed string.
-**Severity:** 🟢 Low
---

Bug #8: Scientific Notation Rejection
- **Summary:** Standard mathematical notation (e.g., 1e3 for 1000) is rejected as alphanumeric by the validation logic.
- **Steps:** Input (1e2, 1e2, 1e2).
- **Expected:** The system should parse scientific notation as a valid number.
- **Actual:** Input is rejected as invalid.
- **Severity:** 🟢 Low
---
Bug #9: Lack of "Clear" or "Reset" Functionality
- **Summary:** There is no way to reset the application state. Previous results and shapes persist during new inputs.
- **Steps:** Run a test for (5, 5, 5), then run a test for (10, 10, 10).
- **Expected:** The canvas should clear before the new triangle is drawn.
- **Actual:** Visual artifacts from previous tests sometimes remain visible.
- **Severity:** 🟡 Medium
---
Bug #10: Empty Field Submission (System Stability)
- **Summary:** Submitting the form with one or more empty fields causes an unhandled "NaN" error.
- **Steps:** Leave one side length blank and click "Submit".
- **Expected:** A validation message: "All fields are required."
- **Actual:** The system displays "NaN" or a broken visual state.
- **Severity:** 🔴 High
---


