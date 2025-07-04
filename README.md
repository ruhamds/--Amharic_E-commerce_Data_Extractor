# 🛒 EthioMart Telegram NER & Vendor Analytics

This project extracts structured business insights from Amharic Telegram vendor posts to support inclusive **micro-lending**. It combines **Named Entity Recognition (NER)**, **explainability (SHAP & LIME)**, and **vendor behavior analytics** into a complete NLP-driven fintech solution.

---

## 📦 Project Structure

├── data/ # Telegram data and labeled CoNLL files
├── models/ # Trained NER models (mBERT, etc.)
├── notebooks/ # Jupyter notebooks for each task
├── scripts/ # Python scripts for inference, scoring, labeling
├── reports/ # Generated PDF reports and charts
└── telegram_data.csv # Main vendor post dataset (local only)
---

## ✅ Tasks Summary

### Task 1: Telegram Data Scraping
- Scraped **20,000+ posts** from 6 vendor channels.
- Metadata collected: text, views, timestamps, image OCR.
- Exported to `telegram_data.csv`.

### Task 2: NER Data Labeling
- Labeled **51 Amharic posts** in CoNLL format.
- Entity tags: `B-Product`, `I-Product`, `B-PRICE`, `I-PRICE`, `B-LOC`, `I-LOC`, `O`.
- Used regex rules + manual annotation tools.

### Task 3: NER Model Fine-Tuning
- Models trained: `xlm-roberta`, `distilbert`, `mBERT`.
- ✅ **Best model:** `mBERT`
  - Accuracy: `0.88`
  - F1: `0.73`
  - Recall: `0.72`

### Task 4: NER Inference
- Applied the fine-tuned `mBERT` model to extract:
  - **Product names**
  - **Prices (ETB)**
  - **Locations**
- Results saved to enriched dataset for scoring.

### Task 5: Model Interpretability
- Tools used:
  - **SHAP** — token-level explanation
  - **LIME** — sentence-level explainability
- Improved understanding of model behavior & debugging.

### Task 6: Vendor Scorecard for Micro-Lending
- Computed per-vendor metrics:
  - `Posts per Week`
  - `Average Views per Post`
  - `Average Price Point`
  - `Top Performing Product`
  - `Lending Score = 0.5 * Avg Views + 0.5 * Posting Frequency`
- Output: vendor comparison table for lender decision-making.

---

## 📊 Sample Vendor Scorecard Output

| Vendor       | Views | Posts/Week | Avg. Price | Lending Score | Top Product     |
|--------------|-------|------------|------------|----------------|------------------|
| classybrands | 723   | 5.2        | 890 ETB    | 364.1          | የፀጉር መታጠቢያ   |
| qnashcom     | 420   | 7.1        | 310 ETB    | 213.5          | ቤት ዕቃ          |

---

## 💡 Business Impact

> This project equips EthioMart and lending partners with real-time vendor intelligence in **Amharic**, enabling better credit risk decisions and financial inclusion — especially for **unbanked or informal sellers** operating on Telegram.

---

## 🚀 Next Steps

- Integrate customer review sentiment analysis
- Expand NER label set (e.g., categories, discounts)
- Launch pilot lending dashboard with vendor metrics
- Explore vendor segmentation by price/value clusters

---

## 📄 Resources

- `INTERIM WEEK 4.pdf` — Initial scraping + labeling report
- `EthioMart_Report_Tasks1-6.pdf` — Final analytic report
- `/models/ner_model/` — Trained NER model (mBERT)
