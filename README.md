# Optical Engineering & Wavefront Optimization Portfolio

Welcome to my optical systems design portfolio. This repository serves as an evolving engineering sandbox where I model, optimize, and analyze optical configurations using **Ansys Zemax OpticStudio**. 

The core goal of this repository is to demonstrate an advanced understanding of ray tracing, sequential lens design, coordinate breaks, solve constraints, and aberration mitigation techniques.

## 📂 Active System Designs

### 📁 [01_Keplerian_Beam_Expander](./01_Keplerian_Beam_Expander/)
- **System Class:** Afocal Laser Spreading System
- **Key Benchmarks:** M = 3× Magnification | EPD = 10 mm
- **Core Insights:** Explored first-order lens spacing parameters (t = f₁ + f₂). Mastered the use of **Element Power Solves** to anchor individual component focal lengths while dynamically optimizing front curvatures.
- **Aberration Profile:** Effectively mitigated wavefront error down to 35 waves using precise spherical lens bending to minimize third-order spherical aberration (W₀₄₀). Evaluated primary axial chromatic separation using broad F, d, C spectral fields.

### 📁 [02_Three_Lens_Telescope](./02_Three_Lens_Telescope/)
- **System Class:** Afocal Terrestrial Keplerian Telescope with Field Lens
- **Key Benchmarks:** M = 20× Magnification | Off-Axis Angles: 0.0°, 0.2°, 0.4°
- **Core Insights:** Solved a critical real-world problem—vignetting of off-axis field bundles—by introducing an intermediate **Field Lens** positioned precisely at the primary intermediate focus via a **Marginal Ray Height Solve (M)**. Utilized **Symmetric Surface Pickup Solves (P)** to enforce component stability.
- **Aberration Profile:** Achieved a **diffraction-limited system** satisfying the Maréchal Criterion, crushing global wavefront error by a factor of 10 down to <0.05 waves. Evaluated residual off-axis aberrations, isolating primary cubic coma in the Transverse Ray Fan.

## 🗂️ Global Repository Structure
To explore a project, open its dedicated sub-folder to view the underlying `.ZMX` modeling files, structural blueprints, and corresponding high-resolution analysis exports:
```text
├── README.md                           <-- (You are here) Main Portfolio Page
├── .gitignore                          <-- Sanitizes out backup (*.BAK) and junk config files
│
├── 01_Keplerian_Beam_Expander/
│   ├── 01_keplerian_beam_expander.zmx   <-- Core Zemax File
│   ├── README.md                       <-- Technical Project Deep-Dive
│   └── images/                         <-- Layout & Ray/OPD Analysis Plots
│
└── 02_Three_Lens_Telescope/
    ├── 02_three_lens_telescope.zmx     <-- Core Zemax File
    ├── README.md                       <-- Technical Project Deep-Dive
    └── images/                         <-- Layout & Ray/OPD Analysis Plots
```

---

## 📬 Contact & Collaboration
If you are an optical engineer, hiring manager, or optics enthusiast looking to discuss ray tracing methodology, aberration theory, or system parameters, feel free to reach out via GitHub Issues or connect with me directly!
