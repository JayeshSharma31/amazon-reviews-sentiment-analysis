# 🛒 Amazon Food Reviews Sentiment Analysis

### End-to-End NLP & Machine Learning Project

An end-to-end Natural Language Processing project that analyzes Amazon food reviews and classifies customer sentiment as **Positive** or **Negative** using TF-IDF and machine learning.

The project covers the complete workflow from raw review data and text preprocessing to model comparison, error analysis, and prediction on unseen customer reviews.

---

## 📌 Project Overview

Customer reviews contain valuable information about customer satisfaction and product experience. However, manually analyzing thousands of reviews is time-consuming and difficult to scale.

This project builds an automated **sentiment classification pipeline** capable of transforming unstructured review text into structured sentiment information.

Three machine learning algorithms were evaluated:

- Logistic Regression
- Multinomial Naive Bayes
- Linear Support Vector Machine (Linear SVM)

Based on the evaluation results, **Linear SVM achieved the strongest Macro F1-score and was selected as the final model.**

---

## 🎯 Business Objective

The objective of this project is to use Natural Language Processing and Machine Learning to automatically identify whether a customer review expresses **positive or negative sentiment**.

Such a system can support businesses in:

- Monitoring customer feedback at scale
- Identifying negative customer experiences
- Prioritizing reviews that may require further investigation
- Understanding overall customer sentiment
- Reducing manual review analysis effort

---

## 📊 Dataset

The project uses the **Amazon Fine Food Reviews** dataset containing customer reviews and ratings for food products.

### Original Dataset

- **568,454 reviews**
- Customer review text
- Review summary
- Star rating
- Product and user information
- Helpfulness information

### Sentiment Definition

| Rating | Sentiment |
|---|---|
| 1–2 Stars | Negative |
| 3 Stars | Excluded |
| 4–5 Stars | Positive |

Three-star reviews were excluded to formulate the task as a **binary sentiment classification problem**.

> The complete dataset is not stored in this repository because of its size. Instructions for obtaining and placing the dataset are provided in the `data` directory.

---

## 🔄 Project Workflow

```text
Amazon Food Reviews
        │
        ▼
Data Quality Assessment
        │
        ▼
Data Cleaning
        │
        ▼
Sentiment Label Creation
        │
        ▼
NLP Text Preprocessing
        │
        ▼
Exploratory Text Analysis
        │
        ▼
Train / Test Split
        │
        ▼
TF-IDF Vectorization
        │
        ▼
Machine Learning Models
        │
        ├── Logistic Regression
        ├── Multinomial Naive Bayes
        └── Linear SVM
        │
        ▼
Model Evaluation & Comparison
        │
        ▼
Error Analysis
        │
        ▼
Sentiment Prediction
```

---

## 🧹 Text Preprocessing

The NLP preprocessing pipeline includes:

- Converting text to lowercase
- Removing HTML tags
- Removing URLs
- Removing unwanted characters
- Removing selected stopwords
- Preserving important negation terms
- Lemmatization
- Removing empty processed reviews

The cleaned text is then transformed into numerical features using **TF-IDF**.

---

## 🔢 Feature Engineering

Review text was converted into numerical features using:

**TF-IDF (Term Frequency–Inverse Document Frequency)**

The vectorizer considers both:

- **Unigrams** — individual words
- **Bigrams** — two-word combinations

A maximum of **50,000 TF-IDF features** was used.

Importantly, the TF-IDF vectorizer was fitted only on the **training data** to avoid data leakage.

---

## 🤖 Machine Learning Models

Three classification algorithms were compared using the same training and testing data.

| Model | Accuracy | Macro F1 |
|---|---:|---:|
| Logistic Regression | 91.59% | 0.8601 |
| Multinomial Naive Bayes | 91.37% | 0.7994 |
| **Linear SVM** | **92.47%** | **0.8686** |

### 🏆 Selected Model — Linear SVM

Linear SVM achieved the strongest Macro F1-score among the evaluated models and was therefore selected as the final classifier.

**Final Test Accuracy: 92.47%**

**Macro F1 Score: 0.8686**

---

## 📈 Final Model Performance

The final Linear SVM model demonstrated strong overall sentiment classification performance.

The project evaluates performance using more than accuracy alone because the sentiment classes are imbalanced.

Evaluation includes:

- Accuracy
- Precision
- Recall
- F1-score
- Macro F1-score
- Classification Report
- Confusion Matrix

---

## 🔍 Error Analysis

Incorrect predictions were examined after model evaluation.

The analysis considers:

- **False Positives:** Negative reviews predicted as positive
- **False Negatives:** Positive reviews predicted as negative

Reviewing misclassified examples helps identify situations where traditional TF-IDF-based models may struggle with complex or context-dependent language.

---

## 💬 Predicting New Reviews

The final pipeline can also classify previously unseen customer reviews.

Example:

```python
analyze_review(
    "The product was fresh, delicious and arrived on time. Highly recommended!"
)
```

Output:

```text
Predicted Sentiment: Positive
```

The prediction pipeline applies:

```text
New Review
    ↓
Text Preprocessing
    ↓
TF-IDF Transformation
    ↓
Linear SVM
    ↓
Positive / Negative
```

---

## 💼 Business Applications

An automated sentiment classification system can support:

**Customer Feedback Monitoring**  
Analyze large volumes of customer reviews automatically.

**Early Issue Detection**  
Surface negative customer feedback for further investigation.

**Customer Experience Analysis**  
Transform unstructured feedback into measurable sentiment information.

**Review Prioritization**  
Help teams identify dissatisfied customer feedback more efficiently.

**Large-Scale Review Analysis**  
Reduce the manual effort required to examine thousands of customer reviews.

---

## ⚠️ Limitations

- Sentiment labels are derived from star ratings rather than manually annotated sentiment.
- Three-star reviews are excluded from the binary classification task.
- TF-IDF has limited ability to capture deeper semantic context.
- Sarcasm, mixed sentiment and context-dependent language can be challenging.
- The model predicts overall review sentiment rather than sentiment toward individual product attributes.
- Performance may vary when applied to reviews from other domains.

---

## 🚀 Future Improvements

Future extensions could include:

- Hyperparameter tuning with cross-validation
- Additional n-gram experiments
- Deep learning models
- Transformer-based models such as BERT
- Aspect-based sentiment analysis
- Interactive Streamlit application
- Model deployment through an API

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- NLTK
- Scikit-learn
- TF-IDF
- Logistic Regression
- Multinomial Naive Bayes
- Linear SVM
- Jupyter Notebook

---

## 📁 Repository Structure

```text
amazon-reviews-sentiment-analysis/
│
├── Amazon_Reviews_Sentiment_Analysis.ipynb
├── README.md
├── requirements.txt
├── .gitignore
├── LICENSE
│
└── data/
    └── README.md
```

---

## ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/JayeshSharma31/amazon-reviews-sentiment-analysis.git
```

### 2. Move into the project directory

```bash
cd amazon-reviews-sentiment-analysis
```

### 3. Install the dependencies

```bash
pip install -r requirements.txt
```

### 4. Add the dataset

Place the Amazon Food Reviews CSV file inside:

```text
data/AmazonFoodReviews.csv
```

### 5. Run the notebook

Open:

```text
Amazon_Reviews_Sentiment_Analysis.ipynb
```

and execute the notebook cells sequentially.

---

## 👨‍💻 Author

**Jayesh Sharma**

Data Analytics | Data Science & Machine Learning | Generative AI

If you found this project useful, feel free to ⭐ the repository.
