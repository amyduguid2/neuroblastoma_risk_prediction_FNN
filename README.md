# Neuroblastoma Risk Prediction using a Feedforward Neural Network
This repository contains a Python notebook that implements a feedforward neural network to classify neuroblastoma patients as high risk or low risk. The model integrates multi-omics data and patient metadata, using RNA-Seq, microarray gene expression profiles, and clinical features to generate predictions.

## Usage

Clone the repository and run the main notebook 

git clone https://github.com/amyduguid2/neuroblastoma_risk_prediction_FNN.git

jupyter notebook Risk_Model.ipynb

## 🧠 Project Overview
The primary goal of this project is to develop a deep learning model that can accurately predict patient risk groups in neuroblastoma, a heterogeneous pediatric cancer. The pipeline includes preprocessing, feature selection, model training with cross-validation, and final predictions on previously unseen samples.

## Workflow

![Workflow_Diagram](Workflow/workflow.png).


## 📂   Data Sources
RNA-Seq data (fpkm)

Microarray data (intensities)

Patient metadata (age, sex)

These datasets were preprocessed and combined before model training.

## ⚙️ Workflow Summary
Data Preprocessing

Integration of RNA-Seq, microarray, and metadata features.

Normalization and cleanup steps.

## Feature Selection

Sequencing/microarray data is filtered using:

SelectKBest from sklearn

Followed by an autoencoder for dimensionality reduction

The top 50 features were selected from the latent space representations of autoencoders trained separately on microarray and RNA-Seq datasets. These features were then combined to form a unified feature set for downstream analysis.

## Model Architecture

A feedforward neural network built using TensorFlow

Binary classification output: High Risk vs Low Risk

## Cross-Validation

Model evaluation using 5-fold cross-validation to ensure generalisability.

Selection of the best-performing model based on model accuracy

Average accuracy across 5 folds was 95%

Precision, recall, F1-score and ROC curve also plotted in the notebook for 5 folds

## Prediction on Unlabeled Data

Final model is selected and used to generate predictions on unlabeled test data.

## 📊 Evaluation Metrics
Accuracy

Precision, Recall, F1-score

ROC-AUC Curve
