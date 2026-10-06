# ⚙️ Motor Fault Diagnosis using Machine Learning

A research-oriented machine learning project focused on **motor fault diagnosis using Motor Current Signature Analysis (MCSA)**.

This repository combines three progressive Machine Learning assignments that explore different classical ML algorithms for identifying healthy and faulty motor conditions using electrical current signals.

The project includes implementations of:

- K-Nearest Neighbors (K-NN)
- Principal Component Analysis (PCA)
- Logistic Regression
- Naive Bayes
- Support Vector Machine (SVM)

A major focus of the work is implementing machine learning algorithms **from scratch**, comparing binary and multi-class fault classification, and studying the effect of dimensionality reduction and class-level performance.

---

## 📌 Project Overview

Industrial motors are widely used in manufacturing and automation systems.

Unexpected motor faults can lead to:

- Equipment failure
- Production downtime
- Maintenance costs
- Energy inefficiency
- Reduced equipment lifetime

Predictive maintenance aims to identify faults before complete failure occurs.

This project investigates whether electrical motor current signals can be used to distinguish healthy operation from different fault conditions using classical machine learning techniques.

---

## 🎯 Main Objectives

The main objectives of this project were to:

- Process motor current-signature data
- Convert raw signal sequences into machine-learning samples
- Perform binary motor health classification
- Perform multi-class motor fault classification
- Implement classical ML algorithms from scratch
- Evaluate classifier performance using multiple metrics
- Study the effect of dimensionality reduction
- Compare different approaches to motor fault diagnosis
- Understand challenges caused by class imbalance and overlapping fault signatures

---

## 🧠 Research Progression

The repository combines three related machine learning studies.

### Assignment 01 — K-NN and PCA

The first study investigates motor fault detection using:

- K-Nearest Neighbors
- Euclidean distance
- Manual K-NN implementation
- PCA dimensionality reduction
- Manual PCA using Singular Value Decomposition
- Binary classification

The original feature representation contains approximately:

**1000 features per sample**

PCA was used to reduce this representation to:

**100 features**

while attempting to preserve useful information for fault detection.

The recorded comparison showed:

| Metric | Original K-NN | PCA + K-NN |
|---|---:|---:|
| Feature Count | 1000 | 100 |
| Test Accuracy | 98.29% | 98.05% |
| Fault Recall | 33.33% | 35.09% |
| F1 Score | 0.4776 | 0.5000 |

Although overall accuracy decreased slightly after PCA, the reduced model improved fault recall and F1 score while using approximately **90% fewer features**.

This demonstrates why accuracy alone may not be sufficient when evaluating fault-detection systems.

---

## 🔍 Assignment 01 Evaluation

The K-NN study includes evaluation using:

- Confusion Matrix
- Accuracy
- Precision
- Recall
- F1 Score
- ROC Curve
- AUC
- Precision-Recall Curve
- Sensitivity
- Specificity

The value of K was evaluated before selecting the final neighborhood size.

---

## 📉 PCA Dimensionality Reduction

PCA was applied to investigate whether high-dimensional current-signal features could be compressed without significantly reducing classification performance.

The project uses a manual PCA implementation based on:

- Feature standardization
- Singular Value Decomposition
- Component selection
- Projection into a lower-dimensional feature space

The comparison demonstrates the trade-off between:

- Predictive performance
- Fault sensitivity
- Feature dimensionality
- Computational efficiency

---

## 📊 Assignment 02 — Logistic Regression

The second study extends motor fault diagnosis using a custom implementation of **Logistic Regression**.

Two classification scenarios are investigated:

### Binary Classification

The binary model distinguishes between:

- Healthy motor condition
- Faulty motor condition

A Logistic Regression classifier was implemented from scratch using:

- Sigmoid activation
- Iterative weight updates
- Numerical clipping for stable computation
- Manual standardization
- Probability-based prediction

---

### Multi-Class Classification

The study was then extended beyond healthy-versus-faulty classification.

The multi-class implementation attempts to distinguish between multiple motor operating and fault conditions.

A custom multi-class Logistic Regression framework was developed rather than relying entirely on a pre-built classifier.

This experiment demonstrates that detailed fault identification is more challenging than binary health detection because several fault conditions may produce similar current signatures.

---

## 📈 Logistic Regression Evaluation

The Logistic Regression experiments include visualizations and measurements such as:

- Confusion Matrix
- ROC Curves
- AUC
- Precision-Recall Curves
- Accuracy
- Precision
- Recall
- F1 Score
- Sensitivity
- Specificity
- Threshold-based performance analysis

For multi-class evaluation, class-level metrics are also calculated to better understand individual fault performance.

---

## 🧪 Assignment 03 — Naive Bayes and SVM

The third study compares two additional classical machine learning techniques:

- Naive Bayes
- Support Vector Machine

Both algorithms were implemented for motor fault diagnosis rather than simply applying a single library classifier.

---

## 🎲 Naive Bayes

A custom Naive Bayes implementation was developed for:

- Binary classification
- Multi-class classification

The model estimates class probabilities using statistical properties of the input features.

