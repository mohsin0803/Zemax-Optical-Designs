# Optical Engineering & Wavefront Optimization Portfolio

Welcome to my optical systems design portfolio. This repository serves as an evolving engineering sandbox where I model, optimize, and analyze optical configurations using **Ansys Zemax OpticStudio**. 

The core goal of this repository is to demonstrate an advanced understanding of ray tracing, sequential lens design, coordinate breaks, solve constraints, and aberration mitigation techniques.

## Active System Designs

### [01_Keplerian_Beam_Expander](./01_Keplerian_Beam_Expander/)
- **System Class:** Afocal Laser Spreading System
- **Key Benchmarks:** M = 3× Magnification | EPD = 10 mm
- **Core Insights:** Explored first-order lens spacing parameters (t = f₁ + f₂). Mastered the use of **Element Power Solves** to anchor individual component focal lengths while dynamically optimizing front curvatures.
- **Aberration Profile:** Effectively mitigated wavefront error down to 35 waves using precise spherical lens bending to minimize third-order spherical aberration (W₀₄₀). Evaluated primary axial chromatic separation using broad F, d, C spectral fields.

### [02_Three_Lens_Telescope](./02_Three_Lens_Telescope/)
- **System Class:** Afocal Terrestrial Keplerian Telescope with Field Lens
- **Key Benchmarks:** M = 20× Magnification | Off-Axis Angles: 0.0°, 0.2°, 0.4°
- **Core Insights:** Solved a critical real-world problem—vignetting of off-axis field bundles—by introducing an intermediate **Field Lens** positioned precisely at the primary intermediate focus via a **Marginal Ray Height Solve (M)**. Utilized **Symmetric Surface Pickup Solves (P)** to enforce component stability.
- **Aberration Profile:** Achieved a **diffraction-limited system** satisfying the Maréchal Criterion, crushing global wavefront error by a factor of 10 down to <0.05 waves. Evaluated residual off-axis aberrations, isolating primary cubic coma in the Transverse Ray Fan.

### [03_Cooke_Triplet_Objective](./03_Cooke_Triplet_Objective/)
- **System Class:** Focal Photographic Objective / Camera Lens System
- **Key Benchmarks:** EFL ≈ 47.7 mm | EPD = 25 mm | Wide-Angle Field: 0.0°, 10.0°, 14.0°
- **Core Insights:** Transited from afocal designs to a true focal imaging system using an alternate **Crown-Flint-Crown (N-BK7 / N-SF2 / N-BK7)** glass configuration. Successfully anchored the image focus plane onto the sensor via a **Marginal Ray Height Solve (M)** on the final air gap.
- **Boundary Optimization:** Discovered and mitigated "wild escape mode" trends and Total Internal Reflection (TIR) failure profiles during optimization. Implemented strict **Glass and Air Boundary Constraints** within the Merit Function Editor, forcing a 2 mm minimum edge thickness rule to guarantee structural physical manufacturability.
- **Aberration Profile:** Successfully balanced third-order off-axis aberrations across a wide field of view, compressing the edge-of-field blur flare from a massive **492 µm down to a balanced 165 µm geometric footprint**. Utilized Transverse Ray Fans and OPD plots to isolate primary third-order astigmatism and residual field curvature at the extreme field points.


## Global Repository Structure
To explore a project, open its dedicated sub-folder to view the underlying `.ZMX` modeling files, structural blueprints, and corresponding high-resolution analysis exports:
```text
├── README.md                           
├── .gitignore                          
│
├── 01_Keplerian_Beam_Expander/
│   ├── 01_keplerian_beam_expander.zmx   
│   ├── README.md                       
│   └── images/                         
│
├── 02_Three_Lens_Telescope/
│   ├── 02_three_lens_telescope.zmx     
│   ├── README.md                       
│   └── images/                         
│
└── 03_Cooke_Triplet_Objective/
    ├── 03_cooke_triplet.zmx            
    ├── README.md                       
    └── images/                         

---

## Contact & Collaboration
If you are an optical engineer, hiring manager, or optics enthusiast looking to discuss ray tracing methodology, aberration theory, or system parameters, feel free to reach out via GitHub Issues or connect with me directly!
