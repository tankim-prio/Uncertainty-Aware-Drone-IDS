# ISOT Drone Anomaly Detection Dataset (Preprocessed)

This folder contains the data pipeline and access instructions for the dataset used in this research. The foundation of this project is the **ISOT Drone Anomaly Detection Dataset**, which captures extensive Wi-Fi network telemetry for both benign and malicious drone swarm activities.

## Data Preprocessing: `updated_drone_ids_dataset.csv`
To ensure seamless reproducibility and save reviewers time, I have engineered a fully preprocessed version of the original ISOT dataset, finalized as `updated_drone_ids_dataset.csv`. 

Rather than working with raw, messy telemetry, this dataset has already undergone the rigorous ML-pipeline detailed in the main research paper:
* **Leakage-Safe Chronological Split:** Sorted strictly by time to prevent temporal target leakage (a common flaw in cybersecurity ML).
* **Cross-Split Duplicate Hashing:** Purged identical packets that overlap between training and testing phases.
* **Feature Hardening:** Over-predictive network artifacts (features with AUC > 0.85) were deliberately dropped to force the model to learn structural anomalies rather than memorizing easy shortcuts.
* **Non-IID Partitioning:** Formatted to perfectly integrate with the 10-client feature-skew federated topology.

## Download Instructions
Due to GitHub's file size limits, `updated_drone_ids_dataset.csv` is securely hosted on Google Drive.

**[Click Here to Download: updated_drone_ids_dataset.csv](https://drive.google.com/file/d/1vnk18Sr-Y29aHIVLVfTIlYBvwQNhSiFC/view?usp=drive_link)**

### How to use it:
1. Download the file using the link above.
2. Place `updated_drone_ids_dataset.csv` directly into this `01_Dataset/` directory.
3. The main Jupyter Notebook in `03_Codebase/` is pre-configured to load the data automatically from this location!
