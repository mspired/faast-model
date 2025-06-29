# FAAST: A Physiologic Model of Dynamic Alveolar Fatigue

**Force, Area, Acceleration, Stress‑Transient, Times (FAAST)** is an open‑source computational model that translates global ventilator settings into *compartment‑level* alveolar wall stress and fatigue risk.
Developed for physiologists, clinicians, and engineers, FAAST reproduces key phenomena of ventilator‑induced lung injury (VILI) in silico and provides actionable metrics such as **TAS** (Total Alveolar Stress), **ASTI** (Alveolar Stress‑Time Index), and 24‑h **P<sub>fail</sub>**.

---

## ⭐ Features

* **20‑compartment nonlinear mechanics** with Laplace‑based stress amplification.
* **Weibull fatigue law** anchored to an empiric stress threshold (σ<sub>th</sub> ≈ 49.8 kPa).
* Millisecond‑resolution solution of the full equation of motion, capturing the early *stress transient* from flow acceleration.
* Turn‑key presets for healthy, stiff ICU, high‑VT, and heterogeneous ALI/ARDS lungs.
* Reproducible Python 3.10 code and Jupyter analysis notebook.

---

## 📦 Installation

```bash
# Clone the repo
$ git clone https://github.com/<your‑username>/faast-model.git
$ cd faast-model

# Create the Conda environment
$ conda env create -f environment.yml
$ conda activate faast
```

> **Note** If you prefer *pip*, simply install the requirements listed in `environment.yml`.

---

## 🚀 Quick Start

Run the healthy‑lung demo and open the analysis notebook:

```bash
# Simulate 24 h with the "healthy" preset
activate faast
python simulate_faast.py --preset healthy

# Launch Jupyter to visualise stress curves, TAS, ASTI
jupyter notebook analyze_outputs.ipynb
```

Command‑line options allow any preset JSON (or your own custom file):

```bash
python simulate_faast.py --preset ards --hours 12 --rr 20
```

---

## 📁 Repository Structure

```
faast-model/
├── LICENSE                # MIT license (see below)
├── README.md              # You are here
├── environment.yml        # Conda dependencies
├── simulate_faast.py      # Main CLI simulation driver
├── analyze_outputs.ipynb  # Interactive plots & tables
├── faast/                 # Core package
│   ├── __init__.py
│   ├── model_core.py      # ODEs & fatigue law
│   ├── parameters.py      # Default constants & σ_th
│   └── utils.py
└── data/
    ├── presets/           # *.json lung mechanics presets
    └── results/           # HDF5 simulation outputs (git‑ignored)
```

---

## 📖 Documentation

A PDF describing the full derivation of the governing equations is in `docs/FAAST_model_theory.pdf`.
API doc‑strings render nicely in VS Code or can be built with Sphinx (see `docs/`).

---

## 🔬 Citing FAAST

If FAAST contributes to your research, please cite:

> Champagne MS. *A Physiologic Model of Dynamic Alveolar Fatigue and Stress Amplification During Mechanical Ventilation.* **J Appl Physiol** (2025). DOI: *pending*.

A permanent DOI for this repository will be minted automatically via Zenodo on tagged releases (`v1.0.0`, `v1.1.0`, …).

---

## 🛡️ License

This project is released under the **MIT License** — see the separate [`LICENSE`](./LICENSE) file for details.

© 2025 Michael S. Champagne
All rights reserved.
