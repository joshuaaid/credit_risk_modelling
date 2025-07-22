# Credit‑Risk‑Modelling‑with‑Python 📈  
**An open, notebook‑driven PD ▪︎ LGD ▪︎ EAD ▪︎ Expected‑Loss pipeline on Lending Club loans**

[![Made with Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-%23DA5B0B?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Python ≥ 3.10](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)](https://python.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## ✨ Project snapshot
This public repository delivers a **fully‑reproducible credit‑risk modelling workflow** that covers the complete model life‑cycle:

1. **Data preparation & feature engineering**  
2. **Probability of Default (PD)**  
3. **Loss Given Default (LGD)**  
4. **Exposure at Default (EAD)**  
5. **Portfolio Expected Loss (EL)**  
6. **Ongoing monitoring & drift detection**

Everything is implemented in plain‑vanilla Python—notebooks only, no GPU needed.

---

## 📂 Repository layout

├── data/ # <‑‑ created by notebooks
│   ├── raw/ # original Lending Club CSVs (you provide)
│   └── processed/ # tidy train / test matrices
├── models/ # pickled PD / LGD / EAD artefacts
├── reports/ # PSI plots, EL tables, monitoring PDFs
│
├── Credit Risk Modeling - Preparation - With Comments.ipynb
├── Credit Risk Modeling - PD Model - With Comments.ipynb
├── Credit Risk Modeling - LGD model - With Comments.ipynb
├── Credit Risk Modeling - EAD model - With Comments.ipynb
├── Credit Risk Modeling - LGD and EAD Models - With Comments.ipynb
├── Credit Risk Modeling - Calculating expected loss - With Comments.ipynb
├── Credit Risk Modeling - Monitoring .ipynb
│
├── requirements.txt
├── README.md # ← this file
├── CITATION.cff # citation metadata recognised by GitHub
└── LICENSE


### Notebook quick‑look  

| ▶ | Notebook | Key tasks |
|---|----------|-----------|
| 1 | **Preparation** | Load ≈ 800 k Lending Club loans (2007‑15), clean, encode, split & save. |
| 2 | **PD Model** | Logistic‑regression scorecard, AUC / KS / calibration. |
| 3 | **LGD Model** | Two‑stage recovery‑occurrence + recovery‑rate modelling with Beta calibration. |
| 4 | **EAD Model** | Hybrid linear‑logistic utilisation model with censoring. |
| 5 | **LGD + EAD** | Joint segmentation & validation pipeline. |
| 6 | **Expected Loss** | Combine PD × LGD × EAD → EL, plus macro stress scenarios. |
| 7 | **Monitoring** | PSI, feature drift and performance decay alerts. |

> **Run notebooks in the shown order** for a smooth end‑to‑end narrative.

---

## 🚀 Quick start
# 1 · Clone
git clone https://github.com/joshuaaid/credit_risk_modelling.git
cd credit‑risk‑modelling

# 2 · Install dependencies

# 3 · Download your raw data

# 4 · Launch notebooks
jupyter lab


Minimal install:

pip install pandas numpy scikit-learn scipy matplotlib seaborn

| Stage             | Core ideas                                                    |
| ----------------- | ------------------------------------------------------------- |
| **Data prep**     | Winsorise outliers, WOE binning, time‑based OOT split         |
| **PD**            | Logistic regression with WOE features ➜ scorecard             |
| **LGD**           | Two‑stage model (occurrence + rate) with Beta calibration     |
| **EAD**           | Linear‑logistic utilisation model, predictions clipped \[0‑1] |
| **Expected Loss** | `EL = PD × LGD × EAD × EAD_factor`; stress scenarios          |
| **Monitoring**    | Quarterly PSI, AUC drift alerts (> 5 pp), auto‑reports        |


🤝 Contributing
Fork → git checkout -b feature/my‑feature

Commit → git commit -m 'Add feature'

Push → git push origin feature/my‑feature

Open a Pull Request

Please follow PEP‑8 and include unit tests where relevant.

⚖️ License
This project is released under the MIT License (see LICENSE).

@misc{jafarov20255creditrisk,
  author       = {Joshgun Jafarov},
  title        = {Credit Risk Modelling with Python},
  year         = 2025,
  howpublished = {\url{https://github.com/credit_risk_modelling/credit‑risk‑modelling}},
  note         = {Version 1.0.0}
}

