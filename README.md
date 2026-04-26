# Test the Famous Triangle (v1.3.1)

## 📋 Project Overview
This repository documents a formal Quality Assurance audit of the **Famous Triangle Application**. The goal was to verify the intersection of geometric logic (Triangle Inequality Theorem) and graphical UI rendering.

## 🛠 Testing Methodologies
- **Boundary Value Analysis (BVA):** Identifying failure points at the exact limits of valid geometry.
- **Negative Testing:** Validating system resilience against alphanumeric and non-positive inputs.
- **Visual-Logic Synchronization:** Auditing the consistency between text classifications and visual output.

## 📁 Repository Structure
- `/docs`: Contains the detailed [Formal Test Report](./docs/TRIANGLE_APPLICATION_TESTING.docx).
- `README.md`: Project executive summary and QA roadmap.

## 🚨 Key Findings (Defect Summary)
The audit identified **5 Critical Defects** that impact user trust and mathematical accuracy:
1. **Invalid Rendering:** Systems draws a "flat line" for invalid geometry (5, 5, 10).
2. **Sanitization Failure:** Input fields accept alphanumeric strings (e.g., '10A').
3. **Precision Mismatch:** Floating-point rounding causes text/visual inconsistency.

## 👤 Auditor
- **Amogi Endurance**
- Software Test Engineer
