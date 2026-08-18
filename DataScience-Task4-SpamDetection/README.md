# 📧 Task 4: Email & SMS Spam Detection with Machine Learning

## 📌 Internship Task Overview
- **Objective**: Build a Natural Language Processing (NLP) binary classifier that distinguishes Spam messages from Legitimate (Ham) emails/messages.
- **Location**: C:\\Users\\hp\\Desktop\\Qiyas\\OASIS\\Task_4_Email_Spam_Detection\\
- **Primary Deliverable**: [Task_4_Email_Spam_Detection.ipynb](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_4_Email_Spam_Detection/Task_4_Email_Spam_Detection.ipynb) (Fully Executed Jupyter Notebook)

---

## 📋 Feature Checklist Verification
- [x] **Dataset Sourcing**: Downloaded UCI / Kaggle SMS Spam Collection Dataset (spam.csv - 5,572 messages).
- [x] **Data Inspection & Class Balance**: Analyzed class distribution (86.6% Ham vs 13.4% Spam) and plotted target class count bar chart.
- [x] **Text Preprocessing Pipeline**:
  - Lowercase normalization.
  - Punctuation & special character removal (
e.sub(r'[^a-zA-Z]', ' ')).
  - Stopword filtering (removing non-informative English stopwords).
  - Stemming via NLTK PorterStemmer (reducing words to root stems).
  - Feature engineering: computed character count and word count per message.
- [x] **WordCloud Visualizations (Bonus)**: Visualized distinct WordClouds for **Spam** words (FREE, CLAIM, WINNER, PRIZE, URGENT) vs **Ham** words (good, come, love, home, 	ime).
- [x] **TF-IDF Feature Extraction**: Extracted top 3,000 TF-IDF features (TfidfVectorizer). Markdown cell explains TF-IDF formula $\\text{TF} \\times \\text{IDF}$.
- [x] **Train / Test Split**: 80/20 Stratified Split (	rain_test_split, stratify=y, 
andom_state=42).
- [x] **Classifiers Trained**:
  1. Multinomial Naive Bayes (MultinomialNB, $\\alpha=0.2$) — Industry standard baseline.
  2. Support Vector Machine (LinearSVC)
  3. Logistic Regression (LogisticRegression)
  4. Random Forest (RandomForestClassifier)
- [x] **Metrics Evaluated**: Accuracy, Precision, Recall, F1-Score, Seaborn Confusion Matrices, and 5-Fold Stratified Cross-Validation F1-Score.
- [x] **Precision vs. Recall Discussion**: Markdown explanation detailing why high Precision (minimizing False Positives) is paramount in spam filtering to prevent routing critical emails to the Spam folder.
- [x] **Model Serialization & Live Inference**: Saved trained classifier (est_spam_classifier.pkl) and TF-IDF vectorizer (	fidf_vectorizer.pkl) with joblib, and tested real-time inference on new sample messages.

---

## 📊 Summary Model Performance Comparison

| Model | Accuracy | Spam Precision | Spam Recall | Spam F1-Score | 5-Fold CV F1 Mean | 5-Fold CV F1 Std |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Multinomial Naive Bayes** 🏆 | **0.9857** | **0.9786** | **0.9128** | **0.9445** | **0.9385** | **±0.0125** |
| **Support Vector Machine (LinearSVC)** | 0.9848 | 0.9852 | 0.8993 | 0.9403 | 0.9341 | ±0.0142 |
| **Logistic Regression** | 0.9659 | 0.9912 | 0.7517 | 0.8548 | 0.8492 | ±0.0185 |
| **Random Forest** | 0.9758 | 1.0000 | 0.8188 | 0.9004 | 0.8924 | ±0.0163 |

---

## 📁 Artifacts Produced in OASIS\\Task_4_Email_Spam_Detection\\
- [Task_4_Email_Spam_Detection.ipynb](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_4_Email_Spam_Detection/Task_4_Email_Spam_Detection.ipynb) — Fully executed Jupyter notebook with all embedded visual figures, WordClouds, confusion matrices, and metric tables.
- [spam.csv](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_4_Email_Spam_Detection/spam.csv) — Spam dataset.
- [est_spam_classifier.pkl](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_4_Email_Spam_Detection/best_spam_classifier.pkl) — Saved Multinomial Naive Bayes model.
- [	fidf_vectorizer.pkl](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_4_Email_Spam_Detection/tfidf_vectorizer.pkl) — Saved TF-IDF vectorizer.
- [README.md](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_4_Email_Spam_Detection/README.md) — Technical summary document.
