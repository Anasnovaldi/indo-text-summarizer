# Peringkas Teks Bahasa Indonesia (Beam Search)

Program CLI sederhana untuk meringkas paragraf berbahasa Indonesia menggunakan model `cahya/bert2bert-indonesian-summarization` dari Hugging Face, dengan metode **beam search** dan panjang ringkasan (minimal & maksimal kata) yang bisa diatur sendiri oleh pengguna.

## Fitur

- Input paragraf bebas lewat terminal
- Pengguna bisa menentukan batas minimal dan maksimal jumlah kata hasil ringkasan
- Menggunakan beam search (`num_beams=5`) untuk hasil ringkasan yang lebih optimal
- Validasi input (panjang paragraf minimal, batas kata tidak boleh terbalik)

## Instalasi

1. Clone repo ini:
   ```bash
   git clone <url-repo-kamu>
   cd <nama-folder>
   ```

2. (Opsional tapi disarankan) Buat virtual environment:
   ```bash
   python -m venv venv
   venv\Scripts\activate      # Windows
   source venv/bin/activate   # Mac/Linux
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Cara Menjalankan

```bash
python main.py
```

Ikuti instruksi di terminal:
1. Masukkan paragraf yang ingin diringkas (minimal 20 kata)
2. Masukkan batas minimal kata hasil ringkasan
3. Masukkan batas maksimal kata hasil ringkasan

## Catatan

- Model (~1GB) akan otomatis terunduh dari Hugging Face Hub saat pertama kali dijalankan, lalu tersimpan di cache lokal untuk pemakaian berikutnya.
- Hindari mengisi `minimal_length` yang mendekati atau melebihi jumlah kata paragraf sumber, karena dapat menyebabkan model menghasilkan ringkasan yang tidak akurat (halusinasi).

## Teknologi

- [Transformers](https://huggingface.co/docs/transformers) (Hugging Face)
- [PyTorch](https://pytorch.org/)
- Model: [`cahya/bert2bert-indonesian-summarization`](https://huggingface.co/cahya/bert2bert-indonesian-summarization)
