# Comparative Study of PCA and LDA

## Overview

This project presents a comparative study of **Principal Component Analysis (PCA)** and **Linear Discriminant Analysis (LDA)**, two linear methods used for dimensionality reduction with different objectives.

PCA identifies directions that preserve as much of the overall variance in the data as possible, without using class labels. LDA uses known class labels to identify directions that maximize class separation and can also be used as a classifier.

The methods are applied to the Breast Cancer Wisconsin (Diagnostic) dataset to explore their properties, visualize the data, and evaluate LDA classification performance.

## Objectives

- Understand the main principles and differences between PCA and LDA.
- Apply dimensionality reduction to a real-world dataset.
- Examine explained variance and the selection of principal components.
- Visualize class distributions in the reduced feature spaces.
- Evaluate LDA classification performance using multiple metrics and a confusion matrix.

## Dataset

The **Breast Cancer Wisconsin (Diagnostic)** dataset contains 569 samples, each described by 30 numerical features computed from digitized images of cell nuclei.

The samples belong to two diagnostic classes:

- **Benign:** 357 samples (62.7%)
- **Malignant:** 212 samples (37.3%)

The dataset is used to study dimensionality reduction and the separation of the two diagnostic classes.

## Methodology

### Principal Component Analysis (PCA)

PCA is applied to standardized features to reduce dimensionality while retaining as much total variance as possible.

The main steps in this report are:
1. Standardize the input features.
2. Compute the principal components.
3. Analyze the explained and cumulative explained variance.
4. Select the number of components needed to retain at least 95% of the total variance.
5. Visualize the samples using the first two principal components.

### Linear Discriminant Analysis (LDA)

LDA uses the known diagnostic labels to identify directions that maximize separation between classes relative to within-class variability.

This analysis includes:
1. Standardize the features.
2. Project the data onto the discriminant space.
3. Visualize the distributions of benign and malignant samples.
4. Train and evaluate an LDA classifier using an 80/20 stratified train-test split.
5. Examine classification metrics and the confusion matrix.

Since the dataset contains two classes, LDA produces at most one discriminant component.

## Results

### PCA

- The first principal component explains **44.27%** of the total variance.
- The first two principal components explain **63.24%**.
- Ten principal components retain **95.16%** of the total variance.
- Dimensionality is reduced from 30 features to 10 components, corresponding to a **66.7% reduction**.

The two-dimensional projection shows some separation between the diagnostic classes, but overlap remains. This illustrates that preserving overall variance does not necessarily maximize class separation.

### LDA

The projection onto the single discriminant component shows a clearer separation between the benign and malignant samples, although the distributions are not completely separated.

On the held-out test set of 114 samples, the LDA classifier achieves:

- **Accuracy:** 95.61%
- **Weighted F1-score:** 95.58%
- **Malignant-class recall:** 90.48%
- **Benign-class recall:** 98.61%

The confusion matrix shows that 109 of the 114 test samples are classified correctly. Four malignant samples are misclassified as benign, while one benign sample is misclassified as malignant.

These results highlight the importance of evaluating class-specific performance in addition to overall accuracy.

## PCA vs. LDA

| Aspect | PCA | LDA |
|---|---|---|
| Main objective | Preserve overall variance | Maximize class separation |
| Uses class labels | No | Yes |
| Dimensionality reduction | Yes | Yes |
| Classification | Can be combined with a separate classifier | Can also be used as a classifier |
| Typical applications | Data compression and visualization | Supervised dimensionality reduction and classification |

The appropriate method depends on the objective of the analysis and whether class labels are available.

## Tools and Technologies

- Python
- scikit-learn
- NumPy
- Matplotlib

## References

- scikit-learn documentation: [Principal Component Analysis (PCA)](https://scikit-learn.org/stable/modules/decomposition.html#pca)
- scikit-learn documentation: [Linear and Quadratic Discriminant Analysis](https://scikit-learn.org/stable/modules/lda_qda.html)
- UCI Machine Learning Repository: [Breast Cancer Wisconsin (Diagnostic) Dataset](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)

---
## 🎓 Academic Context & Author

This project was developed as part of the **“Fundamental Knowledge of Artificial Intelligence”** course within the **MSc in Artificial Intelligence** at the **University of Piraeus**, in collaboration with the **National Centre for Scientific Research “Demokritos” (NCSR Demokritos)**.

* **Author:** Agapi Kallinikou
* **Academic Year:** 2026 - 2027
