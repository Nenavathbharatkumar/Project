# Final Project README — NETFLIX Stock Price Prediction

## 1. Project Overview

This project develops and compares multiple machine learning models to predict Netflix (NFLX) stock closing prices. The goal is to identify a reliable and explainable model that can support stock-price analysis and demonstrate how predictive analytics can inform business decisions.

The project follows a reproducible workflow covering data preparation, chronological partitioning, preprocessing, model training, evaluation, business cost analysis, and final model selection.

## 2. Business Problem

Stock prices fluctuate over time, making accurate prediction challenging. This project investigates whether historical NFLX stock data can be used to predict the next day's closing price.

The project compares multiple predictive models and evaluates their performance using statistical error metrics and business-oriented cost analysis. The final recommendation considers predictive accuracy, explainability, and practical limitations.

## 3. Dataset

- **Dataset:** Netflix (NFLX) historical stock market data
- **Format:** CSV
- **Target variable:** `next_day_close`
- **Prediction task:** Regression
- **Data preparation:** Exclude nominal date fields from model predictors, sort records chronologically, and assign the prediction target.

Place the dataset in the documented project data folder, or follow the data-access instructions supplied with the project files.

If the dataset is not included in the repository, obtain it from the documented source and preserve the expected column names and structure.

## 4. Project Workflow

The modeling process consists of the following stages:

1. **Retrieve data:** Load the NFLX historical stock dataset.
2. **Select attributes:** Exclude nominal date fields from the predictor set.
3. **Sort chronologically:** Arrange records by date to preserve temporal order.
4. **Set the target:** Use `next_day_close` as the prediction target.
5. **Partition the data:** Divide observations chronologically into 60% training, 15% validation, and 15% test sets, as configured in the process.
6. **Preprocess each partition:** Handle missing values, generate derived attributes where configured, convert nominal attributes to numerical representations, and normalize numerical predictors.
7. **Train models:** Compare Linear Regression, Neural Network, Decision Tree, Random Forest, and Naive Bayes baseline configurations.
8. **Generate predictions:** Apply the trained models to the relevant evaluation records.
9. **Evaluate performance:** Calculate RMSE and compare prediction errors.
10. **Perform business analysis:** Evaluate directional dollar-cost implications using the configured asymmetric cost assumptions.
11. **Select the final model:** Use the leaderboard and the project's explainability and performance criteria to justify the recommendation.

**Important:** The workflow is configured for chronological evaluation. Preprocessing parameters, particularly normalization parameters, should be learned from training data and reused on validation and test data to reduce data leakage.

## 5. Models Compared

| Model | Purpose |
|---|---|
| Linear Regression | Provides an interpretable baseline and explainability reference. |
| Neural Network | Captures potentially nonlinear relationships in the data. |
| Decision Tree | Provides rule-based predictions that are relatively easy to interpret. |
| Random Forest | Combines multiple decision trees to model complex relationships. |
| Naive Bayes | Included as a baseline model for the configured tournament. Verify that its implementation and target handling are appropriate for regression before interpreting its results. |

The final model should be selected using the recorded experimental results rather than assumptions about which algorithm will perform best.

## 6. Evaluation Metrics

### Root Mean Squared Error (RMSE)

RMSE measures the typical magnitude of prediction errors while penalizing larger errors more heavily. Lower RMSE indicates better predictive accuracy on the same target scale.

### Directional Dollar-Cost Analysis

The workflow also examines prediction errors using asymmetric cost assumptions. The final report should explain how these costs are defined, how they are calculated, and what they mean for the business decision.

### Model Leaderboard

The leaderboard should report each model's test-set performance, RMSE, business-cost results, and explainability assessment. Include the actual measured results from the completed experiments; do not substitute illustrative or estimated values.

## 7. How to Run the Project

1. Install and open **Altair AI Studio**.
2. Place the NFLX CSV dataset in the documented data location.
3. Open the supplied `.rmp` process file.
4. Verify that the dataset location and required attributes match the available CSV file.
5. Inspect the preprocessing, partitioning, and model-training operators.
6. Run the process and review the model evaluation outputs.
7. Record the actual metrics and update the leaderboard.
8. Use the selected final model to score a new record and interpret the prediction in business terms.

The exact steps may vary depending on the Altair AI Studio version and the operators used in the supplied process.

## 8. Reproducibility and Data Leakage

The process file documents the main analytical workflow. Reproducibility requires access to the same dataset, compatible software, consistent parameter settings, and documented model configurations.

Chronological partitioning is used because randomly mixing historical stock observations can lead to an unrealistic evaluation of future predictions. Preprocessing must also respect partition boundaries: parameters learned from training data should not be independently fitted using validation or test data.

Before relying on the results, verify that the test set was not used for model selection or hyperparameter tuning.

## 9. Limitations

- Historical stock prices do not guarantee future performance.
- Market movements can be affected by news, economic conditions, company announcements, and other variables absent from the dataset.
- A low RMSE does not automatically translate into profitable trading decisions.
- Transaction costs, market impact, timing, and risk exposure may affect real-world outcomes.
- Model performance can change as market conditions evolve.
- Explainability and predictive accuracy must be considered alongside the project's intended use.

## 10. Responsible Use and Monitoring

The models are intended for educational and analytical purposes, not as guarantees of investment returns or personalized financial advice.

If deployed beyond the coursework, the model should be monitored for prediction errors, changes in data distributions, and deterioration in performance. Predictions should be reviewed alongside current market information, and any business decision should account for uncertainty and financial risk.

## 11. Project Deliverables

The complete portfolio package should include:

- **Process file:** The Altair AI Studio `.rmp` workflow.
- **Dataset or access instructions:** The CSV file, where redistribution is permitted, or clear instructions for obtaining it.
- **Annotated workflow:** A PDF or equivalent documentation explaining the process stages and operator connections.
- **Model leaderboard:** A plain table containing the actual model evaluation results.
- **Executive report:** Business problem, methodology, model tournament, evaluation, recommendation, monitoring plan, responsible-ML assessment, limitations, and next steps.
- **Recorded presentation:** A 10-minute presentation that includes a live demonstration of scoring a new record through the final process.
- **Methods and AI-use note:** A disclosure of tools and material AI assistance, along with a statement of responsibility for the modeling decisions.

## 12. Final Recommendation

The preferred model should be chosen after reviewing the completed leaderboard, validation results, test-set metrics, explainability requirements, and business-cost analysis. The recommendation should explain why the selected model is suitable for the stated problem, acknowledge its limitations, and identify how its performance would be monitored over time.

**Project status:** Update this README with the final selected model, measured evaluation results, dataset source, software version, and instructions specific to the completed workflow before submitting the portfolio.