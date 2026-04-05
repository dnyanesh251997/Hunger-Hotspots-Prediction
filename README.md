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
## ⚙️ Methodology

This project follows a **Knowledge Discovery in Databases (KDD)** approach:

### 1. Data Collection
- Dataset: *WFP HungerMap of Zimbabwe* (HDX)
- Contains:
  - Food insecurity indicators
  - Population data
  - Regional information
  - Time-indexed observations

### 2. Data Preprocessing
- Removed irrelevant metadata rows
- Converted date fields to datetime format
- Cleaned column names (lowercase, underscores)
- Handled missing values:
  - Filled prevalence using mean
- Encoded categorical variables using label encoding

### 3. Data Transformation
- Feature engineering:
  - Year, month, quarter features
  - Log transformations
- One-hot encoding for categorical data
- Feature scaling for consistency
- Time-series windowing for LSTM model

### 4. Model Selection
The following models were implemented:
- XGBoost
- Random Forest
- Decision Tree
- Linear Regression
- LSTM (Long Short-Term Memory)

### 5. Training Strategy
- Train-test split: **80% training / 20% testing**
- Target variable: **Prevalence**
<img width="3472" height="1439" alt="image" src="https://github.com/user-attachments/assets/c93751a5-2e2b-416f-8d93-c7b7b6620c79" />

## 📈 Evaluation Metrics

All models are evaluated using:
- **MSE** — Mean Squared Error
- **RMSE** — Root Mean Squared Error
- **R²** — Coefficient of Determination

---
## 🏗️ Design Specification

### Dataset Details
- Total Observations: **6,228**
- Total Features: **9**

#### Feature Types:
- **Numerical**:
  - Population
  - Prevalence
  - Indicator-related features
- **Categorical**:
  - Country code
  - Region
  - Date
  - Data type

### System Architecture
The system follows a **stacked ensemble architecture**:

1. Data Preprocessing & Feature Engineering  
2. Independent Model Training:
   - XGBoost  
   - Random Forest  
   - Decision Tree  
   - Linear Regression  
   - LSTM  
3. Predictions from all models are combined  
4. **Meta-Learner (Linear Regression)** generates final output  

### Evaluation Metrics
- **MSE (Mean Squared Error)**
- **RMSE (Root Mean Squared Error)**
- **R² Score**
<img width="1540" height="840" alt="image" src="https://github.com/user-attachments/assets/1576e065-2e91-4656-b8f5-74841f1ca80e" />
---
## 📈 Model Evaluation

| Model              | MSE    | RMSE   | R² Score |
|-------------------|--------|--------|----------|
| XGBoost           | 0.0012 | 0.0342 | 0.8796   |
| Random Forest     | 0.0029 | 0.0540 | 0.7007   |
| LSTM              | 0.0023 | 0.0483 | 0.4616   |
| Linear Regression | 0.0058 | 0.0759 | 0.4078   |
| Decision Tree     | 0.0013 | 0.0357 | 0.8700   |
| Hybrid Model      | 0.0012 | 0.0347 | 0.8509   |

### Key Insights
- **XGBoost** achieved the highest accuracy (R² ≈ 0.88)
- **Decision Tree** performed similarly well
- **Hybrid Model** improved robustness using ensemble learning
- **LSTM & Linear Regression** underperformed due to:
  - Complexity of data
  - Limitations in capturing non-linear relationships
---
## 🔍 Model Comparison

### Best Performing Models
- ✅ **XGBoost**
- ✅ **Decision Tree**
- ✅ **Hybrid Stacking Model**

### Moderate Performance
- ⚖️ Random Forest

### Low Performance
- ❌ LSTM
- ❌ Linear Regression

### Key Observations
- Ensemble methods outperform single models  
- Hybrid stacking improves:
  - Accuracy
  - Generalization
- Tree-based models capture non-linear relationships effectively  
---
## 🗺️ Tableau Visualization
Predictions from the models are exported to CSV and visualised in **Tableau Desktop**:
1. Open Tableau → Connect to File → Text (CSV)
2. Load the model output CSV
3. Build dashboards to explore regional hunger hotspots

## 📊 Model Prediction Graphs

### 1. XGBoost Prediction
<img width="1442" height="323" alt="image" src="https://github.com/user-attachments/assets/d2ca1e90-7799-4310-8441-526556e4fbe4" />


### 2. Random Forest Prediction
<img width="1437" height="297" alt="image" src="https://github.com/user-attachments/assets/5301af18-e979-48c7-8bed-878c00c436a9" />

### 3. LSTM Time Series Prediction
<img width="1251" height="408" alt="image" src="https://github.com/user-attachments/assets/943071ea-7bfb-4791-aab2-0dba98a1a307" />


### 4. Linear Regression Prediction
<img width="1251" height="408" alt="image" src="https://github.com/user-attachments/assets/6078e86a-fbf3-4c83-b491-fcc7c9123882" />


### 5. Decision Tree Prediction
<img width="1245" height="397" alt="image" src="https://github.com/user-attachments/assets/a3eab5d2-b93e-4208-826e-7df7cd0cfa64" />


### 6. Hybrid Model Prediction
<img width="1222" height="448" alt="image" src="https://github.com/user-attachments/assets/ea59354a-7b1d-43c9-b469-fb23c9bb29a7" />




