# Konfigurasi paket

Setiap fitur (paket) TZ Club Kit punya folder sendiri di **ServerStorage > TZKit > Packages**.
Semua pengaturan yang boleh dan aman diedit ada di file **Config** (dan sub-folder `Config/` kalau
ada) di dalam folder paket itu — kode di `Server`/`Client`/`Shared` tidak perlu dan tidak bisa
diedit (terlindungi).

## Aturan umum

- **Config = data saja.** Tidak ada kode di dalamnya, jadi aman diedit siapa pun tanpa merusak
  sistem — paling parah salah isi field, dan itu pun sudah diperiksa otomatis (lihat SetupCheck di
  bawah).
- **Warna** ditulis teks hex, misalnya `"#FF3232"`. Untuk warna keseluruhan tampilan (bukan per
  paket), lihat [kustomisasi-tema.md](kustomisasi-tema.md).
- **Tombol keyboard** ditulis nama huruf/tombolnya, misalnya `"E"`.
- **ID aset** (gambar/suara/animasi) ditulis `"rbxassetid://123456789"`. ID harus milik akun/grup
  pemilik game ini, atau sudah diberi izin akses — lihat [aset-pihak-ketiga.md](aset-pihak-ketiga.md)
  kalau muncul error "doesn't have access permission".
- **ID Game Pass / Developer Product** ditulis angka biasa. `0` berarti belum diisi — fiturnya tetap
  jalan, hanya tombol beli/klaimnya belum bisa dipakai.
- Setiap file Config punya **komentar berbahasa Indonesia** di setiap bagian yang menjelaskan
  persis apa yang diedit dan efeknya — baca komentar di file sebelum mengubah nilai.

## Pemeriksaan otomatis (SetupCheck & ConfigCheck)

- Saat Kit menyala, isian Config diperiksa otomatis. Isian yang salah tipe (misalnya teks di field
  yang harus angka) **tidak menghentikan Kit** — paketnya tetap jalan memakai nilai bawaan, dan
  pesannya muncul di Output sebagai `[TZKit:Config]`.
- Khusus di Studio, `[TZKit:SetupCheck]` menampilkan daftar lengkap yang masih perlu diisi (ID Game
  Pass/Product yang masih `0`, HTTP belum aktif, dsb.) setiap kali kamu menekan Play.

## Menyalakan / mematikan fitur

Lihat [pasang-copot-paket.md](pasang-copot-paket.md).

## Daftar paket

| Paket | Fungsi | Bergantung pada |
|---|---|---|
| AdminPanel | Panel kontrol staff; tab-nya datang dari paket lain (Music Settings, Fake Donate, dst.) | — |
| Boards | Papan geser staff & papan gambar/iklan di map | — |
| Carry | Gendong/peluk pemain lain | NoCollision |
| Cinematic | Kamera cinematic untuk semua pemain (dipicu paket lain, mis. Saweria) | opsional: MainMenu |
| Commands | Perintah pemain di tab Commands & lewat chat | opsional: MainMenu |
| Dance | Panel dance & pose | — |
| Emoji | Sticker di atas kepala pemain lewat tool | — |
| GlobalFX | Efek untuk semua pemain dari Admin Panel (Fly, Shake, Fire, Crown, Aura) | — |
| Hotbar | Pengganti backpack bawaan Roblox (grid + panel inventory) | — |
| Level | Naik level dari lama bermain + papan waktu main | — |
| Lights | Jembatan ke GLights (Gybasoft) — **GLights dipasang sendiri**, lihat [instalasi.md](instalasi.md) | — |
| Love | "Love" antar pemain + papan Top Loved | — |
| MainMenu | Menu utama (tombol M / ikon topbar); host tab dari paket lain | — |
| Music | Klub musik: playlist, genre, DJ/EQ, panel Account | — |
| NoCollision | Tabrakan antar pemain | — |
| Overhead | Nama/rank/title di atas kepala pemain | opsional: VIP, RobuxDonate |
| Players | Popup menu pemain, profil, komunitas; host aksi dari paket lain | — |
| RobuxDonate | Donasi Robux lewat Developer Product + papan Top Donate | opsional: AdminPanel (notif sultan) |
| RunningText | Teks berjalan di papan LED | — |
| Saweria | Donasi uang asli lewat Saweria (dijual terpisah juga) | — |
| ServerList | Tab Servers di menu (server ini + pindah server) | opsional: MainMenu |
| Sky | Pilihan langit & hujan per pemain | opsional: MainMenu |
| VIP | Status VIP/VVIP, tool khusus, zona | — |

"Bergantung pada" yang **bukan** opsional (mis. Carry → NoCollision) berarti paket itu butuh
paket satunya tetap terpasang. Yang **opsional** aman dicopot; fitur yang menempel di sana (tab,
notifikasi) otomatis hilang sendiri — lihat [pasang-copot-paket.md](pasang-copot-paket.md).

## Siapa yang jadi admin / staff

Diatur di **ReplicatedStorage > TZKit > Settings > Roles**, satu tempat untuk semua paket (Admin
Panel, GlobalFX, overhead rank, dst.). Pemilik game otomatis jadi role pertama (Owner). Detail
lengkap ada di komentar file `Roles.luau` itu sendiri.

## Lisensi & data rahasia

**ServerStorage > TZKit > ServerSettings** menyimpan `LicenseKey` — lihat
[instalasi.md](instalasi.md) bagian 2. Untuk paket Saweria, link Saweria kamu sendiri diisi di
`Packages/Saweria/Config` (`SaweriaLink`).
