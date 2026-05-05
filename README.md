# 🏥 Healthcare Disease Prediction Pipeline

## 📌 Project Overview
An end-to-end Machine Learning pipeline designed to predict patient diseases based on symptoms, age, and gender. The project includes data preprocessing, exploratory data analysis (EDA), feature selection, and the implementation of multiple supervised and unsupervised machine learning algorithms, capped off with an interactive web UI.

## 🔬 Key Scientific Finding: Dataset Analysis
A major component of this project was evaluating the integrity of the provided `Healthcare.csv` dataset. Through rigorous mathematical evaluation across multiple models, **it was mathematically proven that the dataset is synthetic and randomly generated**, lacking real-world clinical correlations. 

**Proof of Synthetic Data:**
* **Classification Baseline:** With ~30 diseases, random guessing yields a ~3.33% accuracy. Our models (Decision Tree, Naive Bayes, MLP) all scored exactly at this baseline (~3.2% - 3.6%), proving the inability to find underlying patterns.
* **Regression Flatline:** Predicting symptom count based on age/gender yielded an $R^2$ score of `-0.0002` with near-zero coefficients, proving zero predictive power.
* **Clustering Overlap:** K-Means clustering resulted in a Silhouette Score of `0.12`, indicating highly overlapping clusters with no natural patient segmentation.

## ⚙️ Methodology & Pipeline
1. **Data Preprocessing:** Label encoding for categorical variables and binary dummy variable creation for symptoms.
2. **Feature Selection:** Applied **Chi-Square ($X^2$)** to identify the top 10 most statistically significant symptoms.
3. **Supervised Learning (Classification):** 
   * Decision Tree Classifier
   * Gaussian Naive Bayes
   * Neural Networks (Multi-Layer Perceptron)
4. **Unsupervised Learning (Clustering):**
   * K-Means Clustering (Validated with the Elbow Method and Silhouette Score).
5. **Regression Analysis:**
   * Linear Regression (Age & Gender vs. Symptom Count).

## 💻 Interactive UI
The project includes a dynamic, user-friendly interface built with **Gradio**. The UI automatically generates checkboxes for the most critical features identified during the Chi-Square test, translates user inputs into encoded formats, and returns the predicted disease in real-time.

## 🛠️ Technologies Used
* **Python**
* **Pandas & NumPy** (Data Manipulation)
* **Scikit-Learn** (Machine Learning Models & Preprocessing)
* **Matplotlib & Seaborn** (Data Visualization)
* **Gradio** (Web Interface Deployment)

## 🚀 How to Run Locally
1. Clone this repository.
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
3. Run the main script or Jupyter Notebook to execute the pipeline and launch the Gradio interface.
