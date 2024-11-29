# URL Classification Project

### **Authors**:  
- James Rivera  
- Agustin Lorenzo  

---

## **Project Overview**

This project focuses on building machine learning models to classify URLs as either **phishing** (Bad) or **safe** (Good). Phishing URLs are designed to deceive users into providing sensitive information, such as passwords or credit card details. By leveraging various machine learning techniques, including **Logistic Regression**, **Single-Layer Perceptron Neural Networks**,**Multi Layer Preceptron neural Networks**, **Deep Neural Networks** and **Naive Bayes**, this project aims to identify effective methods for detecting phishing URLs.

---

## **Objectives**
1. Develop models to classify URLs as "good" or "bad."
2. Compare the performance of:
   - Logistic Regression
   - Single-Layer Perceptron (SLP) Neural Network
   - Multi-Layer Perceptron (MLP) Neural Network
   - Deep Neural Network
   - Naive Bayes Classifier
3. Evaluate model performance using metrics like **accuracy**, **F1-score**, and **ROC-AUC**.

---

## **Dataset**
- **Name**: `phishing_site_urls.csv`
- **Description**: Contains labeled URLs classified as either "good" (safe) or "bad" (phishing).
- **Columns**:
  - `URL`: The website URL to be classified.
  - `Label`: The classification label (`good` or `bad`).

---

## **Features**
The models utilize the following features:
1. **URL Length**: The length of the URL string.
2. **Contains HTTPS**: Whether the URL includes the "https" protocol (binary: 1 if true, 0 otherwise).
3. **Number of Special Characters**: The count of special characters in the URL (e.g., `!@#$%^&*()`).
4. **Tokenized Text Features**: For the Naive Bayes model, tokenized words from URLs are vectorized using `CountVectorizer`.

---

## **Models**
### **1. Logistic Regression**
- Uses numerical features (e.g., URL length, HTTPS presence) to classify URLs.
- **Implementation**:
  - Preprocessed features are standardized using `StandardScaler`.
  - Model trained using `sklearn.linear_model.LogisticRegression`.
- **Performance Metric**: Accuracy calculated over 15 iterations with randomized train-test splits.

### **2. Single-Layer Perceptron Neural Network**
- A simple neural network with no hidden layers:
  - Input: Numerical features.
  - Output: Binary classification using a sigmoid activation function.
- **Implementation**:
  - Built and trained using `TensorFlow/Keras`.
  - Performance evaluated over multiple randomized train-test splits.

### **3. Naive Bayes Classifier**
- Tokenizes URLs into words and uses `CountVectorizer` for vectorization.
- **Implementation**:
  - Built using `sklearn.naive_bayes.MultinomialNB`.
  - Accuracy recorded over 15 iterations.

---

## **Results**
Performance metrics for each model are saved in the following CSV files:
- `LogisticRegressionResults.csv`: Accuracies from 15 iterations of logistic regression.
- `SLPResults.csv`: Accuracies from 15 iterations of the single-layer perceptron neural network.
- `NBResults.csv`: Accuracies from 15 iterations of the Naive Bayes classifier.

---

## **Installation**
### **1. Clone the Repository**
```bash
git clone https://github.com/your-repo-name/url-classification.git
cd url-classification
