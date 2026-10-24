# Comparative Study of Machine Learning Models for Fake News Detection

## Overview

This project presents a comparative study of four machine learning algorithms for fake news detection using the **Indian Fake News Dataset (IFND)**.

The objective is to evaluate and compare the performance of different classification techniques in distinguishing genuine news from fake news using text-based features.

The study applies TF-IDF vectorization and Chi-Square feature selection before training and evaluating four machine learning classifiers. Their performance is compared using standard classification metrics, including accuracy, precision, recall, and F1-score.

This project is intended for educational and research purposes. It is an experimental study and is not intended to serve as a definitive fake news detection system or replace professional fact-checking.

## Dataset Credits

This project uses the **IFND (Indian Fake News Dataset)** for fake news detection. The dataset is not included in this repository. Please refer to the original source to access the dataset.

### Original Paper

Sharma, D. K., & Garg, S. (2023). *IFND: A benchmark dataset for fake news detection*. Complex & Intelligent Systems, 9, 2843–2863.

- **Research Paper:** https://doi.org/10.1007/s40747-021-00552-1
- **Dataset Source:** https://www.kaggle.com/datasets/sonalgarg174/ifnd-dataset

Please cite the original research paper when using the IFND dataset in your work.

### Dataset Usage Restrictions

According to the dataset providers, the IFND dataset is intended for **research purposes only**. This project uses the dataset for comparative model evaluation.

Users must comply with the dataset's original terms of use and citation requirements.

### Data Preprocessing

The following preprocessing steps are performed:

1. Load the dataset from the `IFND.csv` file.
2. Select the `Statement` and `Label` columns.
3. Remove records containing missing values in the selected columns.
4. Retain records with `TRUE` and `FAKE` labels.
5. Encode the labels as follows:
   - `TRUE` → `0`
   - `FAKE` → `1`
6. Split the data into training and testing sets using an 80:20 ratio, with stratified sampling.

## Methodology

The experimental workflow consists of the following stages:

1. **Dataset Loading:** Load the IFND dataset using Pandas.
2. **Data Cleaning:** Remove missing records and filter the relevant labels.
3. **Label Encoding:** Convert the target labels into numerical values.
4. **Train-Test Split:** Divide the dataset into 80% training data and 20% testing data.
5. **TF-IDF Vectorization:** Convert news statements into numerical representations using Term Frequency–Inverse Document Frequency.
6. **Feature Selection:** Apply the Chi-Square test to select informative features.
7. **Model Training:** Train four machine learning algorithms using the selected features.
8. **Performance Evaluation:** Compare the models using classification metrics and visualizations.

## Feature Extraction and Selection

### TF-IDF Vectorization

TF-IDF is used to transform text statements into numerical feature vectors. The implementation uses the following configuration:

- Maximum features: 5,000
- Stop words: English
- Input: News statements

The TF-IDF vectorizer is fitted on the training data and then applied to the testing data.

### Chi-Square Feature Selection

The Chi-Square test is applied using Scikit-learn's `SelectKBest` to select up to 2,000 informative features from the TF-IDF representation.

The feature selection process is fitted only on the training data, and the resulting transformation is applied to the testing data.

A visualization of the top 10 selected features by Chi-Square score is also generated.

## Machine Learning Algorithms

Four machine learning algorithms are evaluated in this study.

### 1. Multinomial Naive Bayes

A probabilistic classification algorithm commonly used for text classification. It estimates class probabilities based on the distribution of features.

### 2. Logistic Regression

A linear classification algorithm used to distinguish between the genuine and fake news classes.

### 3. Linear Support Vector Machine (Linear SVM)

A linear classifier that learns a decision boundary to separate the two classes.

### 4. K-Nearest Neighbors (KNN)

A distance-based classification algorithm that predicts a class based on the labels of nearby training examples. The implementation uses five neighbors and Euclidean distance.

## Evaluation Metrics

