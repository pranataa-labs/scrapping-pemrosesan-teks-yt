# 📊 Text Processing & NLP Practicum: YouTube Comment Mining

**Universitas Teknologi Yogyakarta (UTY)**  
*Faculty of Science & Technology • Department of Informatics*  

---

## 📌 Project Overview & Research Context

* **Topic:** Public Opinion Mining on Budget Misappropriation and Audit Manipulation via YouTube Comments
* **Data Source:** YouTube Public Commentary (`https://www.youtube.com/watch?v=ToZSRkAybKc`)
* **Corpus Volume:** 520 Curated Indonesian Text Comments
* **Academic Course:** Applied Text Processing Practicum

---

## 📁 Repository Organization

* [`Tugas_Kelompok_Pemrosesan_Teks.ipynb`](./Tugas_Kelompok_Pemrosesan_Teks.ipynb): Master Jupyter/Colab notebook executing the 5-stage text mining pipeline, regex extraction, negation preservation, Sastrawi morphological stemming, Top-15 Bigrams, and Top-10 PMI collocations.
* [`korpus_komentar_clean.csv`](./korpus_komentar_clean.csv): Anonymized and cleaned text corpus dataset (520 verified comments with SHA-256 author hashing).

---

## 🔬 NLP Methodology & Processing Pipeline

1. **Automated Data Scraping:** Ingestion of 520 raw YouTube comments using `youtube-comment-downloader`.
2. **Privacy Anonymization:** One-way irreversible SHA-256 account masking (`user_xxxxxxxx`).
3. **Regex Pattern Extraction:** Explicit capture and auditing of URLs, user mentions (`@`), hashtags (`#`), unicode emojis, and numeric quantities.
4. **Multi-Stage Text Preprocessing:**
   * Case folding to lowercase.
   * Regex character cleaning and punctuation stripping.
   * NLTK tokenization.
   * Slang word normalization against a 15,000-word vernacular dictionary.
   * Stopword removal with **critical negation preservation** (*tidak, bukan, belum, kurang, jangan, tanpa, palsu*) to protect sentiment polarity.
5. **Stemming & N-Gram Collocation:**
   * Indonesian morphological stemming utilizing the Sastrawi library.
   * Frequency distribution extraction of Top-15 Bigrams (`FreqDist`).
   * Top-10 Pointwise Mutual Information (PMI) collocation extraction with frequency threshold ($\ge 3$).

---

<p align="center">
  Maintained by <b><a href="https://github.com/pranataa-labs">pranataa-labs</a></b>
</p>
