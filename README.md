Amharic E-commerce Data Extractor
Project Overview
This project focuses on data ingestion and preprocessing for Ethiopian-based Telegram e-commerce channels. The goal is to collect, clean, and structure messages containing product listings, prices, and locations. Additionally, a subset of the dataset is labeled in CoNLL format for Named Entity Recognition (NER) tasks.


Task 1: Data Ingestion & Preprocessing
Objective
- Fetch messages from at least 5 Ethiopian Telegram e-commerce channels.
- Extract text, images, and documents in real-time.
- Preprocess text data for entity extraction.
Steps
- Identify & Connect to relevant Telegram channels using a custom scraper.
- Implement a message ingestion system to collect data in real-time.
- Preprocess text data:
- Tokenization
- Normalization (handling Amharic-specific linguistic features)
- Cleaning & structuring metadata (sender, timestamp, message content)
- Store preprocessed data in a structured format for further analysis.



Task 2: Labeling Dataset in CoNLL Format
Objective
- Label a subset of 30-50 messages for Named Entity Recognition (NER).
- Identify products, prices, and locations in Amharic text.
CoNLL Format
Each token is labeled on its own line, followed by its entity type. Blank lines separate individual messages.

Output
- `Telegram_Scraper.ipynb`: Data collection from Telegram channels
- `Telegram_Data_Labeling.ipynb`: Interactive labeling interface  
- `Amharic_NER_CoNLL.ipynb`: CoNLL format conversion and model training.

