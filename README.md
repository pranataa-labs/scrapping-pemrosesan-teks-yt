# Praktikum Pemrosesan Teks
**Universitas Teknologi Yogyakarta (UTY)**  
*Fakultas Sains & Teknologi • Program Studi Informatika*  
*Semester Ganjil 2026/2027*

### Topik Kasus Nyata
* **Judul:** Analisis Opini Publik terhadap Korupsi Anggaran dan Manipulasi Laporan Berdasarkan Komentar Video YouTube
* **Sumber Data:** https://www.youtube.com/watch?v=ToZSRkAybKc
* **Jumlah Korpus:** 520 Data Komentar Bahasa Indonesia

---

### Struktur Berkas
* [`Tugas_Kelompok_Pemrosesan_Teks.ipynb`](./Tugas_Kelompok_Pemrosesan_Teks.ipynb) : Notebook Google Colab / Jupyter lengkap yang mencakup 5 tahap text mining, ekstraksi regex, pemeliharaan negasi, stemming Sastrawi, 15 bigram teratas, dan 10 kolokasi PMI.
* [`korpus_komentar_clean.csv`](./korpus_komentar_clean.csv) : Berkas CSV korpus hasil ekstraksi dan praproses (520 ulasan bersih, teranonimkan dengan hash SHA-256).

---

### Ringkasan Metodologi
1. **Pengumpulan Data:** Scraping 520 ulasan komentar YouTube menggunakan `youtube-comment-downloader`.
2. **Anonimisasi Data:** Penyamaran identitas akun menggunakan enkripsi satu arah SHA-256 (`user_xxxxxxxx`).
3. **Ekstraksi Fitur Regex:** Deteksi URL, mention (@), hashtag (#), emoji, dan angka.
4. **Praproses Teks Multi-Tahap:**
   * Case folding
   * Regex cleaning
   * Tokenisasi NLTK
   * Normalisasi slang (Leksikon 15.000 kata)
   * Stopword removal dengan **kata negasi dipertahankan** (*tidak, bukan, belum, kurang, jangan, tanpa, palsu*).
5. **Stemming & N-Gram:**
   * Stemming bahasa Indonesia dengan Sastrawi.
   * Ekstraksi 15 Bigram teratas (FreqDist).
   * Ekstraksi 10 Kolokasi PMI teratas (Pointwise Mutual Information dengan filter frekuensi $\ge 3$).