The study evaluates how a probabilistic classifier performs on high-dimensional motor current data.

---

## 📐 Support Vector Machine

A custom SVM implementation was also developed.

The SVM attempts to learn decision boundaries that separate healthy and faulty operating conditions.

The implementation includes iterative optimization and performance tracking during training.

Both binary and multi-class versions are explored.

---

## 📊 Assignment 03 Evaluation

Naive Bayes and SVM are evaluated using a broad set of visualizations.

These include:

- Confusion Matrices
- ROC Curves
- Precision-Recall Curves
- Training Accuracy Curves
- Validation Accuracy Curves
- Loss Curves
- Sensitivity-Specificity Trade-offs
- Final Metric Comparison Charts

The multi-class section extends these evaluations across several motor fault categories.

---

## ⚡ Motor Current Signature Analysis

Motor Current Signature Analysis is used to analyze electrical current measurements produced during motor operation.

Motor faults can affect patterns within these signals.

Instead of requiring physical inspection of the motor, current measurements can potentially provide useful information for condition monitoring.

The general workflow used in this project is:

**Motor Current Signals → Signal Segmentation → Feature Construction → Standardization → Machine Learning → Fault Classification**

---

## 🧩 Signal Segmentation

Raw motor current data is divided into fixed-length windows.

Each segment is transformed into a machine-learning sample containing approximately:

**1000 signal values**

along with its associated health or fault label.

This converts continuous signal measurements into structured tabular data suitable for machine learning.

---

## 🏷️ Classification Tasks

Two major forms of classification are studied.

### Binary Classification

The binary task simplifies motor condition monitoring into:

- Healthy
- Faulty

This is useful when the primary goal is determining whether maintenance may be required.

---

### Multi-Class Classification

The multi-class task attempts to distinguish specific operating and fault categories.

These can include different forms or severities of motor faults.

Multi-class diagnosis provides more detailed information but also creates a more difficult machine learning problem.

---

## 📏 Model Evaluation

Several evaluation metrics are used throughout the project.

### Accuracy

Measures the overall percentage of correctly classified samples.

---

### Precision

Measures how many predicted positive cases were actually positive.

---

### Recall / Sensitivity

Measures how effectively the model detects actual fault cases.

Recall is particularly important in predictive-maintenance applications because missing a real fault may be more costly than producing a false warning.

---

### F1 Score

Combines Precision and Recall into a single balanced metric.

---

### Specificity

Measures how effectively the model recognizes negative or healthy cases.

---

### ROC-AUC

ROC curves are used to evaluate classifier performance across different thresholds.

---

### Precision-Recall Analysis

Precision-Recall curves provide additional information when class distributions are imbalanced.

---

## 🔎 Why Accuracy Alone Is Not Enough

One important observation from the experiments is that very high overall accuracy does not automatically mean strong fault detection.

For example, the K-NN experiment achieved approximately **98% accuracy**, while fault recall was much lower.

This can occur when:

- Healthy samples dominate the dataset
- Fault samples are relatively rare
- Models become biased toward the majority class

Therefore, this project places additional emphasis on:

- Recall
- F1 Score
- Sensitivity
- Specificity
- Confusion matrices
- Class-level evaluation

---

## 🧱 Algorithms Implemented

The project investigates the following algorithms:

### K-Nearest Neighbors

Used for distance-based classification of motor current samples.

### Principal Component Analysis

Used for reducing high-dimensional signal features.

### Logistic Regression

Used as a linear probabilistic classifier for binary and multi-class fault diagnosis.

### Naive Bayes

Used as a probabilistic classifier based on feature distributions.

### Support Vector Machine

Used to learn decision boundaries between different motor conditions.

---

## 🧮 From-Scratch Implementations

A significant part of this project focuses on understanding the algorithms rather than treating them as black boxes.

Custom implementations include major elements of:

- K-NN
- PCA
- Logistic Regression
- Naive Bayes
- SVM

Library functions are mainly used for supporting tasks such as:

- Visualization
- Metric calculation
- Data manipulation
- Numerical operations

This approach helps demonstrate the mathematical and computational foundations of the algorithms.

---

## 📁 Repository Structure

Motor-Fault-Diagnosis-Machine-Learning/

├── notebooks/

│   ├── 01_knn_pca_motor_fault_diagnosis.ipynb

│   ├── 02_logistic_regression_motor_fault_diagnosis.ipynb

│   └── 03_naive_bayes_svm_motor_fault_diagnosis.ipynb

│

├── reports/

│   ├── assignment_01_knn_pca/

│   │   ├── report.tex

│   │   └── figures/

│   │

│   ├── assignment_02_logistic_regression/

│   │   ├── report.tex

│   │   └── figures/

│   │

│   └── assignment_03_naive_bayes_svm/

│       ├── report.tex

│       └── figures/

│

├── data/

│   └── README.md

│

├── requirements.txt

├── .gitignore

└── README.md

---

## 📓 Notebooks

### 01 — K-NN and PCA Motor Fault Diagnosis

**notebooks/01_knn_pca_motor_fault_diagnosis.ipynb**

Contains:

