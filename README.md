# **Classifying Phishing URLs**

This project is focused on identifying phishing websites by analyzing their URLs. Various machine learning models are employed to determine the effectiveness of different approaches in detecting phishing websites.

by James Rivera and Agustin Lorenzo

---

## **Project Overview**

Phishing websites aim to deceive users into revealing sensitive information such as login credentials or financial details. This project uses machine learning models to classify URLs as either **phishing** or **non-phishing**.

### **Goals**:
- Build and compare machine learning models.
- Analyze the contribution of different features to classification accuracy.
- Save results from each model for comparison.

---

## **Features**

Each URL is analyzed to extract the following features:

1. **HTTPS Presence**: Whether the URL uses HTTPS (`1` if present, `0` otherwise).
2. **URL Length**: The total number of characters in the URL.
3. **Special Character Length**: The number of special characters in the URL.
4. **Number of Dots**: The count of `.` characters.
5. **Number of Slashes**: The count of `/` characters.
6. **Total Special Characters**: Sum of occurrences of specific special characters (`!@#$%^&*()-=`).
7. **Domain Type**:
   - Common domains like `.com`, `.org`, `.net`, `.me`.
   - Other domains are categorized separately.
8. **Group Features**:
   - **Mean URL Length by Domain**: Average URL length for each domain type.
   - **Deviation from Mean URL Length**: Difference between a URL's length and the average length for its domain.

---

## **Models**

The following models are implemented to classify URLs:

### **1. Logistic Regression**
- Simple linear classifier.
- Used as a baseline to compare against other models.

### **2. Naive Bayes**
- Probabilistic model based on Bayes' theorem.
- Assumes feature independence.

### **3. Single-Layer Perceptron (SLP)**
- Neural network with a single hidden layer.
- Sigmoid activation for binary classification.

### **4. Multi-Layer Perceptron (MLP)**
- Neural network with 2 hidden layers, each containing 10 nodes.
- Uses ReLU activation for hidden layers and sigmoid for output.

### **5. Deep Neural Network (DNN)**
- Neural network with 10 hidden layers, each containing 30 nodes.
- Designed for more complex patterns in the data.

---

Each model was implemented using either **Scikit-learn** (for logistic regression and Naive Bayes) or **PyTorch** (for SLP, MLP, and DNN). The neural networks are trained for 5 epochs with a batch size of 16.
## **Dataset**
---

The dataset contains URLs labeled as either:
- **Good**: Non-phishing URLs.
- **Bad**: Phishing URLs.

The dataset is preprocessed to extract features for training and testing the models. It is stored as a CSV file: `phishing_site_urls.csv`.

---

## **How to Run**

### **Prerequisites**
- Python 3.7–3.10
- Libraries:
  ```bash
  pip install numpy pandas scikit-learn torch
