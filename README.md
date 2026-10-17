# dis-mpxv-h3l-pipeline
Comprehensive README.md Description Template
Markdown
# Digital Immune System (DIS) — Mpox H3L Epitope Pipeline

[![Python 3.10+](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains the official computational pipeline and output datasets for the research study: **"Population-Level T-Cell Epitope Analysis of Mpox H3L Within a Modular Framework"**. 

The pipeline implements Phase 1 of the **Digital Immune System (DIS)** architecture to predict, quantify, and model cellular immune responses to the *Monkeypox virus* (MPXV) IMV envelope protein H3L (ortholog of vaccinia OPG141).

---

## 🚀 Key Features & Workflow
1. **Target Ingestion (Layer 1):** Processes the 361-amino-acid MPXV H3L reference sequence (NC_063383.1) into overlapping 9-mer peptide windows ($n = 353$).
2. **Antigen Presentation (Layer 2):** Evaluates MHC class I binding and presentation probabilities using **MHCflurry 2.3** across 16 high-frequency human leukocyte antigen (HLA) alleles (HLA-A and HLA-B).
3. **Population Coverage (Layer 5):** Executes Monte Carlo simulations ($n = 100,000$) using global HLA allele frequencies from the Allele Frequency Net Database (AFND).
4. **Immunodynamics (Layer 6):** Simulates coupled non-linear ordinary differential equations (ODEs) to correlate epitope presentation breadth ($S_T$) with systemic viral clearance kinetics.

---

## 📂 Repository Contents
* `dis_mpxv_h3l.py` — The primary end-to-end Python script executing sequence generation, MHCflurry predictions, Monte Carlo population coverage, and figure generation.
* `requirements.txt` — Python package dependencies.
* `results/`
  * `strong_binders.csv` — Filtered strong-binding peptide-allele pairs ($\le 2.0\%$ rank).
  * `top_promiscuous_peptides.csv` — Ranked promiscuous H3L epitope candidates.
  * `all_predictions.csv` — Complete raw prediction dataset across all evaluated alleles.

---

## 🛠️ Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR-USERNAME/dis-mpxv-h3l-pipeline.git](https://github.com/YOUR-USERNAME/dis-mpxv-h3l-pipeline.git)
   cd dis-mpxv-h3l-pipeline
Create a virtual environment and install dependencies:

Bash
conda create -n dis python=3.10
conda activate dis
pip install -r requirements.txt
mhcflurry-downloads fetch
Run the pipeline:

Bash
python dis_mpxv_h3l.py
The script will generate summary tables and high-resolution multi-panel figures in the results/ folder.
