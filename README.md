# FAAST: A Physiologic Model of Alveolar Fatigue

**Force, Area, Acceleration, Stress Transient, Times (FAAST)** is a computational model for simulating regional wall stress and fatigue failure in the lungs under mechanical ventilation.

### 🧠 What It Does

- Models 20-compartment nonlinear alveolar mechanics
- Converts global ventilator inputs into compartmental wall stress
- Embeds a Weibull fatigue law with empirical σ<sub>th</sub>
- Outputs include TAS (Total Alveolar Stress), ASTI (Alveolar Stress-Time Index), and Pfail

### 📁 Repository Structure

- `simulate_faast.py` — runs predefined simulations
- `analyze_outputs.ipynb` — plots stress curves, failure risk, ASTI
- `faast/` — core equations and model logic
- `data/` — parameter presets and simulation outputs
- `environment.yml` — Python dependencies

### 🧪 Requirements

```bash
conda env create -f environment.yml
conda activate faast
