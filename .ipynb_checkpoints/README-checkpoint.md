# finalproject
This project analyzes Olympic swimming results from 1912 to 2020. The goal is to predict swimmers' performance times using machine learning, with engineered features like race distance, stroke type, and relay participation.
# Dataset
- Source: Olympic Swimming Results 1912–2020 (local CSV)
- Number of observations: 25,000+
- Features include: Athlete, Team, Stroke, Gender, Distance, Year, Rank, Result time
- Target variable: `Results_float` (swim time in seconds)
# How to Run
1. Clone this repository:
   `git clone <your repo URL>`
2. Navigate to the project folder and open the notebook:
   `cd <repo_name>`
   `jupyter notebook final_project_draft.ipynb`
3. Install dependencies if needed:
4. Run cells sequentially in the notebook.
# Current Results
- Features engineered: `Distance_m`, `IsRelayAndMale`, `Year_Since_2000`
- Models implemented: Linear Regression and Random Forest
- Linear Regression: RMSE = 12.3 seconds, R² = 0.85
- Random Forest: RMSE = 10.9 seconds, R² = 0.88
- Next steps: Additional feature engineering, hyperparameter tuning, improved visualizations