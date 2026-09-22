# Aset (suara/animasi/gambar) yang mungkin perlu diizinkan atau diupload ulang

Beberapa suara, animasi, dan gambar di Config Kit ini diupload dari akun TZ sendiri. Sejak
kebijakan Roblox soal aset audio/animasi, **aset yang diupload satu akun tidak otomatis bisa
dipakai di game akun lain** — harus diizinkan lewat Creator Hub, atau diupload ulang oleh pemilik
game.

Kalau kamu menemukan error seperti **"The experience doesn't have access permission"** atau suara/
animasi yang tidak jalan, ini penyebabnya — bukan bug di Kit.

## Cara memperbaiki (pilih salah satu)

1. **Paling cepat:** hubungi TZ (lihat [EULA.md](EULA.md) butir 7), TZ akan memberi izin akses aset
   itu ke game/experience kamu lewat Creator Hub (Aset > Permissions). Butuh **Universe ID** atau
   **Place ID** game kamu.
2. **Mandiri:** upload ulang aset yang sama (atau penggantinya) ke akun/grup kamu sendiri di
   [Creator Hub](https://create.roblox.com), lalu ganti ID-nya di Config paket terkait (lihat tabel
   di bawah untuk lokasi tiap ID). Untuk animasi/suara publik, kamu juga bisa mengganti dengan ID
   yang sudah tersedia bebas di catalog Roblox.

## Aset yang sudah dikonfirmasi bermasalah (diuji 2026-09)

| Aset | Dipakai di | Config |
|---|---|---|
| `rbxassetid://75017133469714` (suara) | Emoji slot 3 | `Packages/Emoji/Config` |
| `rbxassetid://139097699311164` | Belum diketahui lokasinya | — |
| `rbxassetid://105564016306662` (DJ Pergilah Kau) | Playlist musik | `Packages/Music/Config` |
| `rbxassetid://137370132182730` (Ada Yang Marah) | Playlist musik | `Packages/Music/Config` |
| `rbxassetid://131264633090522` (Humko Humise Chura Lo) | Playlist musik | `Packages/Music/Config` |

## Kategori yang berisiko sama (belum semuanya diuji satu-satu)

- **Suara UI** (klik, hover, buka/tutup panel, error) di `ReplicatedStorage > TZKit > Settings >
  UISound` — 5 suara, semua diupload dari akun TZ.
- **Animasi Smite** (efek donasi Saweria melempar target ke udara) di
  `Packages/Saweria/Config` → `GlobalEffects.SmiteAnimationId`. Kalau animasinya gagal dimuat, efek
  tetap jalan dengan timer cadangan (tidak error, hanya animasinya tidak presisi).
- **Daftar Dance** (~220 animasi) di `Packages/Dance/Config`. Sebagian besar adalah animasi dance
  populer yang beredar luas dan biasanya sudah publik, tapi belum semuanya diuji satu per satu ke
  akun TZ. Kalau ada dance tertentu yang animasinya tidak jalan (karakter diam saat dance dipilih),
  ganti ID-nya mengikuti format di baris paling atas Config:
  ```lua
  {name = "Nama Dance", id = "rbxassetid://123456789"},
  ```
- **Playlist musik** (37 lagu) di `Packages/Music/Config` — 3 di antaranya sudah dikonfirmasi
  bermasalah (lihat tabel di atas); lagu lain kemungkinan aman tapi belum diuji semuanya.

## Yang TIDAK termasuk masalah ini

Gambar ikon/logo yang dipakai UI (topbar, menu, badge) umumnya aset publik/katalog Roblox atau
digambar langsung dari kode (vector), jadi biasanya tidak kena masalah izin akses ini.
