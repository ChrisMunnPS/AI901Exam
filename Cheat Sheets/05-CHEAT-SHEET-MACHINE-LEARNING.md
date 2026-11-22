# AI-901 cheat sheet 2/5 — Machine learning on Azure

*One page. Facts snapshot 2026-11; verify current behaviour on Microsoft Learn before the exam.*

## Features, labels, and data splits

| Term | Meaning | House-price example |
|---|---|---|
| **Feature** | An input variable the model uses. | Bedrooms, floor area, location |
| **Label** | The target the model predicts. | Selling price |
| **Training set** | Fits the model parameters. | Most of the history |
| **Validation set** | Tunes hyperparameters and compares candidates. | A held-out slice |
| **Test set** | Final, unbiased estimate on unseen data. | Touched once, at the end |

**Exam trap:** if you tune on the test set it becomes a validation set and the score is no longer clean. **Data leakage** — test rows inside training data — makes results look better than reality.

## Supervised vs unsupervised

| | Supervised | Unsupervised |
|---|---|---|
| **Training data** | Features **and** labels | Features only |
| **Goal** | Learn a mapping to a known target | Find structure or groups |
| **Tasks** | Classification, regression, forecasting | Clustering, anomaly detection |
| **Example** | Predict churn: yes or no | Segment customers by behaviour |

## Supervised tasks

| Task | Output | Example |
|---|---|---|
| **Binary classification** | One of two classes | Fraud / legitimate |
| **Multi-class classification** | One of three or more classes | Ticket category (5 options) |
| **Regression** | A continuous number | Price, temperature, duration |
| **Forecasting** | A future number from time-ordered data | Demand next quarter |

## Model evaluation

| Metric | Formula or meaning | Use it when |
|---|---|---|
| **Accuracy** | Correct predictions ÷ all predictions | Classes are balanced |
| **Precision** | TP ÷ (TP + FP) | False alarms are expensive |
| **Recall** | TP ÷ (TP + FN) | Missing a positive is expensive |
| **F1 score** | Harmonic mean of precision and recall | Imbalanced classes, both errors matter |
| **RMSE** | Root of the mean squared error, in target units | Large errors must be punished |
| **MAE** | Mean absolute error, in target units | Every error counts equally |

Confusion matrix: **TP** true positive, **TN** true negative, **FP** false positive, **FN** false negative.

| Situation | Error type | Metric to raise |
|---|---|---|
| Fraud is missed | False negative | Recall |
| Legitimate email marked spam | False positive | Precision |
| 95% of cases are negative, accuracy looks great | Majority-class shortcut | Recall and precision, not accuracy |

**Exam trap:** accuracy can be 95% while the model misses every positive case. Precision is about the quality of positive predictions; recall is about coverage.

## Overfitting and underfitting

| Symptom | Diagnosis | Remedy |
|---|---|---|
| Great on training data, poor on new data | **Overfitting** | More data, simpler model, regularisation, early stopping |
| Poor on training and test data | **Underfitting** | Richer model, better features, longer training |

## Azure Machine Learning

| Asset | Purpose |
|---|---|
| **Workspace** | Top-level container for experiments, data, compute, models, endpoints |
| **Compute instance** | Managed workstation for notebooks and interactive work |
| **Compute cluster** | Scalable multi-node compute for training; scales to zero when idle |
| **Datastore** | Connection details for Azure storage (Blob, Data Lake) |
| **Data asset** | Versioned reference to data used by experiments |
| **Environment** | Reproducible Python packages and dependencies |
| **Model registry** | Versions and tracks trained models |
| **Pipeline** | Repeatable steps: prepare, train, evaluate, deploy |
| **Designer** | Drag-and-drop canvas for building pipelines |
| **Automated ML (AutoML)** | Tries algorithms and hyperparameters, ranks by a primary metric |
| **Online endpoint** | Real-time REST predictions |
| **Batch endpoint** | Scheduled or on-demand scoring of large datasets |

**AutoML:** supports classification, regression, and forecasting. You choose a **primary metric** (accuracy, recall, RMSE) and it selects the best trial using that metric.

## Deployment and operations

| Need | Choose |
|---|---|
| Real-time prediction per request | Online endpoint |
| Overnight scoring of millions of rows | Batch endpoint |
| Explore algorithms without code | Automated ML |
| Build a pipeline visually | Designer |
| Reproduce and audit an experiment | Versioned data, code, and pipelines (MLOps) |
| Detect drift and quality loss after launch | Model monitoring |

**ML lifecycle:** collect → prepare → train → validate → test → deploy → monitor → retrain.

## Exam traps

- **Features go in, labels come out.** The price is the label; bedrooms are features.
- **A target column means supervised learning.** No target column means clustering or another unsupervised task.
- **Accuracy is not enough on imbalanced data.**
- **Validation guides choices; the test set reports the final score.**
- **Compute instance is for authoring; compute cluster is for scale-out training.**
- **AutoML is not a model type** — it is a search over algorithms and settings.
- **Azure Machine Learning trains custom models; Microsoft Foundry builds generative AI apps and agents.** They can be combined.
