# SMS & Email Spam Classifier

An end-to-end Machine Learning web application built with Python, scikit-learn, NLTK, and Streamlit to detect whether an incoming message or email is Spam or Ham (Not Spam).

---

## Features

- **Text Preprocessing Pipeline:** Tokenization, lowercase conversion, punctuation filtering, stopword elimination, and Porter Stemming via NLTK.
- **Vectorization:** TF-IDF (Term Frequency-Inverse Document Frequency) vectorizer.
- **Machine Learning Inference:** Pretrained supervised classification model serialized via `pickle`.
- **Interactive UI:** Lightweight, responsive web interface built using Streamlit.
- **Cloud Ready:** Structured for zero-config deployment to Streamlit Community Cloud.

---

## Project Structure

```text
spamClassifier/
│
├── app.py              # Streamlit application & inference pipeline
├── model.pkl           # Trained classification model
├── vectorizer.pkl      # Trained TF-IDF vectorizer
├── requirements.txt    # Python dependencies
└── README.md           # Project documentation
```

---

## NLP & ML Workflow

1. **Input Preprocessing (`transform_text`):**
   - Convert text to lowercase.
   - Tokenize into individual words using `nltk.word_tokenize`.
   - Remove special characters, alphanumeric filtering, and punctuation (`string.punctuation`).
   - Filter English stopwords (`nltk.corpus.stopwords`).
   - Stem words to root form using `PorterStemmer`.

2. **Feature Extraction:**
   - Preprocessed text is converted to a numerical feature matrix using the trained TF-IDF vectorizer (`vectorizer.pkl`).

3. **Classification:**
   - The feature vector is passed to the trained classifier (`model.pkl`) to generate a binary prediction:
     - `1` $\rightarrow$ **Spam**
     - `0` $\rightarrow$ **Ham (Not Spam)**

---

## Local Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Dhanush-K249/spam-classifier.git
cd spam-classifier
```

### 2. Create a Virtual Environment (Optional but Recommended)

```bash
python -m venv venv

# On Windows:
venv\Scripts\activate

# On macOS/Linux:
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

> **Note:** Do not include `pickle` or `string` in `requirements.txt` as they are built-in Python standard libraries.

### 4. Run the Streamlit App

```bash
streamlit run app.py
```

The web application will open locally at `http://localhost:8501`.

---

## Deployment (Streamlit Community Cloud)

1. Push your repository to GitHub:
   ```bash
   git add .
   git commit -m "Prepare repository for deployment"
   git branch -M main
   git push -u origin main
   ```
2. Navigate to [Streamlit Community Cloud](https://share.streamlit.io/).
3. Connect your GitHub account.
4. Select repository: `Dhanush-K249/spam-classifier`.
5. Set the main file path to `app.py`.
6. Click **Deploy**.

---

## Tech Stack

- **Language:** Python
- **Natural Language Processing:** NLTK
- **Machine Learning:** Scikit-learn
- **Frontend / Hosting:** Streamlit & Streamlit Community Cloud