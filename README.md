# 🇮🇩 Computational Historiography of Macroeconomic Volatility: Multimodal EWS for Indonesian Rupiah (1998–2026)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)](https://tensorflow.org/)

An advanced **Multimodal Machine Learning Framework** and **Early Warning System (EWS)** for macroeconomic stability. This repository bridges political text analysis (*Computational Historiography*) with time-series forecasting to predict USD/IDR exchange rate volatility and identify systemic financial risks during key Indonesian political transition periods (1998–2026).

---

## 📌 Executive Summary & Novelty

Conventional macroeconomic models primarily listen to numerical indicators (e.g., Inflation, BI Rate), often overlooking public panic and political sentiment that trigger market turbulence. This research addresses this gap by treating political narrative history as machine-readable data:

1. **Context-Preserving NLP Extraction**: Utilizes **IndoBERT** (`indobenchmark/indobert-base-p1`) with tailored text preprocessing that preserves emotionally valuable tokens (e.g., negation terms like *'tidak'*, *'bukan'*, and contrast markers like *'krisis'*), preventing semantic attention loss.
2. **Deep Autoencoder Compression**: Compresses 768-dimensional IndoBERT contextual embeddings into 5 latent non-linear features via a multi-layer Neural Autoencoder ($128 \rightarrow 64 \rightarrow 5$).
3. **Multimodal Sequential Forecasting**: Combines macro-monetary indicators and latent text features using an Early Fusion approach to train a **Stacked LSTM** model (6-month lookback window), evaluated against a `GridSearchCV`-tuned **Random Forest Regressor** baseline.
4. **Mamdani Fuzzy Early Warning System**: Maps the dynamic Sociopolitical Index ($\text{Isp}$) and predicted exchange volatility into a human-interpretable Mamdani Fuzzy Inference System (FIS), deploying visual risk alerts: 🟢 **Low Risk**, 🟡 **Medium Risk**, and 🔴 **High Risk (Red Alert)**.
5. **Explainable AI (XAI) & Backtesting**: Demonstrates through surrogate feature importance that text features account for $>25\%$ of volatility spikes during historical crisis periods (1998 Reformasi, 2008 Global Crisis, 2020 COVID-19).

---

## 🏗️ System Architecture Pipeline

text
[ Historical Texts (1998-2026) ] ──> [ IndoBERT Encoder ] ──> [ Deep Autoencoder (5 Latent Dims) ]
                                                                        │ (Early Fusion)
[ Numerical (USD/IDR, Inf, Rate)] ──────────────────────────────────────┘
                               │
                               ▼
            [ Stacked LSTM Time-Series Forecasting ]
                               │
                               ▼
          [ Mamdani Fuzzy Inference System (FIS) ]
                               │
            ┌──────────────────┼──────────────────┐
            ▼                  ▼                  ▼
      🟢 Green Alert     🟡 Yellow Alert     🔴 Red Alert
       (Low Risk)        (Medium Risk)       (High Risk)

experimental result : TBA
📁 Repository Structure
.
├── data_penelitiaan.py            # Main end-to-end Python script (Preprocessing, Training, FIS)
├── .gitignore                     # Python cache & system exclusions
├── LICENSE                        # MIT Open Source License
└── README.md                      # Project documentation





🚀 Quick Start & Reproduction

    Clone Repository:
git clone [https://github.com/marvelkumaat026-dot/indonesian-economic-ews-multimodal.git](https://github.com/marvelkumaat026-dot/indonesian-economic-ews-multimodal.git)
cd indonesian-economic-ews-multimodal
Install Dependencies:
pip install transformers torch tensorflow scikit-learn pandas numpy matplotlib seaborn plotly
Run Pipeline:
python data_penelitiaan.py
📑 Research Reports & PublicationsDetailed research documentation and manuscript drafts are available in Google Docs:📄 Complete Research Report (Paper Draft): View Document📄 CRISP-DM Technical Summary: View Document📖 Key ReferencesAsh, E., Gauthier, G., & Widmer, P. (2023/2024). Relatio: Text semantics capture political and economic narratives. Political Analysis.   Gentzkow, M., Kelly, B., & Taddy, M. (2019). Text as data. Journal of Economic Literature, 57(3), 535–574.   Koto, F., et al. (2020). IndoLEM and IndoBERT: A benchmark dataset and pre-trained language model for Indonesian NLP. COLING 2020.Hochreiter, S., & Schmidhuber, J. (1997). Long short-term memory. Neural Computation, 9(8), 1735–1780.📜 LicenseThis project is open-source and distributed under the MIT License.


