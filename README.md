# Space Y Launch Cost and Reuse Prediction

## Project Overview

Space Y aims to compete in the commercial launch market by leveraging reusable booster technology to reduce costs and improve reliability. This project develops a data-driven framework to:

1. **Collect & Integrate Launch Data** from public APIs and web sources.
2. **Wrangle & Store** that data for analysis.
3. **Explore & Visualize** key launch parameters using SQL, Python, and Folium.
4. **Engineer Features** relevant to first-stage recovery, such as payload mass, grid fin usage, and prior reuse history.
5. **Train & Tune** classification models to predict first-stage landing success.
6. **Communicate Results** through interactive dashboards and a comprehensive report.

## Repository Structure

```

├── notebooks/                     # Jupyter notebooks by stage
│   ├── Data Wrangling.ipynb       # Cleaning, merging, and transforming raw data
│   ├── Data Collection API.ipynb  # Fetching launch data via SpaceX API
│   ├── Data Collection with Web Scraping lab.ipynb  # Supplementary scraping of launch logs
│   ├── EDA with SQL.ipynb         # Exploratory queries and aggregations in SQL
│   ├── EDA with Visualization .ipynb  # Charts, histograms, and correlation plots
│   ├── Interactive Visual Analytics with Folium.ipynb  # Geospatial mapping of landing sites
│   └── Machine Learning Prediction.ipynb  # Model pipelines, GridSearchCV, and evaluation
└── README.md                      # Project overview and setup instructions
```

## Getting Started

1. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

2. **Run Notebooks**:

   * Data Wrangling: `notebooks/Data Wrangling.ipynb`
   * Data Collection (API & Scraping): `notebooks/Data Collection API.ipynb`, `notebooks/Data Collection with Web Scraping lab.ipynb`
   * EDA: `notebooks/EDA with SQL.ipynb`, `notebooks/EDA with Visualization .ipynb`
   * Geospatial Mapping: `notebooks/Interactive Visual Analytics with Folium.ipynb`
   * Modeling: `notebooks/Machine Learning Prediction.ipynb`

3. **Launch Dashboard**:

   ```bash
   python dashboards/app.py
   ```

## Key Findings

* **Best Model**: Random Forest delivered 92% accuracy and ROC-AUC of 0.90.
* **Top Predictors**: `PayloadMass`, `GridFins`, `ReusedCount`, and `Orbit` category.
* **Visualization Insight**: West Coast launch sites show higher landing success rates.

