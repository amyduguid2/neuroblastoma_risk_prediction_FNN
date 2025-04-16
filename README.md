Neuroblastoma Risk Prediction using a Feedforward Neural Network
This repository contains a Python notebook that implements a feedforward neural network to classify neuroblastoma patients as high risk or low risk. The model integrates multi-omics data and patient metadata, using RNA-Seq, microarray gene expression profiles, and clinical features to generate predictions.

🧠 Project Overview
The primary goal of this project is to develop a deep learning model that can accurately predict patient risk groups in neuroblastoma, a heterogeneous pediatric cancer. The pipeline includes preprocessing, feature selection, model training with cross-validation, and final predictions on previously unseen samples.

📂 Data Sources
RNA-Seq data (fpkm)

Microarray data (intensities)

Patient metadata (age, sex)

These datasets were preprocessed and combined before model training.

⚙️ Workflow Summary
Data Preprocessing

Integration of RNA-Seq, microarray, and metadata features.

Normalization and cleanup steps.

Feature Selection

Sequencing data is filtered using:

SelectKBest from sklearn

Followed by an autoencoder for dimensionality reduction

Model Architecture

A feedforward neural network built using TensorFlow

Binary classification output: High Risk vs Low Risk

Cross-Validation

Model evaluation using 5-fold cross-validation to ensure generalizability.

Selection of the best-performing model based on model accuracy

Average accuracy across 5 folds was 95%

Precision, recall, F1-score and ROC curve also plotted in the notebook for 5 folds

Prediction on Unlabeled Data

Final model is retrained on the full training set and used to generate predictions on unlabeled test data.

📊 Evaluation Metrics
Accuracy

Precision, Recall, F1-score

ROC-AUC Curve

📝 Usage
Clone the repository and run the notebook:

bash
Copy
Edit
git clone https://github.com/amy_duguid2/neuroblastoma_risk_prediction_FNN
jupyter notebook Risk_Model.ipynb
📁 File Structure
bash
Copy
Edit
├── Risk_Model.ipynb  			 # Main notebook
├── Data_Cleaning.ipynb                  # Data Cleaning notebook
├── cleaned_intensities.csv              # cleaned microarray data
├── output.csv                           # cleaned rna seq data
└── README.md                            # Project description
