# Space Y Launch Cost and Reuse Prediction

## Project Scenario & Overview

Space Y is a new entrant in the commercial space industry, aiming to offer competitive launch services by optimizing cost and reliability. SpaceX’s Falcon 9 has demonstrated that first-stage reuse can reduce launch costs from over \$165 million to approximately \$62 million. Replicating this advantage requires accurate prediction of booster recovery success prior to each mission.

This project addresses the following objectives:

1. **Quantify Economic Impact**: Analyze historical launch data to determine how first-stage landings influence overall mission cost.
2. **Predict Recovery Success**: Develop and evaluate machine learning classifiers that forecast whether a Falcon 9 first stage will land successfully, based on pre-launch parameters.
3. **Enable Data-Driven Pricing**: Construct interactive dashboards delivering actionable insights on recovery probabilities and cost metrics, supporting Space Y’s strategic pricing and bidding decisions.

The analysis pipeline includes data acquisition, preprocessing, exploratory analysis, feature engineering, model development with hyperparameter tuning, and deployment of visual analytics tools.

1. **Data Collection & Processing**
   • Gather historical Falcon 9 launch data (payload mass, orbit, launch site, grid fins, reuse counts, etc.).
   • Clean and preprocess to handle missing values and categorical variables (e.g., launch site, orbit type).

2. **Exploratory Data Analysis**
   • Visualize success vs. failure rates across launch parameters.
   • Identify patterns in booster reuse and landing outcomes.

3. **Feature Engineering**
   • Create derived variables such as launch mass categories, mission type flags, and environmental conditions.

4. **Model Development & Tuning**
   • Implement classification pipelines (Logistic Regression, Random Forest, SVM, XGBoost) to predict recovery success.
   • Optimize hyperparameters with cross-validation (GridSearchCV).

5. **Dashboard & Reporting**
   • Develop interactive dashboards (Plotly Dash and Folium) to display feature importances, confusion matrices, and cost projections.
   • Summarize findings and recommend pricing strategies aligned with predicted reuse rates.

## Repository Structure

```bash
├── data/                           # Raw and processed datasets
│   ├── launches.csv               # SpaceX Falcon 9 historical data
├── notebooks/                      # Analysis and prototyping notebooks
│   ├── 01_data_collection.ipynb    # API & web scraping of launch data
│   ├── 02_data_preprocessing.ipynb# Cleaning & feature engineering
│   ├── 03_eda_visualization.ipynb  # Exploratory plots and maps
│   ├── 04_model_training.ipynb     # ML pipelines & hyperparameter tuning
│   └── 05_evaluation_reporting.ipynb# Metrics, confusion matrices & cost analysis
├── src/                            # Python modules for reuse
│   ├── collect.py                 # Data fetching utilities
│   ├── preprocess.py              # Cleaning and feature functions
│   ├── train.py                   # Model pipeline definitions
│   └── dashboard.py               # Dash app and Folium map components
├── dashboards/                     # Deployed dashboard files
│   ├── app.py                     # Plotly Dash application
│   └── assets/                    # CSS and static assets
├── reports/                        # Final PDF report and slides
│   ├── SpaceY_Capstone_Report.pdf
│   └── presentation.pptx
├── requirements.txt                # Python dependencies
└── README.md                       # Project overview and setup instructions
```

## Quickstart

1. **Clone the repo:**

   ```bash
   git clone https://github.com/your-org/spacey-launch-costs.git
   cd spacey-launch-costs
   ```
2. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```
3. **Launch notebooks:**

   ```bash
   jupyter notebook notebooks/01_data_collection.ipynb
   ```
4. **Run dashboard:**

   ```bash
   python dashboards/app.py
   ```

## Summary of Findings

* **Top Predictors of Recovery:** `ReusedCount`, `GridFins`, and `PayloadMass`.
* **Model Performance:** Random Forest achieved 90% accuracy and 0.88 ROC-AUC on test data.
* **Cost Impact:** Successful booster recovery reduces launch cost to \~\$62 M; failures revert cost to \$165 M.

**Recommendation:** Integrate the predictive classifier into Space Y’s bid engine to adjust pricing dynamically based on recovery probability, maximizing profitability and competitive edge.

---

## License

This project is licensed under the MIT License.