- Motor signal preprocessing
- Signal segmentation
- Binary label generation
- Manual K-NN
- Euclidean distance
- K optimization
- PCA using SVD
- Original vs PCA comparison
- Detailed fault-detection metrics

---

### 02 — Logistic Regression Motor Fault Diagnosis

**notebooks/02_logistic_regression_motor_fault_diagnosis.ipynb**

Contains:

- Dataset preparation
- Signal windowing
- Binary classification
- Multi-class classification
- Logistic Regression from scratch
- Sigmoid implementation
- Probability prediction
- Threshold analysis
- ROC analysis
- Precision-Recall analysis
- Class-level evaluation

---

### 03 — Naive Bayes and SVM Motor Fault Diagnosis

**notebooks/03_naive_bayes_svm_motor_fault_diagnosis.ipynb**

Contains:

- Binary motor fault classification
- Multi-class motor fault classification
- Naive Bayes from scratch
- SVM from scratch
- Training history tracking
- Confusion matrices
- ROC analysis
- Precision-Recall analysis
- Accuracy and loss curves
- Sensitivity-Specificity analysis
- Final metric comparison

---

## 📄 Research Reports

Each assignment also includes a research-style report containing:

- Problem introduction
- Algorithm background
- Mathematical concepts
- Methodology
- Experimental setup
- Visual results
- Performance analysis
- Discussion
- Conclusions

The reports are organized separately under the **reports/** directory.

---

## 📦 Python Libraries

The project mainly uses:

- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- tqdm
- Jupyter Notebook

Install the required packages using:

**pip install -r requirements.txt**

---

## 💾 Dataset

The original motor current-signature dataset is not included in this repository.

The notebooks expect externally available motor signal data.

Before running the notebooks:

1. Obtain the required motor current dataset.
2. Update the dataset path inside the notebooks.
3. Ensure the expected CSV structure matches the implementation.
4. Run the preprocessing sections before model training.

Large generated CSV files are also excluded from the repository.

---

## ▶️ How to Run

1. Clone or download the repository.
2. Install the required Python packages.
3. Obtain the motor current-signature dataset.
4. Update dataset paths inside the notebooks.
5. Open the notebooks using Jupyter Notebook, JupyterLab, or a compatible environment.
6. Run the experiments in numerical order.

Recommended order:

**01 K-NN + PCA → 02 Logistic Regression → 03 Naive Bayes + SVM**

---

## 🔬 Main Research Observations

The experiments highlight several important machine learning concepts.

### Dimensionality Reduction

PCA can substantially reduce the number of input features while retaining similar overall classification performance.

---

### Fault Recall Matters

In motor fault detection, identifying actual faults can be more important than maximizing overall accuracy.

---

### Binary Classification Is Simpler

Separating healthy and faulty motors is generally easier than determining the exact fault category.

---

### Multi-Class Diagnosis Is Challenging

Different motor faults may produce overlapping signal characteristics, making detailed fault classification more difficult.

---

### Class Imbalance Affects Evaluation

Large differences between accuracy and fault recall demonstrate why multiple metrics should be considered when evaluating industrial fault classifiers.

---

## 🏭 Practical Applications

Machine learning based motor fault diagnosis can potentially support:

- Predictive maintenance
- Industrial condition monitoring
- Smart manufacturing
- Machine health monitoring
- Early fault detection
- Reduced equipment downtime
- Automated maintenance systems

---

## 🚀 Future Improvements

Possible future extensions include:

- Better class balancing strategies
- SMOTE or other resampling techniques
- Cross-validation
- Hyperparameter optimization
- Feature extraction in the frequency domain
- FFT-based motor current analysis
- Wavelet-based features
- Random Forest comparison
- Gradient Boosting
- XGBoost
- Neural networks
- 1D CNN models for raw current signals
- LSTM-based temporal modeling
- Explainable AI techniques
- Real-time motor condition monitoring
- Deployment as a predictive-maintenance dashboard

---

## 🧠 Key Learning Outcomes

Through this project, I practiced:

- Machine learning from scratch
- Binary classification
- Multi-class classification
- High-dimensional data processing
- Signal segmentation
- Feature normalization
- Dimensionality reduction
- K-NN
- PCA
- Logistic Regression
- Naive Bayes
- Support Vector Machines
- Confusion matrix analysis
- ROC-AUC analysis
- Precision-Recall analysis
- Sensitivity and specificity
- Class imbalance analysis
- Research-oriented model comparison

---

## 🎓 Academic Context

This repository combines a series of **Machine Learning course assignments** focused on motor fault diagnosis.

Rather than presenting the assignments as unrelated exercises, the repository organizes them as a progressive study of classical machine learning approaches for industrial condition monitoring.

---

## 👩‍💻 Author

**Fatima Sohail**

BS Data Science  
GIFT University

---

## ⚠️ Note

This project was developed for academic and research-oriented learning purposes.

The models and results should not be treated as validated industrial diagnostic systems without additional testing, external validation, and evaluation under real operating conditions.

---

## ⭐ Support

If you find this project useful for learning machine learning, predictive maintenance, or motor fault diagnosis, consider giving the repository a ⭐.
