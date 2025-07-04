# 🛒 EthioMart Telegram NER & Vendor Analytics

This project extracts structured business insights from Amharic Telegram vendor posts to support inclusive **micro-lending**. It combines **Telegram data scraping**, **Named Entity Recognition (NER)**, **model interpretability (SHAP & LIME)**, and **vendor scoring analytics** into a complete NLP-driven fintech solution.

---

## 📦 Project Structure

├── data/ # Telegram data and labeled CoNLL files
├── models/ # Trained NER models (mBERT, etc.)
├── notebooks/ # Jupyter notebooks for each task
├── scripts/ # Python scripts for inference, scoring, labeling


---

## ✅ Tasks Summary

### Task 1: Data Ingestion & Preprocessing
**Objective:**
- Fetch messages from at least 5 Ethiopian Telegram e-commerce channels.
- Extract text, images, and documents in real-time.
- Preprocess text data for entity extraction.

**Steps:**
- Identify & connect to Telegram channels using Telethon.
- Collect real-time data from vendors (text, views, timestamps).
- OCR image-based content using Tesseract.
- Normalize, tokenize, and structure the message content.

---

### Task 2: NER Data Labeling
- Labeled **51 Amharic posts** in CoNLL format using a custom interface.
- Entity tags: `B-Product`, `I-Product`, `B-PRICE`, `I-PRICE`, `B-LOC`, `I-LOC`, `O`.
- Balanced distribution of tokens across label types (540 tokens total).

---

### Task 3: NER Model Fine-Tuning
- Models trained: `xlm-roberta`, `distilbert`, and `mBERT`.
- ✅ **Best model:** `mBERT`
  - Accuracy: `0.88`
  - F1 Score: `0.73`
  - Recall: `0.72`

---

### Task 4: Entity Inference on All Vendor Posts
- Applied the fine-tuned NER model to extract:
  - **Product names**
  - **Prices (ETB)**
  - **Locations**
- Enriched the full dataset with these structured fields.

---

### Task 5: Model Interpretability
- Used:
  - **SHAP** — to visualize the token-level impact on predictions.
  - **LIME** — to explain sentence-level NER outputs.
- Improved understanding and debugging of edge cases and token confidence.

---

### Task 6: Vendor Scorecard for Micro-Lending
- Built an analytics engine that scores vendors based on:
  - Posting frequency (`posts per week`)
  - `Average views per post`
  - `Average listed price`
  - Top performing product (by views)
- Calculated a **Lending Score**:  
  `Lending Score = 0.5 * Avg Views + 0.5 * Post Frequency`

---

## 📊 Sample Vendor Scorecard Output

| Vendor       | Views | Posts/Week | Avg. Price | Lending Score | Top Product     |
|--------------|-------|------------|------------|----------------|------------------|
| classybrands | 723   | 5.2        | 890 ETB    | 364.1          | የፀጉር መታጠቢያ   |
| qnashcom     | 420   | 7.1        | 310 ETB    | 213.5          | ቤት ዕቃ          |

---

## 💡 Business Impact

> This project enables EthioMart and partner micro-lenders to make **data-informed decisions** by scoring vendors based on real market engagement and product activity. It supports credit access for **unbanked or informally operating sellers** through AI-driven insights.

---

## 🚀 Next Steps

- Add customer sentiment analysis from user comments.
- Extend entity tags to include discounts, brand names, and stock status.
- Launch a lending pilot using the scorecard dashboard.
- Explore vendor segmentation based on volume vs. margin.

---

## 📄 Resources

- `INTERIM WEEK 4.pdf` — Raw scraping & labeling documentation
- `EthioMart_Report_Tasks1-6.pdf` — Final summary report (all tasks)
- Trained model directory: `/models/ner_model/`

---
