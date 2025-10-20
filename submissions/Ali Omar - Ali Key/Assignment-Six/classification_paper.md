# Machine Learning Classification Assignment

**Author:** Ali Omar Abdi  
**Course:** Data Science & Machine Learning Bootcamp  
**Topic:** Classification Algorithms and Evaluation Metrics  

---

## 1. Introduction to Classification

In Machine Learning, **classification** is a supervised learning method used to predict **categories or classes** based on input features.  
For example, we can train a model to predict whether an email is *spam* or *not spam*.

Classification is **different from regression**, which predicts continuous numerical values.  
Regression answers “*How much?*” or “*How many?*” while classification answers “*Which category?*”.

- **Example of Classification:** Predicting whether a transaction is *fraudulent* or *legitimate*.  
- **Example of Regression:** Predicting the *price of a used car* based on its mileage and age.

---

## 2A. Classification Algorithms

### a) Logistic Regression

**How it works:**  
Logistic Regression predicts probabilities using a mathematical function called the **sigmoid function**.  
It outputs values between 0 and 1, which are then converted into class labels (e.g., 0 = “No”, 1 = “Yes”).

**Real-world use case:**  
Predicting whether a patient has diabetes (Yes/No) using health indicators like glucose level and BMI.

**Advantages:**
- Simple and easy to interpret  
- Works well with smaller datasets  

**Limitations:**
- Assumes a linear relationship between inputs and outputs  
- Not suitable for complex or non-linear problems  

---

### b) Decision Trees

**How it works:**  
Decision Trees split data into branches using conditions based on feature values.  
Each split helps the model make a decision, and the final leaf node gives the predicted class.

**Real-world use case:**  
Predicting whether a customer will buy a new phone plan based on age, income, and usage pattern.

**Advantages:**
- Easy to visualize and explain  
- Works with both numerical and categorical data  

**Limitations:**
- Can easily overfit the data if not controlled  
- Sensitive to small changes in the dataset  

---

### c) Random Forest

**How it works:**  
A Random Forest combines many Decision Trees to form a **stronger ensemble model**.  
Each tree makes a prediction, and the final result is based on the majority vote from all trees.

**Real-world use case:**  
Detecting fake reviews on e-commerce platforms like Amazon or Jumia.

**Advantages:**
- High accuracy  
- Reduces overfitting  
- Works well with large datasets  

**Limitations:**
- Slower to train compared to a single tree  
- Harder to interpret  

---

## 2B. Extended Task – Another Algorithm: K-Nearest Neighbors (KNN)

**What it solves:**  
KNN is used for **pattern recognition** and **recommendation systems**. It works well when similar data points tend to belong to the same class.

**How it works:**  
When a new input is given, KNN looks at its **‘K’ closest neighbors** in the dataset and assigns the most common class among them.

**Real-world use case:**  
A movie recommendation system that suggests films based on what similar users liked.

**Strengths:**
- Very simple to understand and implement  
- Works well for small datasets  

**Weaknesses:**
- Slow for large datasets  
- Affected by irrelevant or unscaled features  

**Comparison to Other Algorithms:**  
Unlike Logistic Regression or Decision Trees, KNN does not build a model during training.  
It classifies data based on **similarity** between examples.

---

## 3. Classification Metrics

### **Accuracy**
Measures the percentage of correct predictions out of all predictions.  
\[
Accuracy = \frac{Correct\ Predictions}{Total\ Predictions}
\]

### **Precision**
Measures how many of the predicted positive results were actually positive.  
Useful when false positives are costly (e.g., in fraud detection).

### **Recall**
Measures how many actual positive cases were correctly identified.  
Useful when missing positive cases is dangerous (e.g., in medical diagnosis).

### **F1-Score**
Combines **Precision** and **Recall** into one metric for balanced evaluation.  
Best for imbalanced datasets.

### **Confusion Matrix**
A table showing the number of **true positives**, **true negatives**, **false positives**, and **false negatives**.  
It helps you understand the types of errors your model makes.

---

### Comparison Table

| Metric | What It Measures | Best Used For | Weakness |
|--------|------------------|---------------|-----------|
| **Accuracy** | Overall correctness | Balanced datasets | Misleading for imbalanced data |
| **Precision** | Correct positive predictions | When false positives are costly | Ignores missed positives |
| **Recall** | How many real positives were found | When false negatives are costly | Ignores false positives |
| **F1-Score** | Balance of precision and recall | Imbalanced datasets | Harder to interpret |
| **Confusion Matrix** | Full error breakdown | Always useful | Needs manual analysis |

---

## 4. Imbalanced Data Problem

**Imbalanced data** happens when one class has many more examples than the other.  
For example, in a fraud detection dataset, 98% of transactions might be legitimate and only 2% fraudulent.

In this case, **accuracy is misleading** — a model predicting all transactions as “legitimate” would still be 98% accurate but completely useless.

**Better metrics for imbalanced data:**
- **Precision, Recall, and F1-Score** – focus on the minority (important) class.  
- **ROC-AUC Score** – measures the ability to distinguish between classes.

---

## 5. Real-World Case Study: Heart Disease Prediction

**Goal:**  
To predict whether a person has heart disease using medical data.

**Dataset Used:**  
*Cleveland Heart Disease Dataset* from the UCI Machine Learning Repository.

**Model Used:**  
Random Forest Classifier – chosen for its accuracy and ability to handle complex data.

**Key Results:**  
- Accuracy: **89%**  
- F1-Score: **0.87**  
- Most important features: **age**, **cholesterol**, **chest pain type**

**Insights:**  
The model helps doctors identify high-risk patients early, improving diagnosis and treatment plans.

---

## References

1. Scikit-learn Documentation – [https://scikit-learn.org](https://scikit-learn.org)  
2. UCI Machine Learning Repository – Heart Disease Dataset  
3. Jason Brownlee, *Machine Learning Mastery with Python*, 2023  
4. Kaggle – Heart Disease Prediction Dataset  

---

**End of Assignment**
