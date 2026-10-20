🇮🇩 Computational Historiography of Macroeconomic Volatility
A Multimodal Early Warning System for Indonesian Rupiah Volatility
Political Narratives · IndoBERT · Deep Learning · Time Series · Fuzzy Logic

Research prototype exploring whether historical political narratives can complement macroeconomic indicators in the analysis of USD/IDR exchange rate volatility.
</div>

🔎 Overview
Traditional macroeconomic forecasting often relies on numerical indicators such as exchange rates, inflation, and policy rates. However, market uncertainty can also be shaped by political events, public narratives, and shifts in collective sentiment.

This project explores a multimodal machine learning framework that combines historical Indonesian political texts with numerical macroeconomic data. The objective is to investigate whether narrative signals can provide additional information for studying exchange rate volatility and developing an interpretable early warning system.

The study focuses on Indonesian political and economic transitions from 1998 to 2026, subject to the availability, consistency, and verification of historical data.
Research status: Experimental research prototype. Findings should be interpreted as preliminary until validated through reproducible evaluation, appropriate baselines, and out-of-sample testing.

✨ Research Objectives
1. Context Aware Political Text Processing
Use IndoBERT (indobenchmark/indobert-base-p1) to represent Indonesian political narratives as contextual embeddings. Text preprocessing is designed to preserve meaningful expressions, including negation and contrast markers, where appropriate.
2. Latent Feature Compression
Explore a deep autoencoder to compress high dimensional text embeddings into a smaller latent representation. The current design investigates reducing 768 dimensional embeddings to five latent features through intermediate layers.
3. Multimodal Time Series Forecasting
Combine latent text representations with numerical macroeconomic indicators using an early fusion approach. A stacked LSTM model with a six month lookback window is explored for sequential forecasting, with a Random Forest Regressor serving as a baseline.
4. Interpretable Risk Classification
Explore a Mamdani Fuzzy Inference System (FIS) that maps selected sociopolitical indicators and model outputs into understandable risk categories.
Indicator	Interpretation
🟢 Green	Low estimated risk
🟡 Yellow	Moderate estimated risk
🔴 Red	High estimated risk


These labels represent model outputs, not official financial advice or guaranteed predictions.
5. Explainability and Historical Evaluation
Investigate feature importance and chronological backtesting around major historical periods, including the 1998 Reformasi, the 2008 global financial crisis, and the 2020 COVID 19 shock. The purpose is to assess whether text derived features contribute useful information beyond numerical variables.
🧠 Conceptual Architecture
Historical Indonesian Political Narratives
                    │
                    ▼
              IndoBERT Encoder
                    │
                    ▼
          Deep Autoencoder
        (Compact Latent Features)
                    │
                    ├──────────────────────┐
                    │                      │
                    ▼                      ▼
          Numerical Indicators      Text Features
                    │                      │
                    └──────────┬───────────┘
                               ▼
                    Multimodal Early Fusion
                               │
                               ▼
                    Stacked LSTM Forecast
                               │
                               ▼
                    Mamdani Fuzzy Inference
                               │
                               ▼
                    Interpretable Risk Signal
This diagram describes the proposed workflow. It should not be interpreted as proof that every component has been fully validated.
🧪 Experimental Evaluation
The evaluation is intended to use chronological data splits to reduce information leakage from future observations into training. Model performance should be compared against simple baselines and reported with suitable forecasting metrics.

Recommended reporting includes:
Evaluation area	What to report
Forecast accuracy	MAE, RMSE, and an appropriate benchmark
Baseline comparison	Random Forest and a simple naive forecast
Temporal robustness	Chronological holdout and rolling evaluation where feasible
Feature contribution	Comparison of numerical only and multimodal inputs
Risk classification	Clearly defined thresholds and classification metrics
Reproducibility	Random seeds, data sources, preprocessing, and package versions


