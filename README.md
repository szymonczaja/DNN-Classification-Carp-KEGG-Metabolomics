# 🧬 Carp Classification Based on KEGG Metabolic Pathways (DNN)

## 📝 Project Summary

This academic project, developed during my **Bioinformatics** studies, focused on the **classification (prediction)** of common carp originating from **five different ponds** that received varying nutritional supplementation. The classification was performed solely using data related to the **activity of KEGG metabolic pathways**.

The primary goal was to leverage a **Deep Neural Network (DNN)** to identify metabolic patterns, while critically evaluating model performance given the complexity and size of the biological dataset.

### Unique Project Aspects:
* Integration of biological data (KEGG pathways) with advanced Deep Learning techniques.
* Handling multi-class classification ($N=5$) in a Bioinformatics context.
* **Dimensionality Reduction** addressing the $N \ll p$ problem (fewer samples than features).
* Application of **Permutation Feature Importance (PFI)** for model explainability.

---

## 🛠️ Technologies Used

The analysis was executed in a **Jupyter Notebook** environment using **Python** and key data science libraries.

<p align="center">
  <img src="https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/-Keras-D00000?style=flat&logo=keras&logoColor=white">
  <img src="https://img.shields.io/badge/-TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white">
  <img src="https://img.shields.io/badge/-scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/-Pandas-150458?style=flat&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/-NumPy-013243?style=flat&logo=numpy&logoColor=white">
  <img src="https://img.shields.io/badge/-SciPy-82B0D9?style=flat&logo=scipy&logoColor=white">
  <img src="https://img.shields.io/badge/-Jupyter-F37626?style=flat&logo=jupyter&logoColor=white">
</p>

---

## ⚙️ Analytical Methodology

### 1. KEGG Data Preprocessing and Dimensionality Reduction
* The initial dataset presented the challenge of having a significantly higher number of features than samples ($p \gg N$), requiring a robust preprocessing pipeline.
* **Correlation Feature Selection:** Features with high correlation (Pearson correlation $> 0.9$) were addressed by removing the variable with the **lower variance**.
* **Principal Component Analysis (PCA):** Final dimensionality reduction was achieved using **PCA** to find an optimal number of components for modeling, preserving maximum variance while mitigating the $p \gg N$ issue.
* The data was then scaled and normalized for optimal neural network training.

### 2. Deep Neural Network (DNN) Architecture
* A multi-layer DNN model was built using **Keras/TensorFlow** with **ReLU activation** in hidden layers and **Softmax activation** for the five-class output.
* Despite hyperparameter tuning, the model performance was **moderate**, indicating inherent complexity or limitations within the data structure.

### 3. Model Evaluation and Interpretation
* **Evaluation Metrics:** Model performance was assessed using **Accuracy**, **Loss**, and a detailed **Confusion Matrix**.
* **Model Explainability (PFI):** **Permutation Feature Importance (PFI)** was utilized to identify the most influential KEGG pathways driving the classification decisions.

---

## 📊 Key Findings

This research successfully addressed the complexity of classifying high-dimensional biological data through a necessary and stringent preprocessing pipeline. However, the overall model performance was **moderate** (highest accuracy observed was approximately **0.76**), and the DNN exhibited signs of **overfitting** during training. This suggests that while the model captured complex patterns, its ability to generalize to unseen metabolic profiles was limited, possibly due to the dataset size.

Despite the moderate performance, the **PFI analysis** provided essential biological interpretability. PFI successfully identified a focused subset of KEGG metabolic pathways as the primary drivers of classification decisions. This offers valuable insights into which biological processes were most affected by the different carp treatments, thereby providing a clear direction for future targeted research.
