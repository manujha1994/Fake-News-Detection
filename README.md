# 📰 Misinformation Classification Using NLP

This project explores the detection of fake news through natural language processing and supervised learning. Built entirely in a Jupyter Notebook, the solution identifies misinformation by analyzing the linguistic features of news articles—without relying on source metadata or external credibility signals.

## 📘 Overview

The spread of digital misinformation poses a growing threat to public discourse. This notebook demonstrates a semantic classification pipeline designed to:

- Clean and preprocess raw news text
- Use noun-focused lemmatization to extract meaningful semantics
- Convert text into vector representations using Word2Vec
- Train multiple machine learning models to classify news as real or fake
- Evaluate model performance using accuracy, precision, recall, and F1-score

## 📊 Dataset

The project uses two CSV files:
- `True.csv` – Contains 21,417 articles verified as factual
- `Fake.csv` – Contains 23,502 articles labeled as false

Each article includes a `title`, `text`, and `date`. Only the textual content was used in the analysis.

## 🛠 Workflow Summary

1. **Data Merging and Cleaning**  
   - Combine both datasets and assign binary labels  
   - Drop missing values and remove date column  

2. **Text Preprocessing**  
   - Convert to lowercase, remove punctuation/numbers  
   - Lemmatize using spaCy (nouns only)  
   - Remove stopwords and short tokens  

3. **Feature Extraction**  
   - Use pre-trained GoogleNews Word2Vec (300 dimensions)  
   - Average word vectors for each article  

4. **Modeling and Evaluation**  
   - Train Logistic Regression, Decision Tree, and Random Forest  
   - Best model: Random Forest (F1-score = 0.901)

## 📈 Performance Snapshot

| Model              | Accuracy | Precision | Recall | F1-Score |
|-------------------|----------|-----------|--------|----------|
| Logistic Regression | 90.1%    | 89.1%     | 90.3%  | 89.7%    |
| Decision Tree       | 82.3%    | 82.7%     | 79.4%  | 81.0%    |
| Random Forest       | **90.6%**| **90.5%** | **89.7%** | **90.1%** |

## 🧠 Insights

- Real news often includes policy and governance-related language (e.g., "government", "election")
- Fake news favors emotionally charged or visual terms (e.g., "image", "video", "supporter")
- Lemmatization dramatically reduces text length and improves semantic clarity

## 📄 Report

Read the full project report:  
📄 [`Fake_News_Detection_Manu.pdf`](./Fake_News_Detection_Manu.pdf)

## 🧪 Try It Out

Open the notebook and run all cells to explore the full pipeline—from raw data to model evaluation. No installation required if you're using platforms like **Google Colab** or **JupyterLab**.

---
