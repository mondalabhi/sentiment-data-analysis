# 🎬 Sentiment & NLP Analysis of IMDB Movie Reviews

A comprehensive, end-to-end Natural Language Processing (NLP) and Sentiment Analysis pipeline implemented in Python. This project loads the popular IMDB Movie Reviews dataset, performs advanced text cleaning and preprocessing (including parallelized spelling correction), conducts Exploratory Data Analysis (EDA) with rich visualizations, and reduces high-dimensional vector representations to a 2D space using PCA.

---

## 📌 Project Overview

This project implements a structured NLP pipeline designed to clean, preprocess, analyze, and visualize textual data. Starting with raw movie reviews, the pipeline processes the text through various NLP techniques to prepare it for machine learning tasks. 

### 🔄 The NLP Pipeline

```mermaid
graph TD
    A[Raw IMDB Reviews] --> B[Data Cleaning]
    B --> C[Text Preprocessing]
    C --> D[EDA & Visualizations]
    D --> E[Vectorization (BOW)]
    E --> F[Dimensionality Reduction (PCA)]
    F --> G[Sentiment Scatter Plot]
```

---
## 🛠️ Pipeline Details

The implementation is broken down into five main steps:

### 1. Data Cleaning
Raw text from movie reviews is cleaned to remove noise and standardize the format:
- **Duplicate Removal**: Identifies and drops duplicate reviews.
- **Normalisation**: Converts all text to lowercase and strips leading/trailing whitespaces.
- **HTML & URL Removal**: Regular expressions remove markup tags (e.g., `<br>`) and web links (`http/www`).
- **Abbreviation Expansion**: Standardizes common contractions (e.g., `he's` to `he is`, `won't` to `will not`).
- **Spelling Correction**: Fixes typos using the `autocorrect` library.
- **Punctuation & Special Characters**: Clears non-alphanumeric noise using custom filters.

> [!TIP]
> **Performance Optimization:** Spelling correction and stopword removal can be CPU-intensive. This project leverages `pandarallel` to parallelize Pandas operations across multiple CPU cores, significantly speeding up execution times.

### 2. Preprocessing
Prepares the cleaned text for vectorization:
- **Tokenization**: Splits text into word tokens using NLTK's `word_tokenize`.
- **Stopwords Removal**: Filters out common English stopwords (e.g., "the", "is", "at") to highlight meaningful words.

### 3. Exploratory Data Analysis (EDA)
Inspects the features of the text data and visualizes differences in sentiment class distributions:
- **Word & Character Counts**: Computes total word and character lengths for positive vs. negative reviews.
- **Distribution Plots**: Uses `seaborn.displot` to compare text lengths and word counts between sentiments.
- **N-Gram Analysis**: Extracts and counts the most frequent Bigrams (2-grams) and Trigrams (3-grams) using NLTK.
- **Word Clouds**: Generates word clouds (for positive vs. negative reviews) using `wordcloud` to visually capture dominant themes.

### 4. Vectorization
Transforms textual data into numerical representation:
- **Bag of Words (BOW)**: Uses `CountVectorizer` with a 2-gram range (`ngram_range=(2,2)`) and limits the vocabulary to the top 10,000 features (`max_features=10000`).

### 5. Dimensionality Reduction (PCA)
- **Principal Component Analysis (PCA)**: Projects the sparse 10,000-dimensional BOW matrix down to a 2D space.
- **Visual Analytics**: Visualizes the 2D document embeddings on a Seaborn scatter plot colored by their sentiment labels (Positive/Negative).

---

## 🚀 Getting Started

### 📋 Prerequisites

Ensure you have Python 3.8+ installed.

### ⚙️ Installation

1. **Clone this repository** (or navigate to your workspace directory):
   ```bash
   git clone <repository-url>
   cd sentiment-data-analysis
   ```

2. **Install the required packages**:
   ```bash
   pip install pandas numpy nltk scikit-learn wordcloud matplotlib seaborn autocorrect pandarallel
   ```

3. **Download NLTK Data**:
   Ensure you have the required NLTK resources downloaded. Run the following in Python:
   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('stopwords')
   ```

### 🏃 Running the Notebook

Start the Jupyter environment and run the cells sequentially:
```bash
jupyter notebook nlp-dataset-analysis.ipynb
```

---

## 📊 Sample Visualizations

The notebook saves and generates visualizations, including:
- **Word Clouds**: Saved as `wordcloud.png` for positive and negative review sentiments.
- **PCA Scatter Plot**: Shows how positive and negative sentiments cluster after dimensionality reduction.

---

## 🗺️ Future Enhancements
- [ ] Implement **Stemming** (PorterStemmer) and **Lemmatization** (WordNetLemmatizer) to group word inflections.
- [ ] Implement **POS Tagging** (Parts of Speech) to capture syntactic structure.
- [ ] Train Classification Models (e.g., Logistic Regression, Naive Bayes, or XGBoost) on vectorized text to predict sentiment.
- [ ] Explore **TF-IDF Vectorization** and Word Embeddings (e.g., Word2Vec, GloVe, or BERT).

---
*Developed as part of Sentiment Data Analysis.*
