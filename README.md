# Exploring-Missing-Data-Imputation
Missing Data & Imputation: Does Made-up Data Work?

## Project Rundown
One of the biggest challenges in data science is handling missing data, as it can lead to biased models and reduced accuracy. This project explores whether imputation techniques—which estimate missing values based on existing patterns—can effectively substitute for real data while maintaining model performance.

Using the Credit Approval dataset, we apply Decision Tree models to evaluate the impact of imputation. The dataset consists of 15 predictor variables (A1 - A15) and a binary response variable (A16), indicating whether a credit application is approved (+) or not (-). To protect confidentiality, the variable names and values have been anonymized.

We compare two models:

1. Reduced Model – trained on complete cases only (excluding missing data).
2. Imputed Model – trained on data with missing values filled using the missRanger Random Forest-based imputation method.
   
## Key Takeaways

🔹 Overall Accuracy Remains Similar (~87%)

- Both models perform nearly identically in terms of overall predictive accuracy.
  

🔹 Imputation Improves Sensitivity (~93% vs. 86%)

- The imputed model is better at identifying negative instances (- class).
- Suggests imputation helps the model capture more patterns from previously missing data.


🔹 Imputation Reduces Specificity (~78-80% vs. 86-89%)

- The reduced model performs better at identifying positive instances (+ class).
- Imputation may introduce noise or overfitting, making it harder to correctly classify + cases.


🔹 Minimal Missingness (0.6%) → Limited Impact of Imputation

- Since missing data is low, excluding incomplete cases still preserves most of the dataset.
- The reduced model maintains comparable performance with a simpler structure.


🔹 When is Imputation More Useful?

- If a large proportion of data were missing, dropping incomplete cases could significantly reduce the dataset and introduce bias.
- In such cases, imputation would help retain more information and improve model robustness.


## Final Verdict

For this dataset (with only 0.6% missing values), imputation is not necessary—the reduced model performs just as well while maintaining simplicity. However, for datasets with higher missingness, imputation would likely be more beneficial.
