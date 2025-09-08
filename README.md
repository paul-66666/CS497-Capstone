

# Aspect-Based Sentiment Analysis (ABSA) for Amazon Beauty Reviews

**Author:** Jinquan Lin
**Advisor:** Sam Chung, Ph.D.
**Program:** BS in Applied Computer Science, City University of Seattle

---

## 📌 Overview

This project implements an end-to-end pipeline for **root cause analysis of negative product reviews**. Using the **Amazon US Beauty Reviews dataset**, the system identifies *why* customers are dissatisfied—not just whether sentiment is positive or negative.

The pipeline integrates:

* **BiLSTM + Attention** for review-level polarity.
* **Aspect lexicon** to detect product/service facets (quality, packaging, fragrance, delivery).
* **Fusion scoring (α = 0.7)**: BiLSTM + VADER for stable sentence-level sentiment.
* **Keyword extraction (YAKE)** + representative quotes as human-readable evidence.
* **Exportable CSVs & charts** to support managerial decision-making.

This project was developed as part of my **CS 497 Capstone** at City University of Seattle.

---

## ✨ Features

* Balanced **BiLSTM** training with interpretable attention.
* **Aspect-Based Sentiment Analysis (ABSA)** with regex lexicons.
* **Representative examples** ranked by negativity + helpfulness.
* **Keyword extraction with YAKE**.
* **Visualization & export**: CSV tables and bar charts.

### Outputs include:

* `absa_sentence_aspect_results.csv` – sentence-level aspect sentiment results.
* `absa_aspect_summary.csv` – counts and negative rate per aspect.
* `absa_aspect_negative_examples.csv` – representative negative quotes.
* `absa_aspect_negative_keywords.csv` – aspect-specific negative keywords.

---

### 📈 Notes on Charts & Visualizations

* All charts (ROC, PR curves, confusion matrix, aspect bar plots, keyword visualizations, etc.) are generated automatically when running the notebook in Google Colab.
* If you want to view the charts and visual outputs from my final submission, please open:
* Root_cause_analysis_system_for_negative_reviews Final Submission notebook
* and scroll through the executed cells. The plots and exports are saved during runtime and attached below the relevant code blocks.

## 🛠️ Tech Stack

* **Python** (Colab / Jupyter Notebook)
* **TensorFlow / Keras** – BiLSTM + Attention
* **scikit-learn** – preprocessing & metrics
* **NLTK + VADER** – sentence tokenization & sentiment
* **YAKE** – keyword extraction
* **Matplotlib** – visualization

---

## 📂 Data Source

* **Dataset:** Amazon US Customer Reviews – Beauty (v1.00)
* **Scope:** Focus on 1–2 star negative reviews to surface *root causes*.

---

## 🚀 Quick Start

### Option A – Fast Inference (no training)

1. Go to the **Releases** page and download the three assets:

   * `absa_bilstm_simpleatt.keras` (pretrained model)
   * `tokenizer.json` (training tokenizer)
   * `inference_config.json` (runtime settings)
2. Place them in a folder, e.g. `./model_ckpt/`.
3. In the notebook/script, set:

   ```python
   SAVE_DIR = "./model_ckpt"
   LOAD_SAVED_MODEL = True
   ```
4. Run the pipeline → directly perform ABSA, aggregation, and export results.

### Option B – Train from scratch

* Set `LOAD_SAVED_MODEL = False` to retrain BiLSTM on a balanced sample, then save new model + tokenizer + config.

---

## 📊 Example Outputs

* **Top Negative Aspects**: *scent/fragrance* & *quality/durability* (largest volumes).
* **High Negative Rates**: *authenticity* & *customer service*.
* Example quote: *“It broke after just one week.”* (durability, fusion score –0.85)

---

## 🎯 Applications

* **E-commerce Operations** – detect recurring product failures.
* **Quality Control** – monitor durability or formula issues.
* **Customer Service** – track refund/return complaints.
* **Logistics** – identify shipping & delivery delays.

---

## 📖 References

* Davoodi, L., Mezei, J., & Heikkilä, M. (2025). *Aspect-based sentiment classification of user reviews*. Electronic Commerce Research.
* Malik, N., & Bilal, M. (2024). *NLP for analyzing online customer reviews: survey and taxonomy*. PeerJ Computer Science.
* Priporas, C.-V., et al. (2022). *Negative Airbnb reviews: An ABSA approach*. EuroMed Journal of Business.

---

## 📜 License

This project is for **educational and research purposes** under the guidance of City University of Seattle.

---

