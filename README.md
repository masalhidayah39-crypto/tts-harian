# Math Fishing (Game Berhitung Memancing)

Game matematika berhitung bertema **memancing di sungai**: pemain yang **paling cepat menjawab benar** akan mendapat **+1 ikan**. Bisa dimainkan **lebih dari 2 orang** (multiplayer online via room).

## 1) Jalankan server (WebSocket)

Prasyarat: Node.js 18+.

```bash
cd math-fishing-game/server
npm install
npm start
```

Server default berjalan di port **8080**.

## 2) Main via browser (web)

Buka file ini di browser:

`math-fishing-game/web/index.html`

Lalu isi:
- **Nama**
- **Alamat server** (contoh: `ws://localhost:8080`)

Buat room → salin kode → teman join → host tekan **Mulai Game**.

## 3) Main via Android (APK dari source)

Folder Android project ada di:

`math-fishing-game/android/`

Langkah (Android Studio):
1. Open project `android/`
2. Tunggu Gradle sync selesai (Android Studio akan download Gradle yang dibutuhkan).
3. Run ke emulator / device.

Catatan koneksi server:
- **Emulator Android**: jika server jalan di PC yang sama, pakai `ws://10.0.2.2:8080`
- **HP fisik**: server harus bisa diakses dari HP (mis. hosting/VPS), pakai `ws://IP-ANDA:8080` atau (disarankan) `wss://domain-anda`

## Aturan game (MVP)
- Realtime: 1 soal muncul untuk semua pemain.
- Jawaban **pertama yang benar** mendapat 1 ikan.
- Timer per soal: **12 detik**.
- Total: **25 ronde**.
- **Level bertahap** (otomatis):
  - Level 1: +/− kecil
  - Level 2: +/− lebih besar
  - Level 3: campur ×/÷ (hasil bulat)

## Kustomisasi cepat
- Batas pemain per room: di client ada `maxPlayers: 4` (ubah di `web/app.js` dan/atau `android/.../app.js`).
- Jumlah ronde / timer: di `server/index.js` (lihat `12_000` dan `roundIndex >= 25`).

