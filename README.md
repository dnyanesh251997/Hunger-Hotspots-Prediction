# 🍽️ Hunger Hotspots Prediction
### Evaluating the Effectiveness of Data-Driven Prediction for Early Crisis Identification
---

## 📌 Project Overview

This project evaluates the effectiveness of machine learning models for predicting hunger hotspots and enabling early crisis identification. Using data from the World Food Programme's HungerMapLive platform, multiple models were trained and compared to forecast food insecurity prevalence across regions in Zimbabwe.

---

## 📂 Repository Structure

```
hunger-hotspots-prediction/
│
├── data/
│   ├── wfp_data.csv                  # Raw dataset from WFP HungerMapLive (HDX)
│   └── cleaned_dataset.csv           # Preprocessed/cleaned dataset
│
├── notebooks/
│   └── Code.ipynb                    # Full implementation notebook
│
├── docs/
│   ├── Config_File.pdf               # Configuration manual
│   └── Report.pptx                   # Research presentation slides
│
├── README.md                         # This file
└── requirements.txt                  # Python dependencies
```

---

## 📊 Dataset

- **Source:** [WFP HungerMapLive — Zimbabwe (HDX)](https://data.humdata.org/dataset/wfp-hungermap-data-for-zwe)
- **Platform:** Humanitarian Data Exchange (HDX) — humdata.org
- **Key columns:** `countrycode`, `countryname`, `adminone`, `adminlevel`, `date`, `datatype`, `indicator_name`, `population`, `prevalence`

---

## ⚙️ System Requirements

| Component | Details |
|-----------|---------|
| OS | Windows 11 Home (or any OS supporting Python 3.12+) |
| Python | 3.12.9 |
| Environment Manager | Miniconda |
| IDE | Jupyter Notebook / VS Code |

---

## 🛠️ Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/hunger-hotspots-prediction.git
cd hunger-hotspots-prediction
```

### 2. Create and Activate Conda Environment

```bash
conda create -n hunger_env python=3.12.9
conda activate hunger_env
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Then open `notebooks/Code.ipynb`.

---

## 📦 Dependencies

```
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
tensorflow
jupyter
```

All dependencies are listed in `requirements.txt`.

---

## 🤖 Models Implemented

| Model | Purpose |
|-------|---------|
| **Linear Regression** | Baseline hunger prevalence prediction |
| **Decision Tree Regressor** | Rule-based regional classification |
| **Random Forest Regressor** | Ensemble prediction with feature encoding |
| **XGBoost Regressor** | Gradient boosting for high-accuracy prediction |
| **LSTM (Deep Learning)** | Time-series forecasting of prevalence trends |
| **Hybrid Stacked Model** | Meta-model combining all five model outputs |

---

## 📈 Evaluation Metrics

All models are evaluated using:
- **MSE** — Mean Squared Error
- **RMSE** — Root Mean Squared Error
- **R²** — Coefficient of Determination

---

## 🗺️ Tableau Visualization

Predictions from the models are exported to CSV and visualised in **Tableau Desktop**:
1. Open Tableau → Connect to File → Text (CSV)
2. Load the model output CSV
3. Build dashboards to explore regional hunger hotspots

---

## 📖 References

- Humdata.org (2024). *Zimbabwe - HungerMap data — Humanitarian Dataset — HDX*. https://data.humdata.org/dataset/wfp-hungermap-data-for-zwe

- Sundaram, J. et al. (2023). An exploration of python libraries in machine learning models for data science. *Handbook of Research on Advanced Practical Approaches to Deepfake Detection and Applications*, IGI Global.

---

