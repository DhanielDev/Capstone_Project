# Capstone_Project
Analisis Sentimen Ulasan Film IMDB Menggunakan Model Granite 3.2 8B via Replicate API

# 🎬 Sentiment Analysis IMDB dengan IBM Granite 3.2 8B Instruct

Proyek ini melakukan **analisis sentimen ulasan film IMDB** menggunakan **LLM IBM Granite 3.2 8B Instruct** yang diakses melalui Replicate API, dengan evaluasi kinerja model berdasarkan **metrik klasik NLP** dan **analisis kualitas penjelasan**.

---

## 🚀 Fitur Utama
- **Dataset:** IMDB Movie Reviews (25.000+ ulasan, diambil subset untuk hemat token).
- **Model:** [`ibm-granite/granite-3.2-8b-instruct`](https://replicate.com/ibm-granite/granite-3.2-8b-instruct).
- **Klasifikasi Sentimen:**  
  - Positive 👍  
  - Negative 👎  
  - Mixed ⚖️ (opsional jika review mengandung pro & kontra kuat)
- **Evaluasi Kinerja:** Accuracy, Precision, Recall, F1-score, Confusion Matrix.
- **Evaluasi Kualitas Penjelasan:**  
  - **Relevance** → kesesuaian penjelasan dengan isi review (cosine similarity).  
  - **Clarity** → kemudahan dibaca & panjang penjelasan yang ideal.
- **Caching Prediksi** → menghindari penggunaan token berulang untuk review yang sama.
- **Output Lengkap ke CSV** untuk dokumentasi & laporan.

---

## 📂 Struktur Output
1. **`imdb_granite_predictions.csv`**  
   Cache hasil prediksi model (label, confidence, penjelasan).
2. **`imdb_granite_results_full.csv`**  
   Hasil lengkap dengan metrik tambahan:
   | review | ground_truth | pred_label | confidence | explanation | relevance | clarity |
3. **Ringkasan Kinerja (`summary`)**
   ```json
   {
     "model": "ibm-granite/granite-3.2-8b-instruct",
     "n_samples": 300,
     "accuracy": 0.85,
     "macro_precision": 0.9845169775227165,
     "macro_recall": 0.8496260683760684,
     "macro_f1": 0.9120876301882921,
     "avg_relevance": 0.5278750361471126,
     "avg_clarity": 0.4607278303044684
   }
