# Project 3: High-Performance Cooke Triplet Objective

This directory contains the files for a fully optimized, manufacturable, wide-angle camera objective. The Cooke Triplet is historically significant as the minimum number of elements required to control all seven primary Seidel aberrations.

## Design Specifications
- **System Type:** Focal Image Space (Afocal Mode Unchecked — Spot Radius Evaluation)
- **Entrance Pupil Diameter (EPD):** 25 mm
- **Effective Focal Length (EFL):** 47.73 mm (System Speed: ≈ f/2)
- **Spectral Fields:** Full Visible Spectrum (F, d, C Presets)
- **Field of View (FOV):** 0.0° (On-axis), 10.0° (Mid-field), 14.0° (Full-field Corner)

## Material Profile & Mechanical Design
The configuration spreads power across three elements in a **Positive-Negative-Positive (Crown-Flint-Crown)** orientation to counteract structural field curvature and color dispersion:
1. **Lens 1 (Front):** Low-dispersion Crown Glass (`N-BK7`)
2. **Lens 2 (Center):** High-dispersion Flint Glass (`N-SF2`) — **System STOP positioned here**
3. **Lens 3 (Rear):** Low-dispersion Crown Glass (`N-BK7`)

### Managing Manufacturing Boundaries:
Initial unconstrained optimization drives the system into "wild escape mode" profiles, inducing negative glass thicking and Total Internal Reflection (TIR) math violations. To ensure a buildable cell, a **Default RMS Spot Centroid Merit Function** was deployed with active **Glass and Air Boundary Values**:
- **Minimum Edge Thickness:** Forced to `2.0 mm` via the boundary wizard, successfully fixing Lens 3 from a physical crossover shape into a structurally safe meniscus form.
- **Back Focal Length (BFL):** Anchored to a real image focus position using a **Marginal Ray Height Solve (M)** on Surface 6, settling safely at `8.640 mm`.

---

## Final Aberration & Sharpness Analysis

### 1. On-Axis Clarity (`0.0° Field`)
The central field lines lay completely flat along the horizontal axis on both the Ray and OPD fans. This confirms that **Spherical Aberration (W₀₄₀) and Axial Chromatic Aberration are fully eliminated**, yielding an ultra-sharp **RMS Spot Radius of 65.3 µm** directly inside the core pixel field.

### 2. Wide-Angle Stabilization (`14.0° Field`)
- **Color Correction:** At the extreme 14.0° edge of the sensor frame, the F, d, C color curves are tightly compressed, indicating excellent mitigation of **Lateral Color** fringing.
- **Spot Shrinkage:** By setting all 6 radii and both airspaces as interconnected variables, the off-axis geometric blur circle **collapsed from a highly distorted 492 µm flare down to a balanced 165 µm footprint**. The remaining footprint is defined by small, predictable traces of third-order astigmatism and field curvature.

---

## Key Visualization Outputs
- `images/03_2d_layout.png` — Mechanical layout showing optimized lens spacing and sharp image focus.
- `images/03_spot_diagram.png` — Spot footprint showing geometric ray points mapped against the field coordinates.
- `images/03_aberration_fans.png` — Ray Fan and OPD graphs tracking monochromatic and color balancing limits.
