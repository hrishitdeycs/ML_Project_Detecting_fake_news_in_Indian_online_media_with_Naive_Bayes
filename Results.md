# Fake News Detection — Results and Evaluation

## 1. Model Performance Comparison

Four machine learning models were evaluated using TF-IDF text features and Chi-Square feature selection on the IFND dataset.

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Naive Bayes | 93.64% | 93.89% | 86.57% | 90.08% |
| Logistic Regression | 94.35% | 97.46% | 85.28% | 90.96% |
| Linear SVM | **94.81%** | 96.40% | **87.71%** | **91.85%** |
| KNN | 90.06% | 94.03% | 74.97% | 83.42% |

## 2. Classification Reports

### 2.1 Naive Bayes

| Class | Precision | Recall | F1 Score | Support |
|---|---:|---:|---:|---:|
| Genuine (0) | 0.94 | 0.97 | 0.95 | 7,560 |
| Fake (1) | 0.94 | 0.87 | 0.90 | 3,783 |

**Accuracy:** 93.64%

### 2.2 Logistic Regression

| Class | Precision | Recall | F1 Score | Support |
|---|---:|---:|---:|---:|
| Genuine (0) | 0.93 | 0.99 | 0.96 | 7,560 |
| Fake (1) | 0.97 | 0.85 | 0.91 | 3,783 |

**Accuracy:** 94.35%

### 2.3 Linear SVM

| Class | Precision | Recall | F1 Score | Support |
|---|---:|---:|---:|---:|
| Genuine (0) | 0.94 | 0.98 | 0.96 | 7,560 |
| Fake (1) | 0.96 | 0.88 | 0.92 | 3,783 |

**Accuracy:** 94.81%

### 2.4 K-Nearest Neighbors (KNN)

| Class | Precision | Recall | F1 Score | Support |
|---|---:|---:|---:|---:|
| Genuine (0) | 0.89 | 0.98 | 0.93 | 7,560 |
| Fake (1) | 0.94 | 0.75 | 0.83 | 3,783 |

**Accuracy:** 90.06%

## 3. Confusion Matrix — Naive Bayes

The confusion matrix evaluates the performance of the Naive Bayes classifier on the test dataset.

| Actual / Predicted | Genuine (0) | Fake (1) |
|---|---:|---:|
| Genuine (0) | 7,347 | 213 |
| Fake (1) | 508 | 3,275 |

### Interpretation

- **True Negatives (TN): 7,347** — Genuine news statements correctly classified as genuine.
- **False Positives (FP): 213** — Genuine news statements incorrectly classified as fake.
- **False Negatives (FN): 508** — Fake news statements incorrectly classified as genuine.
- **True Positives (TP): 3,275** — Fake news statements correctly classified as fake.

The Naive Bayes classifier correctly classified 10,622 out of 11,343 statements, achieving an accuracy of approximately **93.64%**.

## 4. Evaluation Metrics

The following metrics were used to evaluate model performance:

- **Accuracy:** The proportion of all predictions that are correct.
- **Precision:** The proportion of statements predicted as fake that are actually labeled fake.
- **Recall:** The proportion of actual fake statements correctly identified by the model.
- **F1 Score:** The harmonic mean of precision and recall.

The positive class is `FAKE`, encoded as `1`, while `TRUE` or genuine news is encoded as `0`.

## 5. Results Analysis

Linear SVM achieved the highest overall accuracy of **94.81%** and the highest F1 score of **91.85%** among the four evaluated models. It also achieved the highest recall for the fake class at 87.71%.

Logistic Regression achieved the highest fake-class precision at **97.46%**, indicating that a high proportion of statements it predicted as fake were actually labeled fake in the test dataset.

Naive Bayes achieved an accuracy of 93.64%, demonstrating competitive performance. KNN recorded the lowest accuracy of 90.06% and the lowest fake-class recall of 74.97%.

Overall, Linear SVM provided the best balance of accuracy, recall, and F1 score among the evaluated models.

## 6. Conclusion

The experimental results show that TF-IDF text representation combined with Chi-Square feature selection can support effective fake news classification using traditional machine learning algorithms.

Among the evaluated models, **Linear SVM was the best-performing model**, achieving 94.81% accuracy and a 91.85% F1 score. Logistic Regression achieved the highest precision for the fake class, while Naive Bayes also delivered competitive results. KNN performed less effectively, particularly in identifying fake news statements.

These findings are based on the selected test split of the IFND dataset. Performance on new datasets, different sources, or more recent news claims may vary.
