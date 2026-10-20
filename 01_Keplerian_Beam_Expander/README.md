# Project 1: 3x Keplerian Beam Expander

This folder contains the complete model and performance analysis for a standard afocal Keplerian beam expander built using simple spherical singleton lenses.

## Design Specifications
- **System Type:** Afocal Image Space Enabled
- **Entrance Pupil Diameter (EPD):** 10 mm
- **Wavelength:** 0.587 µm (Monochromatic Baseline)
- **Target Magnification:** 3× (M = f₂ / f₁)
- **Lens 1 Focal Length (f₁):** 25 mm (N-BK7 Crown Glass)
- **Lens 2 Focal Length (f₂):** 75 mm (N-BK7 Crown Glass)

## System Layout & Principal Planes
A basic first-order layout dictates an airspace separation equal to the sum of the focal lengths (t = f₁ + f₂ = 100 mm). However, because real thick lenses house their principal planes deep inside the glass volume, an exact 100 mm air thickness causes the output beam to emerge slightly diverging.

To resolve this, an **Element Power Solve** was implemented on the back surfaces of the lenses to anchor their respective focal lengths. The airspace was set as an active variable (`V`), allowing the optimizer to compress the spacing down to **93.914 mm** to achieve perfect collimation.

### Lens Configurations:
- **Surface 1 (STOP):** Lens 1 Front | Radius: `25.840 mm` | Thickness: `4.000 mm` | Glass: `N-BK7`
- **Surface 2:** Lens 1 Back | Radius: `-25.840 mm` (Element Power Constraint) | Thickness: `93.914 mm` (Variable)
- **Surface 3:** Lens 2 Front | Radius: `77.520 mm` | Thickness: `7.000 mm` | Glass: `N-BK7`
- **Surface 4:** Lens 2 Back | Radius: `-77.520 mm` (Element Power Constraint) | Thickness: `20.000 mm`

---

## Aberration Profile & Analysis

### 1. Primary Spherical Aberration (W₀₄₀)
Entering a wide 10 mm beam into a fast f/2.5 (25 mm / 10 mm) singlet generates massive spherical aberration. 
- **Bending Optimization:** Letting the optimizer freely manipulate the front curvatures ("lens bending") reduced the initial Peak-to-Valley (P-V) wavefront error from **49.54 waves down to 35.12 waves**.
- **Analysis Verification:** On the Transverse Ray Fan Plot, this manifests as a classic cubic symmetric "S-curve," showing a maximum angular ray deviation scale of ± 5.0 mrad at the pupil edge.

### 2. Chromatic Performance (Multi-Wavelength Expansion)
When evaluated across the full visible spectrum (F, d, C), the system demonstrates substantial **Axial Chromatic Aberration**. Because N-BK7 glass possesses a higher refractive index for shorter wavelengths, green/blue rays cross the optical axis prematurely relative to red rays, altering the linear slopes at the origin of the Ray Fan and introducing visible color splitting at the periphery.

---

## Key Visualization Outputs
- `images/01_2d_layout.png` — 2D ray-trace window showing uniform collimation.
- `images/01_ray_fan.png` — Transverse Ray Fan displaying the ± 5.0 mrad spherical aberration profile.
- `images/01_wavefront_map.png` — Wavefront phase map tracking the residual 35.12 waves.
