# Changelog

Format versi: `MAJOR.MINOR.PATCH`. Kernel memberi tahu server kamu otomatis kalau ada versi baru
(lihat [faq.md](faq.md) bagian Update).

## 2.0.0 — Rilis pertama sebagai TZ Club Kit

Penulisan ulang penuh dari sistem-sistem TZ yang sebelumnya dijual/dipakai terpisah, digabung
menjadi satu kit modular.

**Arsitektur baru**
- Satu titik boot (`Kernel`) yang menjalankan semua fitur sebagai **paket** mandiri — bisa
  dipasang/dicopot tanpa mengedit kode (lihat [pasang-copot-paket.md](pasang-copot-paket.md)).
- Kustomisasi tampilan lewat **Theme** (satu tempat untuk semua warna/font) dan **Config** per
  paket (data murni, tidak ada kode) — lihat [kustomisasi-tema.md](kustomisasi-tema.md) dan
  [konfigurasi.md](konfigurasi.md).
- Verifikasi lisensi otomatis ke server TZ, dengan masa tenggang 72 jam saat server/jaringan
  bermasalah, dan cek ulang berkala supaya lisensi yang dicabut langsung berlaku di server yang
  sedang jalan.
- Kode server, Kernel, dan client dilindungi (obfuscated/dikecilkan) untuk mempersulit pembajakan.

**23 paket tersedia:** AdminPanel, Boards, Carry, Cinematic, Commands, Dance, Emoji, GlobalFX,
Hotbar, Level, Lights, Love, MainMenu, Music, NoCollision, Overhead, Players, RobuxDonate,
RunningText, Saweria, ServerList, Sky, VIP.

**Perubahan dari sistem lama (untuk yang sudah pernah pakai versi sebelumnya)**
- Semua Config lama (`TZStudioConfig`, `TZModules.Configuration`, `Donate.Config`,
  `TZ_Lights`, dsb.) digabung jadi satu Config per paket dengan lokasi konsisten.
- Semua Remote pindah ke bawah Kernel (`Runtime.Remotes.<Paket>`), tidak lagi tersebar di banyak
  folder.
- Nama variabel hasil decompile di menu lama ditulis ulang bersih.
- `ServerStorage.TZBackups` (source admin panel lama) tidak lagi ikut terkirim di file rilis.
- Panel bar playback admin di Music dihapus (tidak pernah dipakai).
- GLights (Gybasoft) tidak lagi ikut dikirim di dalam kit — dipasang sendiri dari Toolbox (lihat
  [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)).

**Diketahui perlu perhatian:** beberapa aset suara/animasi/lagu bawaan mungkin perlu diizinkan
ulang oleh TZ atau diupload ulang sendiri — lihat [aset-pihak-ketiga.md](aset-pihak-ketiga.md).
