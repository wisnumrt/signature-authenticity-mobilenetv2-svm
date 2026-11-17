# signature-authenticity-mobilenetv2-svm
Deteksi keaslian tanda tangan (asli vs palsu) dengan ekstraksi fitur MobileNetV2 dan klasifikasi SVM

# SIGNATURE AUTHENTICITY DETECTION USING MOBILENETV2 FEATURE EXTRACTION AND SVM

Tugas UAS Pengenalan Pola (UAS-C081)

## Tim
| Nama | NPM |
|---|---|
| Hapsoro Wisnu Murti | 22081010073 |
| Frendiya Mei Sindy | 22081010078 |
| Ama Maulidatul Khairah | 22081010329 |

## Deskripsi
Sistem klasifikasi biner (asli / palsu) pada citra tanda tangan. MobileNetV2 (pretrained ImageNet, tanpa top layer, global average pooling) dipakai sebagai feature extractor (vektor 1280 dimensi), lalu diklasifikasi dengan SVM kernel RBF.

## Pipeline
Pengumpulan data → Preprocessing → Ekstraksi fitur MobileNetV2 → Klasifikasi SVM → Evaluasi

## Hasil (data uji, 339 citra)
| Kelas | Precision | Recall | F1 |
|---|---|---|---|
| Asli | 0,98 | 0,69 | 0,81 |
| Palsu | 0,71 | 0,99 | 0,82 |

Akurasi 82%. Confusion matrix: `[[131, 60], [2, 146]]`.
Model sangat sensitif terhadap tanda tangan palsu, tetapi masih sering
salah menandai tanda tangan asli sebagai palsu (60 kasus).

## Cara menjalankan
1. Buka notebook di Google Colab.
2. Siapkan dataset (lihat `data/README.md`) dan sesuaikan `data_dir`.
3. Jalankan seluruh sel secara berurutan.

## Library
tensorflow, scikit-learn, numpy, pandas, matplotlib, seaborn

## Link
- [Notebook Colab](https://colab.research.google.com/drive/116eSCJuSgHnyDOMlW5AMlfv7DmV7dlms?usp=sharing)
- Laporan: `docs/Laporan_Akhir.pdf`
- PPT dan video presentasi: (isi dari lampiran laporan)
