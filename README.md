# PySpark-Multi-Class-Network-Intrusion-Detection

Scalable machine-learning project for classifying network traffic using PySpark MLlib on a large multi-class cybersecurity dataset.

Overview

This project explores large-scale network intrusion detection using distributed machine-learning techniques in Apache Spark.

The pipeline processes approximately 2.52 million network records and uses 52 numerical features to classify traffic into 7 classes.

The project includes supervised learning, ensemble learning, dimensionality reduction, clustering, preprocessing, cross-validation, and model evaluation.

Project Goals

Build a scalable machine-learning pipeline using PySpark

Perform multi-class network traffic classification

Handle class imbalance

Compare tree-based models

Tune an ensemble model using cross-validation

Explore unsupervised structure using PCA and K-Means

Evaluate results using suitable classification and clustering metrics

Dataset

The project uses a large network-traffic dataset derived from cybersecurity traffic records.

Key characteristics:

Approximately 2.52 million records

52 numerical input features

7 traffic / attack classes

Multi-class classification problem

The raw dataset is not included in this repository because of its size.

Data Processing

The preprocessing workflow includes:

Data loading and schema inspection

Invalid-value handling

Missing-value processing

Median imputation

Numeric feature selection

Feature vector creation using VectorAssembler

Label preparation

Train / test splitting

Class weighting for imbalanced labels

Caching where useful for repeated Spark operations

Supervised Models

Decision Tree

A Decision Tree model was used as a baseline to provide an interpretable reference point.

Weighted Random Forest

A Random Forest model was trained with class weighting to improve performance across minority classes.

Hyperparameters were tuned using 3-fold cross-validation.

Unsupervised Learning

The project also includes:

PCA

Principal Component Analysis was used to reduce dimensionality before clustering.

K-Means

K-Means clustering was applied to explore whether natural groups in the feature space aligned with network traffic categories.

Cluster quality was assessed using silhouette analysis.

Machine-Learning Pipeline

Raw Network Data
        ↓
Cleaning / Validation
        ↓
Missing-Value Handling
        ↓
Median Imputation
        ↓
Feature Assembly
        ↓
Class Weighting
        ↓
Train / Test Split
        ↓
Decision Tree
        ↓
Weighted Random Forest
        ↓
Cross-Validation
        ↓
PCA
        ↓
K-Means
        ↓
Evaluation & Comparison

Evaluation

Classification models can be assessed using:

Accuracy

Precision

Recall

F1-score

Per-class performance

Confusion matrix

Clustering analysis includes:

Silhouette score

Cluster-size inspection

Comparison between clusters and known traffic labels

Technologies

Python

PySpark

Apache Spark

Spark MLlib

Random Forest

Decision Tree

PCA

K-Means

Cross-Validation

Big Data Processing

Cybersecurity Machine Learning

Repository Structure

pyspark-network-intrusion-detection/
│
├── README.md
├── src/
│   └── intrusion_detection.py
├── notebooks/           # Optional exploratory notebooks
├── docs/                # Report / figures
└── results/             # Metrics, plots, exported tables

How to Run

Install Java, Python, and Apache Spark / PySpark.

Place the dataset in a local data directory.

Update the dataset path in the script or notebook.

Start the PySpark environment.

Run the preprocessing pipeline.

Train and evaluate the classification models.

Run PCA and K-Means analysis.

Review exported metrics and visualisations.

Example environment setup:

pip install pyspark pandas matplotlib

Key Challenges

Processing millions of rows efficiently

Managing Spark transformations and actions

Handling class imbalance

Avoiding unnecessary recomputation

Selecting suitable evaluation metrics for multi-class classification

Comparing supervised and unsupervised methods on the same dataset

Future Improvements

Compare Logistic Regression and Gradient-Boosted models

Add more systematic hyperparameter tuning

Evaluate additional imbalance strategies

Add feature-importance analysis

Build a streaming intrusion-detection pipeline

Deploy the model using a REST API

Test distributed execution on cloud infrastructure

What I Learned

This project strengthened my understanding of:

Distributed data processing

PySpark DataFrame operations

MLlib pipelines

Multi-class classification

Ensemble learning

Cross-validation at scale

PCA and clustering

Working with large cybersecurity datasets

Author

Ali Shreif

Big Data / Machine Learning / Cybersecurity portfolio project.