The models are evaluated using the following metrics:

- **Accuracy:** Measures the proportion of correctly classified statements.
- **Precision:** Measures the proportion of statements predicted as fake that are actually fake.
- **Recall:** Measures the proportion of actual fake statements correctly identified.
- **F1-score:** Represents the harmonic mean of precision and recall.

The implementation also generates classification reports for the individual models.

## Visualizations

The project includes the following visualizations:

- **Workflow Diagram:** Illustrates the overall fake news detection pipeline.
- **Dataset Description Table:** Summarizes the dataset variables, their purposes, and missing-value percentages.
- **Missing-Values Chart:** Shows the percentage of missing values in each dataset column.
- **Feature Selection Chart:** Displays the top 10 features ranked by Chi-Square scores.
- **Model Comparison Chart:** Compares accuracy, precision, recall, and F1-score across all four algorithms.
- **Confusion Matrix:** Visualizes the Naive Bayes model's classification results.

## Technologies Used

- **Python** — Programming language
- **Pandas** — Data loading and manipulation
- **NumPy** — Numerical operations
- **Matplotlib** — Data visualization
- **Seaborn** — Confusion matrix visualization
- **Scikit-learn** — Text vectorization, feature selection, model training, and evaluation
- **Google Colab** — Development and execution environment

## How to Run

1. Download the IFND dataset from https://www.kaggle.com/datasets/sonalgarg174/ifnd-dataset
2. Open the project notebook in Google Colab.
3. Run the upload cell and select the dataset file named `IFND.csv`.
4. Execute the notebook cells in sequence.
5. Review the evaluation metrics, model comparison table, and generated visualizations.

## Citation

The dataset providers request that users cite the following publications when using the IFND dataset.

1. Sharma, D. K., & Garg, S. (2021). IFND: A benchmark dataset for fake news detection. *Complex & Intelligent Systems*, 1–21. [https://doi.org/10.1007/s40747-021-00552-1](https://doi.org/10.1007/s40747-021-00552-1)

2. Garg, S., & Sharma, D. K. (2020, December). New Politifact: A Dataset for Counterfeit News. In *2020 9th International Conference System Modeling and Advancement in Research Trends (SMART)* (pp. 17–22). IEEE.

3. Garg, S., & Sharma, D. K. (2020, December). Phony News Detection using Machine Learning and Deep-Learning Techniques. In *2020 9th International Conference System Modeling and Advancement in Research Trends (SMART)* (pp. 27–32). IEEE.

4. Sharma, D. K., & Garg, S. (2021, July). Machine Learning Methods to identify Hindi Fake News within social-media. In *2021 12th International Conference on Computing Communication and Networking Technologies (ICCCNT)* (pp. 1–6). IEEE.

5. Sharma, Sunidhi, & Sharma, Dilip Kumar. (2019). Fake News Detection: A long way to go. In *2019 4th International Conference on Information Systems and Computer Networks (ISCON)*. IEEE.

6. Sharma, D. K., & Garg, S. (2021). A Framework for automatic fake content identification. In *1st International Conference on Simulation, Automation & Smart Manufacturing (SASM 2021)*, GLA University, India.

## Scope and Disclaimer

This project is an educational and research-oriented comparative study of machine learning algorithms for fake news detection using the IFND dataset.

**This project is intended for study and experimentation only. It is not intended to replace professional fact-checking, reliable journalism, or independent verification of information.**

The predictions generated by the models should not be treated as definitive judgments about the truthfulness of news statements. Machine learning classifiers can produce incorrect predictions, and their performance depends on the dataset, preprocessing methods, feature selection, and model configuration.

The results should be interpreted as experimental findings under the conditions of this study, rather than as evidence that any model can reliably determine the truthfulness of all news content.

The IFND dataset is not included in this repository and remains subject to its original usage terms. All credit for the dataset belongs to its original creators and the authors of the associated publications.
