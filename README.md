# Comparing Classifiers: Bank Marketing Campaign

## Summary
This project analyzes a dataset from a Portuguese banking institution containing 41,188 records from multiple telephone marketing campaigns. The goal is to predict whether a client will subscribe to a term deposit product (yes/no) and compare the performance of four classification models.

## Link to Notebook
[prompt_III.ipynb](prompt_III.ipynb)

## Business Problem
The bank wants to improve the efficiency of their telephone marketing campaigns by identifying which customers are most likely to subscribe to a term deposit. Currently only 11.27%  of contacted customers subscribe, making most calls wasteful.

## Key Findings

### Model Comparison (Default Settings)
| Model | Train Time | Train Accuracy | Test Accuracy |
|---|---|---|---|
| Logistic Regression | 0.49s | 89.99% | 90.09% |
| KNN | 0.11s | 91.22% | 89.72% |
| Decision Tree | 0.45s | 99.54% | 84.18% |
| SVM | 165.62s | 90.50% | 90.35% |

### Tuned Model Comparison
| Model | Test Accuracy | Recall (Yes) | Precision (Yes) |
|---|---|---|---|
| Logistic Regression | 90.08% | 21.88% | 68.81% |
| KNN | 87.87% | 31.90% | 44.65% |
| Decision Tree | 90.25% | 24.89% | 68.55% |
| SVM | 89.66% | 26.94% | 58.96% |

## Best Model
**KNN with n_neighbors=3 and distance weighting** was selected as the best model because it achieved the highest recall of 31.90% — correctly identifying 296 out of 928 actual subscribers in the test set.

Recall was chosen as the primary metric because missing a potential subscriber (false negative) is more costly to the bank than calling a non-subscriber (false positive).

## Recommendations
1. Use KNN model to prioritize calling lists and focus  on high probability subscribers
2. Do not rely on accuracy alone — recall is the more  meaningful metric for this imbalanced problem
3. Collect more data on subscribers to improve model performance
4. Consider optimal timing of calls based on month and day of week features

## Next Steps
- Try resampling techniques like SMOTE to handle class imbalance
- Explore ensemble methods in future modules
- Test the model on new campaign data before deploying

## Files
- `prompt_III.ipynb` — Full analysis notebook
- `data/bank-additional-full.csv` — Dataset

## Tools Used
- Python, Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn (KNN, Logistic Regression, Decision Tree, 
  SVM, GridSearchCV, Pipeline)
