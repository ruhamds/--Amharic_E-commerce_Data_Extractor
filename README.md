# 🛒 EthioMart Telegram NER & Vendor Analytics

This project extracts structured business insights from Amharic Telegram vendor posts to support inclusive **micro-lending**. It combines **Named Entity Recognition (NER)**, **explainability (SHAP & LIME)**, and **vendor behavior analytics** into a complete NLP-driven fintech solution.

---

## 📦 Project Structure

├── data/ # Telegram data and labeled CoNLL files
├── models/ # Trained NER models (mBERT, etc.)
├── notebooks/ # Jupyter notebooks for each task
├── scripts/ # Python scripts for inference, scoring, labeling
├── reports/ # Generated PDF reports and charts
└── telegram_data.csv # Main vendor post dataset


---

## ✅ Tasks Summary

### Task 1: Telegram Data Scraping
- Scraped **20,000+ posts** from 6 vendor channels.
- Metadata collected: text, views, timestamps, image OCR.
- Exported to `telegram_data.csv`.

### Task 2: NER Data Labeling
- Labeled **51 Amharic posts** in CoNLL format.
- Labels: `B-Product`, `I-Product`, `B-PRICE`, `I-PRICE`, `B-LOC`, `I-LOC`, `O`.
- Used regex + manual annotation tools.

### Task 3: NER Model Fine-Tuning
- Trained: `xlm-roberta`, `distilbert`, `mbert`.
- **Best model:** `mBERT`
  - Accuracy: `0.88`
  - F1: `0.73`
  - Recall: `0.72`

### Task 4: NER Inference
- Applied fine-tuned NER model to extract:
  - **Product names**
  - **Prices (ETB)**
  - **Locations**
- Outputs stored for downstream analytics.

### Task 5: Model Interpretability
- Applied:
  - **SHAP** → token-level impact visualization
  - **LIME** → per-sentence explainability
- Used to debug model and explain predictions.

### Task 6: Vendor Scorecard for Micro-Lending
- Computed:
  - `Posts per Week`
  - `Average Views per Post`
  - `Average Price Point`
  - `Top Performing Product`
  - `Lending Score = 0.5 * Views + 0.5 * Frequency`
- Created a vendor comparison table for fintech decision-making.

---

## 📊 Sample Vendor Scorecard Output

| Vendor     | Views | Posts/Week | Avg. Price | Lending Score | Top Product |
|------------|-------|------------|------------|----------------|-------------|
| classybrands | 723  | 5.2        | 890 ETB    | 364.1          | የፀጉር መታጠቢያ |
| qnashcom     | 420  | 7.1        | 310 ETB    | 213.5          | ቤት ዕቃ      |

---

## 💡 Business Impact

> This project equips EthioMart and micro-lenders with real-time vendor intelligence in **Amharic**, enabling better credit risk scoring and product insights — especially for **unbanked or informally operating sellers**.

---

## 🚀 Next Steps

- Integrate customer review sentiment
- Expand label set to include product categories
- Launch lending dashboard pilot

---

## 📄 Resources

- `INTERIM WEEK 4.pdf` — Initial data collection & labeling summary
- `EthioMart_Report_Tasks1-6.pdf` — Full analytics report
- Trained model: `/models/ner_model/`

---


