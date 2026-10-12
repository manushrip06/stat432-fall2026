---
name: stat432-lda-qda-analysis
description: Runs an LDA/QDA classification workflow with cross-validation and a one-page report. Use only when the user explicitly invokes this skill and supplies the dataset, response, and predictors.
disable-model-invocation: true
---

# STAT 432 LDA/QDA Analysis

## Intent

Guide a reproducible discriminant-analysis study using only LDA, QDA, or combinations of their class-probability outputs. Produce a concise one-page report with one figure, one table, and numerical fit results.

## When to use

Apply this skill only when the student explicitly names `stat432-lda-qda-analysis` or asks you to use this LDA/QDA analysis skill. The student must supply:

- dataset (file path or loaded table)
- response column or vector (binary or multiclass labels)
- predictor columns or matrix (numeric)
- random seed (optional; ask if missing)

Do not assume variable names, class labels, or expected performance.

## Analysis workflow

1. **Split first.** Hold out a test set (default 30%) with stratification when possible. Fix the split with the stated seed. Never use the test set for model or preprocessing choices.

2. **Define candidates.** Compare at minimum:
   - ordinary LDA (shared covariance)
   - ordinary QDA (class-specific covariances)
   Optional extensions allowed by this skill:
   - PCA embedding + LDA or QDA (number of components chosen by CV)
   - blended classifier: average or weighted average of LDA and QDA predicted class probabilities, then classify by largest blended probability

3. **Cross-validate on training only.** Use one fixed fold scheme (default: 10-fold stratified). Within each fold:
   - fit preprocessing (standardization, PCA, etc.) on training folds only
   - fit each candidate on preprocessed training folds
   - record validation misclassification rate
   Summarize mean CV error (and SD if helpful) per candidate. Select the best candidate by lowest mean CV misclassification rate.

4. **Final fit and test evaluation.** Refit preprocessing and the selected candidate on all training data. Evaluate once on the held-out test set. Report test misclassification rate and a confusion matrix.

5. **Keep classifiers in scope.** Do not use logistic regression, trees, SVM, or neural networks. Only LDA, QDA, PCA variants of these, or probability blends of LDA and QDA.

## Required one-page report

Fit on one printed page (~400–500 words plus one figure and one table):

| Section | Content |
|---------|---------|
| Setup | Sample size, number of predictors, train/test split, seed, response definition |
| Candidates | Brief description of each model compared |
| Cross-validation | Fold scheme, metric (misclassification rate), CV results table |
| Selection | Chosen model and why (CV performance) |
| Test results | Test misclassification rate, key numerical outputs (priors, dimensions, tuning choices) |
| Figure | One plot (e.g., CV error by candidate, or 2D score/PC scatter with classes) |
| Findings | Main conclusion and one limitation |

## Figure and table rules

- **Table:** CV misclassification rates for all candidates (mean ± SD across folds).
- **Figure:** One clear plot supporting model comparison or class separation; label axes; readable font size.
- **Numbers:** Report seed, test error, selected model name, and at least one fitted statistic (e.g., estimated priors or number of PCA components).

## Rules

- Do not peek at the test set until the final evaluation step.
- Do not embed dataset-specific names or expected results in this skill.
- If the report exceeds one page, shorten prose before removing the required figure or table.
- State which Python/R functions were used for LDA and QDA.
