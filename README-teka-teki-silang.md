# Game Teka‑Teki Silang (1 Menurun, 2 Mendatar)

File utama: **`teka-teki-silang.html`**

## Cara main
1. Buka `teka-teki-silang.html` di browser (Chrome/Edge/Firefox).
2. Isi huruf di kotak putih.
3. Klik **Cek Jawaban** untuk memeriksa.

## Cara mengubah pertanyaan & jawaban
Di halaman game, pada bagian **Ubah Soal & Jawaban**:
- Ubah teks pertanyaan (clue)
- Ubah jawaban (huruf **A–Z**, minimal 2 huruf)
- (Opsional) Ubah **ukuran grid** dan **posisi start** (baris/kolom) untuk setiap kata
- Klik **Terapkan Perubahan**

Catatan:
- Posisi start di editor memakai angka **1–N** (untuk manusia). Di JSON, `row/col` disimpan **mulai 0**.
- Kalau kata-kata saling berpotongan, huruf di titik perpotongan harus sama. Jika tidak, game akan menolak perubahan dan menampilkan pesan error.
- Pastikan kata tidak keluar dari batas grid.

## Cara share link puzzle (publik)
1. Ubah clue/jawaban sesuai keinginan, lalu klik **Terapkan Perubahan**
2. Klik **Buat Link Share**
3. Link akan tersalin ke clipboard (atau muncul prompt untuk disalin)

Link share menyimpan konfigurasi puzzle di bagian URL `#p=...`.

## Mengubah letak angka/posisi (advanced via JSON)
Di textarea JSON, kamu bisa mengubah bagian `layout`:

```json
{
  "layout": {
    "size": 5,
    "across": [
      { "num": 1, "row": 1, "col": 0 },
      { "num": 2, "row": 3, "col": 0 }
    ],
    "down": [{ "num": 1, "row": 0, "col": 2 }]
  }
}
```

- `num` adalah angka yang tampil di kotak start.
- `row/col` mulai dari **0** (0-indexed).
- Versi saat ini tetap **2 mendatar + 1 menurun** (untuk UI sederhana). Kalau kamu mau versi “banyak kata”, bilang saja—saya bisa upgrade.

## Cara mempublikasikan (supaya link bisa diakses publik)
Ini adalah web statis (cukup 1 file HTML), jadi bisa dipublish di mana saja:

### Opsi A — GitHub Pages (gratis)
1. Buat repo GitHub baru (mis. `tts-harian`)
2. Upload `teka-teki-silang.html` ke repo (boleh rename jadi `index.html`)
3. Aktifkan **Settings → Pages → Deploy from branch**
4. Setelah live, buka URL GitHub Pages kamu, lalu pakai tombol **Buat Link Share** untuk membuat link puzzle yang bisa dibagikan.

### Opsi B — Netlify / Vercel (gratis)
1. Drag & drop file `teka-teki-silang.html` (atau folder berisi file itu)
2. Setelah live, share URL-nya.
