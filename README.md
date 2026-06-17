
# Spam Email Detection using NLP & Naive Bayes
A machine learning project that classifies SMS/email messages as spam or ham (not spam) using Natural Language Processing and a Naive Bayes classifier.

# 📌 Business Problem
Spam messages threaten productivity, privacy, and security through phishing attacks, data overload, and distraction. This project builds a model that automatically flags spam so it can be filtered before reaching the user.

# 🧰 Tech Stack

-> Python

-> pandas – data loading and manipulation

-> scikit-learn – TF-IDF vectorization, train/test split, Multinomial Naive Bayes, evaluation metrics

-> Jupyter Notebook

# 📂 Dataset
The project uses the classic SMS Spam Collection dataset (spam.csv), containing 5,572 labeled messages (4,825 ham / 747 spam).

# 🔄 Workflow

1) Load Dataset – Read spam.csv (latin-1 encoding) and inspect with .head() / .tail().

2) Clean Data – Drop unnamed/empty columns, keep only v1 (label) and v2 (text), rename to label and text.

3) Preprocessing – Map labels to binary (ham → 0, spam → 1).

4) Feature Extraction – Convert text to numeric features using TfidfVectorizer (English stopwords removed), producing a sparse matrix with 8,404 features.

5) Train/Test Split – 80/20 split (random_state=42).

6) Model Training – Fit a MultinomialNB classifier on the training data.

7) Evaluation – Predict on the test set and report accuracy, precision, recall, and F1-score.

# 📊 Results

The model achieved an overall accuracy of 96.9% on the test set of 1,115 messages.
For class 0 (ham), the model scored a precision of 0.96 and recall of 1.00, giving an F1-score of 0.98. For class 1 (spam), precision was a perfect 1.00 while recall came in at 0.77, giving an F1-score of 0.87. The weighted average across both classes landed at 0.97 for precision, recall, and F1-score alike.

### Overall Accuracy: 96.9%

# Key Observations

-> The model achieves near-perfect precision and recall on ham, rarely misclassifying legitimate messages.

-> Spam precision is perfect (no false alarms), but recall is lower (0.77), meaning roughly 23% of spam slips through — largely a result of class imbalance (747 spam vs. 4,825 ham examples).

-> Weighted average F1-score of 0.97 confirms strong overall performance.
