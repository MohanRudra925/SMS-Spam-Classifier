📩 SMS Spam Classifier
A machine learning project to classify SMS messages as spam or ham (not spam) using text processing techniques and multiple ML algorithms. This project includes data preprocessing, exploratory data analysis, feature extraction, model building, evaluation, and saving the final model using pickle.

📚 Dataset
Source: Spam.csv (contains 5,572 SMS messages)

Columns Used:

v1: Label (spam or ham)

v2: Text message

🔧 Preprocessing Steps
Dropped unnecessary columns (Unnamed: 2, Unnamed: 3, Unnamed: 4)

Renamed columns to target (labels) and text (messages)

Encoded labels: ham → 0, spam → 1

Removed duplicates

Added features:

num_characters

num_words

num_sentences

🧼 Text Transformation
Text cleaning and preprocessing included:

Lowercasing

Tokenization

Removal of stopwords and punctuation

Stemming (Porter Stemmer)

Word clouds generated for both spam and ham texts

📊 Exploratory Data Analysis
Visualized distributions of text length, word count, and sentence count for both spam and ham.

Most common words in spam and ham messages were identified and plotted using bar charts.

🧠 Model Building
Feature Extraction
Used TfidfVectorizer with a max feature size of 3000.

Models Trained
Naive Bayes (Multinomial, Gaussian, Bernoulli)

Logistic Regression

Support Vector Machine (SVM)

Random Forest

Decision Tree

K-Nearest Neighbors

AdaBoost, Bagging, Extra Trees, Gradient Boosting

XGBoost

Ensemble Techniques
Voting Classifier (SVM + MultinomialNB + Extra Trees)

Stacking Classifier (with Random Forest as final estimator)

🏆 Best Performing Model
Model	Accuracy	Precision
MultinomialNB	0.97	1.00
BernoulliNB	0.98	0.99
Voting Classifier	0.98	0.99
Stacking Classifier	0.98	0.94

💾 Model Saving
Saved the final model and vectorizer:

model.pkl

vectorizer.pkl

🛠️ Technologies Used
Python

Pandas, NumPy

Scikit-learn

NLTK

Seaborn, Matplotlib

WordCloud

Pickle

📈 Future Improvements
Implement deep learning models (LSTM, BERT)

Use lemmatization instead of stemming

Deploy using a web framework (e.g., Flask or Streamlit)

🔗 How to Run
bash
Copy
Edit
# Clone the repo
git clone https://github.com/yourusername/sms-spam-classifier.git
cd sms-spam-classifier

# Install dependencies
pip install -r requirements.txt

# Run your training script (if available)
python train.py

# Load model and vectorizer
import pickle
model = pickle.load(open('model.pkl', 'rb'))
vectorizer = pickle.load(open('vectorizer.pkl', 'rb'))
