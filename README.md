# UAV-Anomaly-Detection-TCN-A

## Attention-based Temporal Convolutional Network (TCN-A) for Multiclass UAV Anomaly Detection

This repository contains the implementation of an **Attention-based Temporal Convolutional Network (TCN-A)** for multiclass anomaly detection in Unmanned Aerial Vehicle (UAV) telemetry data.

The proposed model combines **Temporal Convolutional Networks (TCNs)** with an **attention mechanism** to effectively capture both temporal dependencies and the most informative features from UAV sensor data. The implementation is developed in TensorFlow/Keras and evaluated using five-fold cross-validation.

---

## Repository Contents

```
UAV-Anomaly-Detection-TCN-A
│
├── 01_GPS_TCN_A.ipynb
├── 02_IMU_TCN_A.ipynb
├── 03_RATE_TCN_A.ipynb
├── 04_VIBE_TCN_A.ipynb
│
├── README.md
└── requirements.txt
```

Each notebook implements the complete workflow for one UAV telemetry source.

| Notebook            | Description            |
| ------------------- | ---------------------- |
| 01_GPS_TCN_A.ipynb  | GPS anomaly detection  |
| 02_IMU_TCN_A.ipynb  | IMU anomaly detection  |
| 03_RATE_TCN_A.ipynb | RATE anomaly detection |
| 04_VIBE_TCN_A.ipynb | VIBE anomaly detection |

---

## Dataset

The experiments use the **TLM UAV Anomaly Detection Dataset**, generated using the ArduPilot Software-In-The-Loop (SITL) simulator.

The repository evaluates four telemetry streams independently:

* GPS
* IMU
* RATE
* VIBE

The dataset contains five operating conditions:

* Normal
* GPS Failure
* Accelerometer Failure
* Engine Failure
* RC Failure

**Dataset source**
uav-autonomous-navigation-dataset

---

## Proposed TCN-A Architecture

The proposed network consists of:

* Sliding window preprocessing
* Feature standardization using StandardScaler
* Three Temporal Convolutional Network (TCN) blocks
* Dilated causal convolutions
* Batch Normalization
* ReLU activation
* Custom Attention Layer
* Softmax classifier
* Adam optimizer
* Five-fold cross-validation

The attention mechanism enables the model to emphasize the most informative temporal features, improving multiclass UAV anomaly classification.

---

## Preprocessing

The following preprocessing steps are applied:

* Removal of redundant label columns
* Label encoding
* Feature normalization using StandardScaler
* One-hot encoding of class labels
* Sliding window generation (window size = 5)

---

## Model Training

Training configuration:

* Framework: TensorFlow / Keras
* Optimizer: Adam
* Learning Rate: 0.001
* Epochs: 50
* Batch Size: 32
* Cross Validation: 5-Fold

---

## Evaluation Metrics

The notebooks evaluate the model using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* Per-class Accuracy
* Prediction Distribution
* Misclassified Sample Analysis
* Correctly Classified Sample Analysis

---

## Generated Outputs

The notebooks automatically generate:

* Classification Report
* Confusion Matrix
* Label Distribution
* Predicted Label Distribution
* Misclassified Samples (CSV)
* Correctly Classified Samples (CSV)

---

## Requirements

The implementation uses:

* TensorFlow
* NumPy
* Pandas
* Scikit-learn
* Matplotlib
* Seaborn

See `requirements.txt` for package versions.

---

## Citation

If you use this implementation in your research, please cite the associated publication.

```
@article{
  title={Attention-based Temporal Convolutional Network for Multiclass UAV Anomaly Detection},
  author={Sangeeta Oswal et al.},
  journal={Under Review},
  year={2026}
}
```

The citation will be updated once the paper is published.

---

## License

This repository is intended for academic and research purposes.

---

## Contact

** Sangeeta Oswal**

Assistant Professor

Department of Artificial Intelligence and Data Science

For questions related to the implementation, please open an issue in this repository.
