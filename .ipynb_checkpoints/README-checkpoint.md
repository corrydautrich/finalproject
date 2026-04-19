# Olympic Swimming Performance Analysis

## Project Overview
This project analyzes Olympic swimming results from 1912–2020 to predict race performance (swim times) and medal outcomes using machine learning models. The goal is to identify key factors that influence performance and provide actionable insights for training and evaluation.

---

## Dataset
- Source: Olympic Swimming Results 1912–2020 (CSV dataset)
- Observations: 25,000+ records
- Features include:
  - Athlete, Team, Stroke, Gender
  - Distance, Year, Rank, Result time
- Target variables:
  - Regression: `Results_float` (time in seconds)
  - Classification: `Medal` (Gold, Silver, Bronze, None)

---

## Feature Engineering
The following engineered features were created to improve model performance:

- `Distance_m`: Numeric race distance
- `Event_Type`: Sprint / Mid / Distance classification
- `Speed`: Distance divided by time (efficiency measure)
- `Avg_Time_Stroke`: Average performance by stroke
- `Avg_Time_Gender`: Average performance by gender
- `Event_Complexity`: Interaction between distance and relay events
- `Is_Sprint`: Binary indicator for short races

These features capture both structural differences across events and performance efficiency.

---

## Models Implemented

### 1. Linear Regression (Baseline)
- Used as a baseline model for predicting swim times
- Requires feature scaling

### 2. Random Forest (Optimized)
- Used for both regression and classification
- Hyperparameters tuned using GridSearchCV:
  - `n_estimators`: 100, 200
  - `max_depth`: None, 10

---

## Final Results

| Model | RMSE | R² | Accuracy |
|------|------|------|---------|
| Linear Regression | ~12 sec | ~0.85 | — |
| Random Forest Regression | ~10–11 sec | ~0.88 | — |
| Random Forest Classification | — | — | ~85–90% |

---

## Key Insights
- Race distance and event type are the strongest predictors of performance.
- Speed (efficiency) is a critical feature across all events.
- Random Forest significantly outperforms Linear Regression due to its ability to capture nonlinear relationships.
- Model performance is weaker for long-distance events, indicating higher variability in endurance races.

---

## Business Recommendations
- Coaches should focus on improving swimmer efficiency (speed) rather than only raw time.
- Training programs should differ significantly between sprint and distance events.
- The model should be used as a **decision-support tool**, not a fully automated system.
- Regular retraining is recommended as new competition data becomes available.

---

## Ethical Considerations
- Potential bias exists due to uneven representation of genders, strokes, and countries.
- Model errors may disproportionately impact underrepresented groups or specific event types.
- Human oversight is required to prevent misuse in high-stakes decisions (e.g., athlete selection).

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/corrydautrich/finalproject.git
2. Navigate to the project directory:
   ```bash
   cd finalproject
3. Install required packages:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
4. Run the notebook:
   ```bash
   jupyter notebook final_project.ipynb
5. Run all cells from top to bottom