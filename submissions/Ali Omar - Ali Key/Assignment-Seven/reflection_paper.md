# 📧 Spam Detection using Machine Learning
### Reflection Paper – Part B  
**Author:** Ali Omar Abdi  
**Project Type:** Machine Learning – Text Classification  

---

## 🧠 Overview

This project focuses on building a **Spam Detection System** that can automatically identify whether a text message is **Spam** or **Ham** (not spam).  
To achieve this, three machine learning models were trained and compared:

1. **Logistic Regression (LR)**  
2. **Random Forest Classifier (RF)**  
3. **Multinomial Naive Bayes (NB)**  

The comparison is based on several evaluation metrics, including **Accuracy**, **Precision**, **Recall**, **F1-Score**, and **Confusion Matrix**.  
Each model’s strengths and weaknesses are discussed in detail below.

---

## ⚙️ Step-by-Step Implementation

### **1. Data Preparation**
- **Dataset Used:** `mail_l7_dataset.csv`  
- The dataset contained thousands of text messages labeled as either **Spam (0)** or **Ham (1)**.  
- Data cleaning included:
  - Removing duplicates and missing values.  
  - Converting all text to lowercase.  
  - Encoding labels (Spam → 0, Ham → 1).

### **2. Text Feature Extraction**
- Used **TF-IDF Vectorization (Term Frequency–Inverse Document Frequency)** to convert messages into numerical values.  
- This technique measures how important a word is in a message relative to all messages in the dataset.  
- Common stop words like “the”, “is”, and “and” were removed to focus on meaningful words.

### **3. Model Training**
Each model was trained using **80% of the data** and tested on the remaining **20%**:

| Model | Description |
|:------|:-------------|
| **Logistic Regression** | Linear classifier that separates spam and ham messages using a weighted decision boundary. |
| **Random Forest Classifier** | Ensemble model that combines multiple decision trees to improve prediction accuracy. |
| **Multinomial Naive Bayes** | Probabilistic model that calculates the likelihood of a message being spam based on word frequency. |

---

## 📊 Model Results and Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|:------|:---------:|:----------:|:-------:|:---------:|
| **Logistic Regression** | 0.968 | 1.000 | 0.758 | 0.863 |
| **Random Forest** | **0.983** | **1.000** | **0.872** | **0.932** |
| **Naive Bayes** | 0.977 | 1.000 | 0.826 | 0.904 |

### 🔍 Key Observations
- All models achieved **perfect precision (1.000)** — none falsely labeled good messages as spam.  
- **Random Forest** achieved the **highest accuracy and recall**, meaning it caught more spam without errors.  
- **Naive Bayes** performed very well and was the fastest to train, but slightly less accurate.  
- **Logistic Regression** was reliable but missed more spam messages compared to the others.

---

## 🧩 Confusion Matrix Analysis

| Model | True Positives (Spam) | True Negatives (Ham) | False Positives | False Negatives |
|:------|:---------------------:|:--------------------:|:---------------:|:----------------:|
| Logistic Regression | 163 | 1019 | 0 | 36 |
| Random Forest | **180** | **1019** | **0** | **19** |
| Naive Bayes | 173 | 1019 | 0 | 26 |

### ✅ Interpretation:
- **True Positives (TP):** Correctly identified spam messages.  
- **True Negatives (TN):** Correctly identified ham (normal) messages.  
- **False Positives (FP):** Normal messages incorrectly marked as spam.  
- **False Negatives (FN):** Spam messages that were missed and marked as ham.  

> In spam detection, **False Negatives** are the biggest issue — missed spam messages can reach users’ inboxes.  
> **Random Forest** had the fewest false negatives, making it the most dependable choice.

---

## 💡 Understanding Naive Bayes

### 📘 What is Naive Bayes?
Naive Bayes is a simple yet powerful algorithm based on **Bayes’ theorem**.  
It calculates the probability that a message belongs to a certain class (Spam or Ham) based on the presence of specific words.  

It’s called “naive” because it assumes all words are independent of each other — which is not entirely true, but this simplification makes it very fast and effective for text classification.

### ⚙️ Why It’s Used in Spam Detection
- Works perfectly with **word-frequency data** like TF-IDF.  
- **Very fast and lightweight**, suitable for real-time email filtering.  
- Performs surprisingly well even with small datasets.

### 👍 Advantages
- Simple and easy to train.  
- Excellent performance on text classification tasks.  
- Requires very little computational power.

### ⚠️ Limitations
- The assumption of word independence is unrealistic in natural language.  
- Struggles with new or unseen words.  
- Can be outperformed by ensemble models like Random Forest in complex datasets.

---

## 📈 Metrics Discussion

| Metric | What It Measures | Ideal Outcome |
|:-------|:----------------:|:--------------|
| **Accuracy** | How often the model is correct overall. | High (close to 1.0) |
| **Precision** | How many messages marked as spam were actually spam. | High precision = fewer false positives |
| **Recall** | How many spam messages were correctly detected. | High recall = fewer missed spam |
| **F1-Score** | Balance between precision and recall. | High F1 = balanced performance |
| **Confusion Matrix** | Detailed breakdown of correct and incorrect predictions. | Low false negatives preferred |

👉 From these metrics, **Random Forest** clearly performed best overall.

---

## 🧾 Sanity Check Messages

| Test Message | Expected Result | Logistic Regression | Random Forest | Naive Bayes |
|:--------------|:----------------|:--------------------:|:--------------:|:-------------:|
| “Hey, how are you?” | Ham | ✅ Ham | ✅ Ham | ✅ Ham |
| “Congratulations! You won a free prize, click here!” | Spam | ❌ Ham | ✅ Spam | ✅ Spam |
| “Meeting at 10 AM tomorrow.” | Ham | ✅ Ham | ✅ Ham | ✅ Ham |

✅ **Conclusion:** Random Forest and Naive Bayes handled keyword-based spam better than Logistic Regression.

---

## 🧭 Findings and Recommendation

After testing and analyzing all three models, here are the conclusions:

- **Naive Bayes:** Fast and efficient, best for quick text classification.
- **Logistic Regression:** Stable and interpretable, but slightly less sensitive to spam cues.
- **Random Forest:** Most accurate and dependable overall.

### 🏆 Recommended Model: **Random Forest Classifier**
It provides:
- The **highest accuracy (0.983)** and **F1-score (0.932)**  
- **Perfect precision** (no false positives)  
- **Fewest false negatives**, catching more spam messages  

> Therefore, **Random Forest** is the best model for real-world spam detection systems, balancing speed, precision, and reliability.

---

## 🧮 Tools and Libraries Used
- **Python**  
- **NumPy**, **Pandas** – Data analysis and handling  
- **Scikit-learn** – Machine learning algorithms and metrics  
- **TF-IDF Vectorizer** – Feature extraction from text  

---

## 💻 How to Run the Project

```bash
# 1. Install dependencies
pip install numpy pandas scikit-learn

# 2. Run the notebook or script
python spam_detection.py
# or open spam_detection.ipynb in Jupyter Notebook