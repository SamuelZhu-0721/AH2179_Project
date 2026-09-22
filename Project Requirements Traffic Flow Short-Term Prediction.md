## Project Requirements: Traffic Flow Short-Term Prediction

### Goal

Build machine learning models that predict, every minute, the traffic **flow or average speed** for the next 15 minutes at the Pampas–Hornsberg bottleneck in Stockholm (MCS/TDIS data). Models must be trained and validated for the **morning peak, 07:30-08:30**. For example, at 07:02 you predict 07:02-07:17. Data before 07:30 may be used as input. The task text also mentions 30 and 60 minute horizons, but the core requirement is the 15-minute prediction.

### Data

- **Training data:** 2021-06-01 to 2021-12-31 (1-minute speed and flow per sensor). You choose the days and the split, and you may use only a subset.
- **Evaluation data:** 2022-01-01 to 2022-06-30. It must **not** be used in training, and final performance must be reported on the **complete** evaluation set.
- An optional all-day dataset (00:00-23:59) is available, but you are not limited to the morning peak.
- Features: DP_ID, PORTAL, Date, Time, Interval_1/5/15/30/60, SPEED_MS_AVG, FLOW.
- The dataset is not open-source. You may use it only in the course and **must not publish it** (e.g., on GitHub).

### Tasks

**A. Descriptive analysis**

- Analyze flow and speed patterns in time and space using descriptive statistics, graphs and histograms.

**B. Problem formulation**

- Decide what to predict (flow, speed, or both).
- Decide the problem type (clustering, regression, classification, or a combination).
- State a-priori hypotheses about which features matter for the 15, 30 and 60 minute horizons.
- Justify how reasonable and practical the formulation is for real-time use.

**C. Model development**

- **Preprocessing:** cleaning, normalization, encoding categorical variables, handling missing values and imputation. Investigate zeros and missing values in 1-minute data and justify whether to aggregate to 5 or 15 minutes.
- **Feature engineering:** time-based features, aggregations of historical data and other new features. Optionally, use clustering to group sensors, portals or days.
- **EDA:** relationships between variables, correlations, patterns and outliers.
- **Model selection:** conventional ML or deep neural networks, as suits the data.
- **Training:** train/validation split and hyperparameter tuning.
- **Evaluation:** use MAE, RMSE and MAPE. You must develop **at least three different types of models**, compare them, and select the best.

**D. Model diagnostics**

- Design scenarios to test how the best model behaves overall.
- Identify when and where it fails.
- Test robustness to noisy and missing data in real time.
- Test generalizability over months.

**E. Model deployment**

- State whether you would recommend the model to the agency.
- Reflect on what you learned.
- Propose an innovative way to operationalize it in practice.

**F. Report and code**

- Put commented code on **GitHub**, without the dataset.
- Save the best trained model as a **.keras** file.
- Submit a report addressing tasks A-E.

### Report Structure

1. Brief introduction and project objectives
2. Descriptive analysis
3. Model formulation
4. Model development
5. Model diagnostics
6. Model deployment
7. Summary of main findings and future work
8. GitHub code link

The report should include all model parameters and results, interpret them, and explain how you arrived at the best model.

### Grading

| Criterion                          | Weight |
| ---------------------------------- | ------ |
| Innovation idea                    | 20%    |
| Quality of analysis                | 30%    |
| Result explanations and discussion | 30%    |
| Report structure and writing       | 20%    |

Extra credit is given for high-quality analysis and writing in the style of a professional research paper. Always comment on your results, for example on which model performs better and why.