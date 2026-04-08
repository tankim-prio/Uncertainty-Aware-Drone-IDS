# ISOT Drone Anomaly Detection Dataset (Preprocessed)

This folder contains the data pipeline and access instructions for the dataset used in this research.

## Original Data Source
The foundation of this project is the **ISOT Drone Anomaly Detection Dataset**, originally published by the Information Security and Object Technology (ISOT) Research Lab. It captures extensive Wi-Fi network telemetry for both benign drone communication patterns and malicious cyberattack scenarios.
* **Official Source:** [ISOT Drone Datasets (UVic)](https://onlineacademiccommunity.uvic.ca/isot/2024/12/05/drone-datasets/)

## Advanced Preprocessing: `updated_drone_ids_dataset.csv`
To ensure seamless reproducibility and to respect the time of reviewers and researchers, I have engineered a fully preprocessed, machine-learning-ready version of the original ISOT dataset, finalized as `updated_drone_ids_dataset.csv`.

Rather than working with raw, unstructured telemetry, this customized dataset has already undergone the rigorous ML-pipeline detailed in the main research paper:
* **Leakage-Safe Chronological Split:** Sorted strictly by time to prevent temporal target leakage (a critical flaw often overlooked in cybersecurity ML).
* **Cross-Split Duplicate Hashing:** Purged identical network packets that overlap between the training and testing phases to ensure true generalization.
* **Feature Hardening:** Over-predictive network artifacts (features with an AUC > 0.85) were deliberately dropped. This forces the federated models to learn true structural anomalies rather than memorizing easily spoofed shortcuts.
* **Non-IID Partitioning:** Specifically formatted to integrate perfectly with the 10-client feature-skew federated topology.

## Download Instructions
Due to GitHub's file size limitations, `updated_drone_ids_dataset.csv` is securely hosted on Google Drive.

**[Click Here to Download: updated_drone_ids_dataset.csv](https://drive.google.com/file/d/1vnk18Sr-Y29aHIVLVfTIlYBvwQNhSiFC/view?usp=drive_link)**

### How to implement it in this repository:
1. Download the preprocessed file using the secure link above.
2. Place `updated_drone_ids_dataset.csv` directly into this `data/` directory.
3. The main Jupyter Notebook located in the `code/` folder is pre-configured to automatically load the data from this exact location for immediate execution!
