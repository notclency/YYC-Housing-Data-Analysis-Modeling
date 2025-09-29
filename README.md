# Calgary Housing Price Prediction

This project explores housing data from Calgary to predict assessed property values. It applies feature engineering, preprocessing pipelines, and a machine learning model to improve predictive performance.

The main workflow is implemented in [`prod.py`](./prod.py), which prepares derived features, applies a preprocessing pipeline, and generates predictions.

---

## 📊 Project Overview

* **Goal:** Predict housing values using city data on land use, size, construction year, and location.
* **Dataset:** Housing property assessment dataset from Calgary.
* **Techniques Used:**

  * Feature engineering (log transforms, categorical grouping, contextual imputations).
  * Preprocessing pipelines for numeric and categorical features.
  * Supervised learning model integrated with `scikit-learn`.

---

## 🛠️ Features

* **Derived Features:**

  * `ERA`: Categorizes properties by year of construction (e.g., Pre-1900, 1950-1999, etc.).
  * `QUADRANT`: Extracted from property address (NW, NE, SW, SE).
  * `LOG_LAND_SIZE`: Log transformation to reduce skewness.
  * `LAND_USE_GROUPED`: Simplified land use categories (Residential, Commercial, Industrial, etc.).

* **Data Imputation Strategies:**

  * Missing `LAND_SIZE_SM` replaced by median values within contextual groups.
  * Missing `YEAR_OF_CONSTRUCTION` filled by group medians.
  * Missing `LAND_USE_DESIGNATION` imputed using group modes.

* **Model Integration:**

  * Pre-trained preprocessing pipeline and model saved with `joblib`.
  * Predictions generated via `predict()` function.

---

## 🚀 How to Run

1. Clone this repository:

   ```bash
   git clone <your_repo_url>
   cd <your_repo_name>
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Ensure you have the trained model file:

   ```
   preprocessing_pipeline_and_model.pkl
   ```

4. Run predictions on holdout data:

   ```bash
   python prod.py
   ```

---

## 📈 Example Outputs

### Prediction Plot

When running `prod.py`, a scatter plot is generated comparing **actual vs. predicted house values**:

![Prediction Plot](./images/prediction_plot.png)

*(Red line = perfect predictions, dots = actual vs predicted values)*

---

## 📝 Reflections

From our exploration:

* Handling skewed distributions and missing data was one of the largest challenges.
* Contextual imputations (e.g., filling missing land size with medians of similar property groups) improved robustness.
* Collaboration was most effective using real-time discussion over Discord screen sharing.

See full reflections in [`reflections.md`](./reflections.md).

---

## 📂 Repository Structure

```
.
├── prod.py                # Main preprocessing and prediction script
├── README.md              # Project documentation
├── reflections.md         # Project reflections
├── data/                  # Dataset directory (not included in repo)
└── images/                # Saved plots and visualizations
```

---

## 🙌 Contributors

* Glenn
* Team members (add names here)

---