Important: Add numerical results, plots, and claims of model superiority only after they have been verified from actual experiment outputs. Avoid presenting feature contribution percentages as established findings unless the calculation and evaluation procedure are documented.
🛠️ Technology Stack
Component	Technology
Language	Python
Indonesian language representation	Hugging Face Transformers and IndoBERT
Deep learning	PyTorch and/or TensorFlow, depending on the implementation
Sequential modelling	LSTM
Baseline modelling	Scikit learn
Data processing	Pandas and NumPy
Visualisation	Matplotlib, Seaborn, and Plotly
Risk interpretation	Mamdani Fuzzy Inference System


📁 Repository Structure
indonesian-economic-ews-multimodal/
│
├── data_penelitiaan.py    # Main research pipeline
├── .gitignore             # Files excluded from version control
├── LICENSE                # Project license
└── README.md              # Project documentation
The repository structure above reflects the files currently described in this project. Update it if additional modules, datasets, notebooks, or test files are added.
🚀 Getting Started
Prerequisites
Install a compatible Python version and ensure that your environment has sufficient memory for transformer embeddings and deep learning experiments. GPU acceleration may help, but availability depends on your hardware and framework configuration.
1. Clone the Repository
git clone https://github.com/marvelkumaat026-dot/indonesian-economic-ews-multimodal.git
cd indonesian-economic-ews-multimodal
2. Install Dependencies
pip install transformers torch tensorflow scikit-learn pandas numpy matplotlib seaborn plotly
Depending on the implementation, you may not need both PyTorch and TensorFlow. For reproducible work, consider creating a virtual environment and maintaining a pinned requirements.txt.
3. Run the Pipeline
python data_penelitiaan.py
The command above assumes the script is located in the repository root and supports direct execution. Confirm the required input files and configuration before running it.
📊 Data and Reproducibility
For credible research, document the source, date range, frequency, licensing, and preprocessing of every dataset. Record how political texts are collected, how they are aligned with monthly or daily economic observations, and how missing values are handled.

To avoid data leakage, fit preprocessing transformations only on training data. Ensure that text published after a forecast date is never used to predict an earlier outcome. Keep test periods separate until model selection is complete.

No dataset should be described as included unless it is actually present in the repository and available to users.
🔬 Research Questions
1. Do political narrative features improve USD/IDR volatility forecasting beyond numerical macroeconomic indicators alone?
2. How stable are the results across different historical periods and political transitions?
3. Can fuzzy logic translate model outputs into risk categories that are understandable without overstating certainty?
4. Do the observed improvements persist under chronological out of sample evaluation?
⚠️ Limitations
Political text data can contain sampling bias, changing language patterns, and uneven historical coverage. Macroeconomic data may be revised, while crisis periods are rare and difficult to forecast. A model that performs well on one historical period may not generalise to future market conditions.

This project is a research prototype, not a production financial system. It does not provide investment recommendations, and its risk signals should not be used as the sole basis for financial decisions.
📚 Research Reports and Publications
Research notes, manuscripts, and supplementary materials can be linked here as they become available and are ready to share.
Resource	Status
Research manuscript	Add verified public link when available
Dataset documentation	Add source and access details
Experiment results	Add reproducible metrics and figures
Supplementary materials	Add repository paths or public links


🧭 Roadmap
1. Verify data sources and establish a reproducible preprocessing pipeline.
2. Implement numerical only and multimodal baselines.
3. Evaluate models using chronological holdout data.
4. Test whether text features provide measurable incremental value.
5. Calibrate and evaluate fuzzy risk categories.
6. Publish experiment configurations, limitations, and reproducible results.
👤 Author
Marvel Edmund Kumaat

Informatics Engineering student
Universitas Sam Ratulangi, Indonesia
📄 License
This project is intended to use the MIT License if the repository's LICENSE file confirms that choice. Please ensure the license file is present and matches the license stated here.
<div align="center">

Computational Historiography × Multimodal Machine Learning × Macroeconomic Risk Research

Building a reproducible research prototype for studying political narratives and economic volatility.
</div>
