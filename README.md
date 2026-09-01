# Predictive Threat Model

What It Does
This machine learning pipeline uses **TensorFlow**, **Pandas**, and **Scikit-Learn** to ingest network telemetry and classify traffic behavior as benign or malicious. It is designed to process real-world CSV datasets (such as firewall logs or intrusion detection datasets like CICIDS2017) dynamically. If no dataset is provided, it automatically generates and trains on a synthetic telemetry sample. 

## Features
- **Real Dataset Ingestion:** Dynamically parses external network telemetry CSV files, automatically identifying features and labels.
- **Automated Preprocessing:** Scales and normalizes variable network features (e.g., packet sizes, error rates) using `StandardScaler`.
- **Deep Neural Network:** Utilizes a Keras-based Sequential model with hidden `Dense` layers and `Dropout` regularization to prevent overfitting on complex multidimensional data.
- **Performance Metrics:** Evaluates and outputs test accuracy and binary cross-entropy loss against the provided network data.

## Why It Matters
Traditional signature-based defenses struggle to catch zero-day attacks and subtle behavioral anomalies. By training a neural network on historical network telemetry, security systems can predict and flag anomalous behaviors—such as slow data exfiltration or low-and-slow brute force attacks—that evade standard firewall rules.

## Use Cases
- **Alert Prioritization:** Feeding SIEM or IDS logs into the model to score and prioritize high-risk network events.
- **Threat Hunting Research:** Training the model on standardized datasets (like NSL-KDD) to experiment with behavioral anomaly detection.
- **AI/ML Integration:** Demonstrating the practical application of data science pipelines to solve infrastructure security challenges.

## Installation & Usage

Ingest and train on a real network telemetry dataset
python threat_model.py production_network_telemetry.csv

Run without a file to auto-generate and train on a synthetic dataset
python threat_model.py

**Prerequisites:**
```bash
pip install pandas scikit-learn tensorflow
