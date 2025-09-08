# capstone-summarization
# Capstone Project: Ringkasan Rapat Otomatis dengan IBM Granite

## Deskripsi Proyek
Proyek ini bertujuan untuk menghasilkan ringkasan otomatis dari transkrip rapat kerja menggunakan model AI IBM Granite (granite-3.3-8b-instruct).

## Latar Belakang
Rapat kerja seringkali menghasilkan dokumen panjang yang sulit dibaca cepat oleh stakeholder. Dengan bantuan AI, proses ini bisa diotomatisasi untuk efisiensi dan kejelasan informasi.

## Dataset
Dataset:
[Transkrip Rapat (meeting_transcript.txt)](https://drive.google.com/file/d/126w9GOIH5WT7z-wozmXgl3TxcUR0gkjV/view?usp=sharing)


Isi transkrip:
```
Rapat dimulai pukul 09.00 membahas penurunan penjualan produk digital Q2 sebesar 15%.
Tim penjualan menyarankan promosi flash sale dan evaluasi strategi distribusi.
Tim marketing mengusulkan kampanye media sosial dengan pendekatan kolaborasi influencer.
Manajer produk mencatat banyak keluhan soal performa fitur baru dan akan koordinasi dengan tim engineering.
Diputuskan bahwa kampanye digital dimulai tanggal 15 September, dan laporan keluhan diselesaikan sebelum akhir bulan
```

## Prompt yang Digunakan
```
Ringkas rapat ini secara sangat singkat dan padat.

Gunakan format berikut:
1. Poin Penting: Maksimal 2 bullet point
2. Keputusan: Maksimal 2 bullet point
3. Tindak Lanjut: Maksimal 2 bullet point

Gunakan kalimat pendek, to the point, dan hindari penjelasan berulang.
```

## Parameter Model
```python
{
  "top_k": 5,
  "top_p": 0.5,
  "max_tokens": 40,
  "min_tokens": 20,
  "repetition_penalty": 1.5,
  "stopping_criteria": "length",
  "stopping_sequence": "\n\n"
}
```

## ✅ Hasil Ringkasan (Final Output)
```markdown
1. Poin Penting:
- Penurunan penjualan digital Q2 sebesar 15%
- Masalah performa fitur baru dan keluhan pengguna

2. Keputusan:
- Implementasi promosi flash sale dan evaluasi distribusi
- Kampanye media sosial dengan influencer kolaborasi

3. Tindak Lanjut:
- Tim engineering akan koordinasi dengan tim produk untuk memecahkan masalah fitur baru
- Kampanye digital dimulai 15 September, laporan keluhan selesai sebelum akhir bulan
```

## Insight
Penggunaan AI untuk summarization mempercepat proses pengambilan keputusan, menghemat waktu stakeholder, dan mengurangi risiko miskomunikasi dalam organisasi.

## Tools
- IBM Granite (via Replicate API)
- Google Colab
- Python
