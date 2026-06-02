# ARDS 3D Dynamic Precision Care Model & Bedside Calculator

Official open-source repository for the manuscript:  
**"Three-dimensional dynamic oxygenation exposure and prognosis in acute respiratory distress syndrome: a multicentre cohort study"**

---

## 📌 Clinical Overview

Acute respiratory distress syndrome (ARDS) is characterized by profound biological and clinical heterogeneity. Traditional risk models rely on static single-timepoint measurements, which fail to capture the temporal dynamics and cumulative exposure of oxygenation impairment. 

This repository hosts the bedside decision support system that integrates:
1. **Baseline Inflammatory Phenotyping Core**: Driven by a parsimonious four-biomarker panel (IL-6, TNF-α, procalcitonin, lactate) with cooperative game-theoretic SHAP (SHapley Additive exPlanations) attribution.
2. **7-Day Trajectory Modeling Core**: Projecting patient real-time oxygenation changes onto a three-dimensional latent survival surface generated via Generalized Additive Models (GAM) with tensor product smooth functions ($t \otimes \text{PaO}_2/\text{FiO}_2$).

---

## 💻 Bedside Interactive Tool (Web Interface)

The bedside calculator is packed into an open-access, responsive web interface. You can access the live system directly at:  
👉 **[Online Bedside 3D Calculator](https://mcp.edgeone.site/share/GHQY13Cg2dG1IrkfFZEZy)**

### Key Technical Implementations:
* **WebGL Hardware Acceleration**: Uses `Plotly.js` (v2.24.1) WebGL engine to render high-performance 3D latent surfaces.
* **Camera Angle Locking**: Prevents 3D viewport resets when input metrics are updated.
* **PCHIP Shape-Preserving Interpolation**: Implements Piecewise Cubic Hermite Interpolating Polynomials to model smooth trajectories without unphysiological overshooting.

---

## 🛠️ Offline Deployment & Local Usage

To run the interactive bedside calculator offline on your local machine:
1. Clone this repository:
   ```bash
   git clone https://github.com/ccmzhangrui/ards-3d-tool.git
