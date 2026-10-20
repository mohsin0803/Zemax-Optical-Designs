# Project 2: 20x Terrestrial Telescope with Field Lens

This folder houses a 20× magnification afocal Keplerian telescope optimized across a wide field of view using an intermediate field lens to eliminate geometric vignetting.

## Design Specifications
- **System Type:** Afocal Image Space Enabled
- **Entrance Pupil Diameter (EPD):** 10 mm (STOP positioned on Surface 1)
- **Field of View (FOV):** 0.0°, 0.2°, 0.4° (Y-Angle Deviation)
- **Primary Wavelength:** 0.55 µm (Monochromatic Baseline)
- **Target Magnification:** 20× (\(M = f_{\text{objective}} / f_{\text{eyepiece}}\))
- **Objective Lens (\(f_o\)):** 400 mm (Plano-Convex, N-BK7)
- **Eyepiece Lens (\(f_e\)):** 20 mm (Plano-Convex, N-BK7)

## The Field Lens Principle & Constraints
In a basic two-lens telescope, highly angled off-axis light rays (0.2° and 0.4°) expand outward after passing through the primary intermediate focal point, completely missing the clear aperture of the eyepiece lens (vignetting).

To resolve this, a **Field Lens** (\(f_f = 20\text{ mm}\)) was positioned precisely at the intermediate image plane. To ensure perfect structural alignment and eliminate manual drift, the following constraint mechanics were applied:
1. **Marginal Ray Height Solve (M):** Applied to the objective airspace (Surface 2 thickness), forcing it to dynamically compute to **395.533 mm** so the paraxial focus lands exactly on the front face of the field lens.
2. **Symmetric Surface Pickup Solve (P):** Configured on the back of the field lens with a Scale Factor of `-1` to lock it into a perfectly symmetric, equiconvex geometry during layout changes.

---

## Aberration Profile & Optimization Results

An **RMS Angular Default Merit Function** was built to optimize the system. By assigning the airspace between the field lens and eyepiece as an active variable, Zemax balanced the spacing down to perfect collimation.

### Performance Breakdown:
- **Wavefront Flatness:** Global Peak-to-Valley (P-V) wavefront error completely collapsed by an entire order of magnitude—**shrinking from ± 1.00 waves down to ± 0.100 waves**. This satisfies the Maréchal Criterion for a **diffraction-limited optical system**.
- **Isolating Off-Axis Coma:** Because the massive defocus parabolas were zeroed out, the residual aberrations became visible. At the 0.4° extreme field position, the **Ray Fan plot exhibits a cubic S-shape**, and the **OPD Fan displays an asymmetric, quadratic U-shape profile**, which is the classic mathematical signature of primary **Coma**.

---

## Key Visualization Outputs
- `images/02_2d_layout.png` — Clear visualization showing off-axis bundles smoothly corralled by the field lens.
- `images/02_ray_fan.png` — Ray fan plots showing perfectly straight, flat, centered configurations.
- `images/02_opd_fan.png` — Transverse OPD fan showing the minute ± 0.100 wave residual coma signature.
