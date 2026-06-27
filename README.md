# Sentiment Data Analysis: IMDB Movie Reviews

This repository focuses on Natural Language Processing (NLP) and sentiment analysis using the classic **IMDB Dataset of 50K Movie Reviews**. The goal of this project is to perform comprehensive exploratory data analysis (EDA), preprocess textual data, and build predictive models to classify movie reviews as either positive or negative.

---

## 🚀 Project Overview

The core of this project is hosted and developed via a Kaggle notebook pipeline (`nlp-dataset-analysis.ipynb`). It explores various NLP techniques to handle text classification at scale. 

### Key Highlights:
*   **Dataset:** IMDB 50K Movie Reviews (binary sentiment classification).
*   **Environment:** Developed using Kaggle Notebooks and synced directly via GitHub integration.
*   **Core Tasks:** Text cleaning, tokenization, Exploratory Data Analysis (EDA), feature extraction (TF-IDF/Embeddings), and model building.

---

## 📊 Dataset Description

The dataset used is the **IMDB Dataset of 50K Movie Reviews**, which consists of highly polar movie reviews for binary sentiment classification. 
*   **Total Rows:** 50,000 reviews
*   **Columns:** 
    *   `review`: The textual body of the movie review.
    *   `sentiment`: The target label (`positive` or `negative`).

---

## 🛠️ Repository Structure

```text
├── .github/          # GitHub configuration files
├── README.md         # Project documentation (this file)
└── nlp-dataset-analysis.ipynb  # Core Jupyter notebook containing the analysis

⚙️ Installation & Setup
To run this notebook locally, ensure you have Python installed, clone the repository, and install the required dependencies.

Clone the repository:

Bash
git clone [https://github.com/mondalabhi/sentiment-data-analysis.git](https://github.com/mondalabhi/sentiment-data-analysis.git)
cd sentiment-data-analysis
Install dependencies:
Make sure to install common NLP and data science libraries:

git clone [https://github.com/mondalabhi/sentiment-data-analysis.git](https://github.com/mondalabhi/sentiment-data-analysis.git)
cd sentiment-data-analysis

📈 Roadmap & Core Workflow
The notebook follows a standard NLP pipeline:

Exploratory Data Analysis (EDA): Checking class distributions, analyzing review lengths, and creating word clouds for positive vs. negative reviews.

Text Preprocessing:

Removing HTML tags (common in IMDB scraps).

Removing emojis, punctuation, and special characters.

Lowercasing text.

Stopword removal and Lemmatization/Stemming.

Vectorization: Transforming text data into numerical format using techniques like Bag-of-Words or TF-IDF.

Model Training: Training traditional Machine Learning classifiers (e.g., Logistic Regression, Naive Bayes, Linear SVM) or Deep Learning models.

Evaluation: Measuring success via Accuracy, Precision, Recall, and F1-Score metrics.

🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the issues page if you want to contribute to enhancing the preprocessing pipeline or adding advanced transformer models (like BERT).
