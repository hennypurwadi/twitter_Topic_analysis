# Twitter Entity and Topic Analysis around London (30km Radius)

This project performs analysis on tweets collected from within a 30 km radius around 10 Downing Street, London. The purpose is to identify key entities and extract prevalent topics without requiring access to the Twitter API.

### 📌 Objectives

- **Entity Analysis**:
  - Identify the 5 most active Twitter users.
  - Find the 5 most frequently used hashtags.
- **Topic Modeling**:
  - Extract the 5 most prevalent topics from tweet content using different vectorization and modeling techniques (LDA, NMF).

---

## 🔧 Installation and Environment Setup

This project uses a Conda virtual environment.

### 1. Create Environment
```bash
conda env create -f DLBDSEDA02.yaml
```

### 2. Activate Environment
```bash
conda activate DLBDSEDA02
```

### 3. Add Library & Update Environment
```bash
conda env update -f DLBDSEDA02.yaml
```

### 4. Deactivate Environment
```bash
conda deactivate
```

---

## 🧪 Run the Notebook

Start the Jupyter Notebook:

```bash
jupyter notebook
```

If it doesn't work:

```bash
python -m notebook
```

> To stop the process: `Ctrl + C`  
> To return to cmd: `Ctrl + Z`

---

## 📥 Library Requirements (if needed manually)
```bash
pip install snscrape
pip install tweepy
pip install wordcloud
```

---

## 📊 Workflow Summary

### 1. Collect Twitter Data

- Tweets were collected using the `snscrape` library.
- Total tweets scraped: **40,000**
- Timeframe: **29–30 July 2022**
- No Twitter Developer API required.
- Dataset includes usernames, hashtags, and tweet text.

### 2. Entity Analysis

- **Top Users**: Based on tweet count (most active = 164 tweets).
- **Top Hashtags**: After basic regex cleaning (lowercasing, removing special characters).
- **No additional lowercase cleaning for usernames** (capitalization is part of identity).

### 3. Topic Modeling

#### Preprocessing:

- Cleaned using regex, URL and special character removal.
- Stopwords removal, tokenization, lemmatization, stemming with `nltk`.

#### Vectorization:

- `CountVectorizer` with `ngram_range=(1,3)` for unigrams, bigrams, trigrams.
- `TfidfVectorizer` with the same `ngram_range`.

#### Topic Extraction:

- Using **LDA** (Latent Dirichlet Allocation) and **NMF** (Non-negative Matrix Factorization) on both vectorizers.
- NMF outperformed LDA for incoherent text like tweets.
- Identified topics included:
  - **Love Island** (TV show)
  - **Music**
  - **Trains and Rail**

#### Insights:

- LDA is better for coherent text, but less effective on noisy Twitter data.
- NMF with Tf-IDF provided more distinct and relevant topics.

---

## ✅ Conclusion

- **Tf-IDF > CountVectorizer** for weighting meaningful words.
- **NMF > LDA** for noisy and short texts like tweets.
- Contrary to expectation, tweets about **Love Island** were more prevalent than those about UK politics during the period analyzed.

---

## 📂 Repository

GitHub Project: [https://github.com/hennypurwadi/twitter_analysis](https://github.com/hennypurwadi/twitter_analysis)

---

## 📚 References

- Marco Bonzanini. *Mastering Social Media Mining with Python* (2016).
- Nassera Habat (2021). *Topic Modeling on Moroccan Tweets*.
- Sheel Saket (2020). *CountVectorizer vs Tf-IDF*.
- [Scikit-learn CountVectorizer Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html)
- [Love Island Final Episode News](https://metro.co.uk/2022/07/27/when-does-love-island-2022-end-final-episode-date-revealed-2-17079275/)
