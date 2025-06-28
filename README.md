# 🔍 Sistem CBR untuk Rekomendasi Putusan Hukum Perbankan

Repositori ini berisi implementasi sistem *Case-Based Reasoning* (CBR) untuk membantu pencarian dan prediksi putusan hukum dalam domain **perkara perbankan**. Sistem ini dibangun menggunakan Python dan library modern seperti `transformers`, `scikit-learn`, dan `BeautifulSoup`.

## 🧩 Struktur Proyek

```
cbr_banking/
├── data/
│   ├── raw/               # File .txt hasil ekstraksi dari PDF
│   ├── processed/         # Dataset CSV siap olah (cases.csv)
│   └── eval/              # Query dan hasil evaluasi
├── logs/
│   └── cleaning.log       # Log pembersihan teks
├── 01_scraper.py          # Script scraping & ekstraksi
├── 02_representation.py   # Ekstraksi metadata & fitur
├── 03_retrieval.py        # Implementasi model retrieval
├── 04_predict.py          # Fungsi prediksi putusan
└── 05_evaluation.py       # Evaluasi kinerja model
```

## 🔧 Instalasi

1. Clone repo:

```bash
git clone https://github.com/username/cbr_banking.git
cd cbr_banking
```

2. Buat virtual environment (opsional):

```bash
python -m venv env
source env/bin/activate  # Windows: env\Scripts\activate
```

3. Install dependensi:

```bash
pip install -r requirements.txt
```

## 🚀 Menjalankan Pipeline End-to-End

### Tahap 1 – Membangun Case Base

```bash
python 01_scraper.ipynb
```
Scraping dokumen PDF putusan MA, membersihkan, dan menyimpan dalam folder `data/raw`.

### Tahap 2 – Representasi Kasus

```bash
python 02_representation.ipynb
```
Mengambil metadata dari file txt dan menyimpannya ke `cases.csv`.

### Tahap 3 – Retrieval

```bash
python 03_retrieval.ipynb
```
Membangun model TF-IDF atau IndoBERT, lalu mencari kasus yang paling mirip.

### Tahap 4 – Prediksi

```bash
python 04_predict.ipynb
```
Mengambil amar putusan dari top-5 hasil retrieval dan menyimpulkan prediksi.

### Tahap 5 – Evaluasi Model

```bash
python 05_evaluation.ipynb
```
Menghitung akurasi, precision, recall, dan F1-score dari sistem retrieval.

## 🧪 Contoh Query

```json
{
  "query": "penipuan dana nasabah oleh teller bank",
  "ground_truth": [5]
}
```

## Link Colab
Kode program tersebut di buat di google colab yang tersimpan di dalam google drive pada link berikut
https://drive.google.com/drive/folders/1AwyPkCx54Cw3DErbN9SsiAM-_mxN6N6q?usp=sharing