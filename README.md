
---

# Aspect-Based Sentiment Analysis (ABSA) for Amazon Beauty Reviews

**Author:** Jinquan Lin
**Advisor:** Sam Chung, Ph.D.
**Program:** BS in Applied Computer Science, City University of Seattle

---

## 📌 Overview

This project implements an **end-to-end pipeline for root cause analysis of negative product reviews**. Using the Amazon US Beauty Reviews dataset, the system identifies why customers are dissatisfied, not just whether sentiment is positive or negative.

The pipeline combines:

* A **BiLSTM with attention** to learn review-level polarity.
* A **compact aspect lexicon** to detect product/service facets (e.g., quality, packaging, fragrance, delivery).
* **Fusion of BiLSTM outputs with VADER** scores for stable sentence-level sentiment.
* **Keyword extraction (YAKE)** and **representative quotes** to provide human-readable evidence.
* **Exportable CSVs and charts** for managerial decision-making.

This project was developed as part of my **CS 497 Capstone** at City University of Seattle.

---

## ✨ Features

* **Balanced BiLSTM training** with interpretable attention layer.
* **Aspect-Based Sentiment Analysis** (ABSA) using regex lexicons.
* **Fusion scoring** (α = 0.7) for robust sentiment labeling.
* **Representative examples** ranked by negativity and helpfulness.
* **Top keyword extraction** with YAKE.
* **Visualization & export**: bar charts and CSV tables.

Output includes four CSVs:

1. `absa_sentence_aspect_results.csv` – sentence-level aspect sentiment results.
2. `absa_aspect_summary.csv` – total/negative counts and negative rate per aspect.
3. `absa_aspect_negative_examples.csv` – top negative representative quotes.
4. `absa_aspect_negative_keywords.csv` – per-aspect negative keywords.

---

## 🛠️ Tech Stack

* **Python** (Colab / Jupyter Notebook)
* **TensorFlow / Keras** – BiLSTM + Attention
* **scikit-learn** – metrics & preprocessing
* **NLTK + VADER** – sentence tokenization & rule-based sentiment
* **YAKE** – keyword extraction
* **Matplotlib** – visualization

---

## 📂 Data Source

* Dataset: [Amazon US Customer Reviews – Beauty (v1.00)](https://www.kaggle.com/datasets/beaglelee/amazon-reviews-us-beauty-v1-00-tsv-zip)
* Scope: Focus on **1–2 star negative reviews** to surface root causes.

---

## 🚀 Quick Start

### 1. Install dependencies

```bash
pip install kagglehub nltk vaderSentiment yake tensorflow scikit-learn matplotlib
```

### 2. Run in Colab

Open the notebook and run cells in order. The pipeline will:

1. Download & clean data.
2. Train or load BiLSTM model.
3. Extract aspects and compute sentiment.
4. Export results as CSVs + visualizations.

### 3. Example Usage

After running, check `/content/` for exported CSVs and use them for analysis or dashboards.

---

## 📊 Example Outputs

* **Top Negative Aspects (by count)**
  ![Example chart](docs/top_negative_aspects.png)

* **Representative Negative Quotes**
  \| Aspect            | Example Quote                        | Fusion Score |
  \|-------------------|--------------------------------------|--------------|
  \| quality\_durability | “It broke after just one week.”       | -0.85 |
  \| scent\_fragrance   | “The smell was too strong and bad.”  | -0.76 |

---

## 🎯 Applications

* **E-commerce Operations** – detect recurring product failures.
* **Quality Control** – track durability or formula issues.
* **Customer Service** – monitor refund/return complaints.
* **Logistics** – identify shipping & delivery problems.

---

## 📖 References

This project builds upon prior research in ABSA, sentiment analysis, and root cause analytics, including:

* Davoodi, L., Mezei, J., & Heikkilä, M. (2025). *Aspect-based sentiment classification of user reviews*. Electronic Commerce Research.
* Malik, N., & Bilal, M. (2024). *NLP for analyzing online customer reviews: survey and taxonomy*. PeerJ Computer Science.
* Priporas, C.-V., et al. (2022). *Negative Airbnb reviews: An ABSA approach*. EuroMed Journal of Business.

---

## 📜 License

This project is for educational and research purposes under the guidance of City University of Seattle.

---
