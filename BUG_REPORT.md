# Consolidated Bug Report: Triangle Application v1.3.1

### 🚨 Bug #1: Flat line rendered for boundary cases
- **Summary:** The system violates the Triangle Inequality Theorem by rendering a shape when $a + b = c$.
- **Steps:** Input (5, 5, 10).
- **Expected:** Input rejection; no rendering.
- **Actual:** "Not a triangle" message appears, but a flat line is drawn.
- **Severity:** 🔴 High

---

### 🚨 Bug #2: Negative inputs produce "Red Wedge"
- **Summary:** Non-physical negative side lengths are accepted and rendered as artifacts.
- **Steps:** Input (-5, -5, -5).
- **Expected:** Validation error blocking negative numbers.
- **Actual:** A red wedge shape is rendered on the canvas.
- **Severity:** 🔴 High

---

### 🚨 Bug #3: Acceptance of Alphanumeric characters
- **Summary:** Input fields lack numeric sanitization, allowing letters to be processed.
- **Steps:** Input "10A" into any field.
- **Expected:** Form should block non-numeric input.
- **Actual:** System accepts and attempts to process the string.
- **Severity:** 🟡 Medium

---

### 🚨 Bug #4: Zero-length side yields inconsistent UI
- **Summary:** A side length of zero is not properly rejected by the validation logic.
- **Steps:** Input (5, 5, 0).
- **Expected:** Immediate "Invalid Input" error.
- **Actual:** System renders a flat line instead of an error state.
- **Severity:** 🟡 Medium

---

### 🚨 Bug #5: Floating-point precision mismatch
- **Summary:** Rounding issues cause a discrepancy between the text classification and the visual drawing.
- **Steps:** Input (5, 5, 4.9999999999).
- **Expected:** Visual and text both reflect "Isosceles."
- **Actual:** Text says "Isosceles," but the shape appears "Equilateral."
- **Severity:** 🟢 Low
