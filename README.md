#Genetic Variant Impact Classifier for Rare Diseases

This project builds a machine learning classifier to predict whether a genetic variant is benign or pathogenic using variant_summary.txt.gz data.

1. Dataset

We use a subset of columns:

Chromosome

Start

ReferenceAllele

AlternateAllele

ClinSigSimple (0 = benign, 1 = pathogenic)

GeneSymbol

PhenotypeList

2. Steps to Run

Install dependencies

pip install pandas scikit-learn xgboost

Load and preprocess data

Load variant_summary.txt.gz with pandas

Drop rows with missing ClinSigSimple

Split into training and testing sets

Use ColumnTransformer to apply:

SimpleImputer for numeric columns

One-hot encoding for categorical columns

Train the model

We use XGBClassifier inside a Pipeline for preprocessing and classification.

Evaluate

We measure performance with:

Accuracy

Cross-validation log loss

esting on a Example

Troubleshooting

If benign variants are predicted as pathogenic:

Check if training data is imbalanced.

Add more relevant features.

Try class weighting or oversampling.

Author: Ali Jawad
Purpose: Educational project on genetic variant classification
