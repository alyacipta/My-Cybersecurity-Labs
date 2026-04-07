# 🚩 picoCTF Challenge: Hidden in Plainsight
**Status:** Completed ✅
**Date:** April 7, 2026
**Category:** Forensics

## 📝 Deskripsi Tantangan
Diberikan sebuah file gambar JPG yang terlihat biasa saja. Tugasnya adalah menemukan *payload* tersembunyi di dalam file tersebut yang berisi Flag.

## 🔍 Metodologi & Logika
Tantangan ini berfokus pada teknik **Steganography** sederhana:
1. **File Inspection:** Memeriksa struktur file gambar untuk melihat apakah ada data tambahan yang menempel.
2. **String Searching:** Mencari pola teks spesifik (picoCTF{...}) di dalam konten mentah file gambar.
3. **Extraction:** Mengidentifikasi data yang disisipkan di luar area data visual gambar (seperti pada metadata atau *trailing data*).

## 💡 Key Insight
Saya belajar bahwa "melihat" sebuah file tidak cukup hanya dengan membukanya secara visual. Seorang *forensic investigator* harus melihat "ke dalam" struktur data file untuk menemukan jejak yang disembunyikan.
