# Physical Activity & Happiness — ML/DL Mini Project

Analysis of the relationship between physical activity and happiness across countries using machine learning models.

**Course:** Machine Learning & Deep Learning  
**Team:** Melisa, Han Yu, Alejandro, Meron  
**Progress Seminar:** 10 June 2026 · **Final Submission:** 24 June 2026

---

## Objective

This project investigates whether physical inactivity levels are associated with national happiness scores on a global scale. Using WHO physical activity data and the World Happiness Report, we apply supervised and unsupervised machine learning models to explore and quantify this relationship.

---

## Datasets

| Dataset | Source | Description |
|---|---|---|
| World Happiness Report 2015 | [Kaggle](https://www.kaggle.com/datasets/mathurinache/world-happiness-report) | Happiness scores and contributing factors (GDP, family, health, freedom) for 158 countries |
| World Happiness Index 2013–2023 | [Kaggle](https://www.kaggle.com/datasets/simonaasm/world-happiness-index-by-reports-2013-2023) | Multi-year happiness scores used to compute per-country averages |
| WHO Physical Activity Country Profiles 2022 | [Kaggle](https://www.kaggle.com/datasets/yingwoowang/who-physical-activity-country-profile-2022) | Physical inactivity rates by age group and gender for 194 countries |

All three datasets are merged on the `Country` column, resulting in 131 matched countries.

---

## Project Structure

```
ml-happiness-activity/
├── data/
│   ├── world_happiness.csv           # World Happiness Report 2015
│   ├── world_happiness_allyears.csv  # World Happiness Index 2013-2023
│   ├── who_physical_activity.csv     # WHO Physical Activity data
│   └── merged_clean.csv              # Final merged & cleaned dataset (auto-generated)
├── notebooks/
│   ├── 01_data_exploration.ipynb     # Data loading, merging, cleaning
│   ├── 02_eda.ipynb                  # Visualizations and correlation analysis
│   ├── 03_linear_regression.ipynb    # Linear Regression model (coming soon)
│   ├── 04_random_forest.ipynb        # Random Forest model (coming soon)
│   └── 05_kmeans.ipynb               # K-Means clustering (coming soon)
├── models/                           # Saved trained models (.pkl files)
├── reports/                          # Generated figures for the IEEE report
├── requirements.txt
└── README.md
```

---

## Models

- **Linear Regression** — Predicts happiness score from physical inactivity and other features
- **Random Forest** — Non-linear model; used to assess feature importance
- **K-Means Clustering** *(optional)* — Groups countries by activity and happiness levels

---

## Key Findings (so far)

- Correlation between average adult inactivity and happiness score: **0.40**
- Strongest predictor of happiness: **Economy (GDP per Capita)** at 0.80
- Note: the positive inactivity-happiness correlation is likely a confounding effect — wealthier countries tend to have both higher happiness and more sedentary (office-based) lifestyles

---

## Setup & How to Run

### 1. Clone the repository
```bash
git clone https://github.com/msubasii/ml-happiness-activity.git
cd ml-happiness-activity
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Add the datasets

Download the three datasets from the links above and place them in the `data/` folder with these exact names:
```
data/world_happiness.csv
data/who_physical_activity.csv
data/world_happiness_allyears.csv
```

> The datasets are not included in the repository due to file size. Download them from Kaggle using the links in the Datasets section.

### 4. Launch Jupyter

Open a terminal in the project folder and run:
```bash
python -m jupyter notebook
```

This opens Jupyter in your browser. Navigate to the `notebooks/` folder.

### 5. Run notebooks in order

Notebooks must be run in order — each one builds on the output of the previous:

| Notebook | Description | Output |
|---|---|---|
| `01_data_exploration.ipynb` | Load, merge, and clean all three datasets | `data/merged_clean.csv` |
| `02_eda.ipynb` | Visualizations and correlation analysis | Figures in `reports/` |
| `03_linear_regression.ipynb` | Linear Regression model | Results + model in `models/` |
| `04_random_forest.ipynb` | Random Forest model | Results + model in `models/` |
| `05_kmeans.ipynb` | K-Means clustering | Results + figures |

---

## TODO

- [ ] Fix country name mismatches to increase merged dataset from 131 to ~150+ countries (e.g. 'Turkiye' vs 'Turkey')
- [ ] Build Linear Regression model (`03_linear_regression.ipynb`)
- [ ] Build Random Forest model (`04_random_forest.ipynb`)
- [ ] K-Means clustering (`05_kmeans.ipynb`)
- [ ] Write IEEE report on Overleaf
