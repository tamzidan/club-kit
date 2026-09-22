# Instalasi TZ Club Kit

Kit ini dikirim sebagai **beberapa file `.rbxm`**, bukan satu file `.rbxl` utuh — satu file per
tempat (service) di Roblox Studio. Kamu pasang di game kamu sendiri (baru atau yang sudah ada),
tanpa perlu menggabungkan dua Studio secara manual.

| File | Dipasang ke |
|---|---|
| `ReplicatedStorage.rbxm` | Explorer > **ReplicatedStorage** |
| `ServerScriptService.rbxm` | Explorer > **ServerScriptService** |
| `ServerStorage.rbxm` | Explorer > **ServerStorage** |
| `StarterPlayerScripts.rbxm` | Explorer > **StarterPlayer > StarterPlayerScripts** |
| `Workspace.rbxm` | Explorer > **Workspace** |
| `Lighting.rbxm` *(opsional)* | Explorer > **Lighting** — suasana lampu/langit bawaan club |

Kode di dalamnya sudah terlindungi (obfuscated/dikecilkan) — kamu tidak perlu dan tidak bisa
mengedit kodenya, hanya **Config** dan **Theme** yang memang dibuat untuk diedit (lihat
[konfigurasi.md](konfigurasi.md) dan [kustomisasi-tema.md](kustomisasi-tema.md)).

## 1. Pasang tiap file `.rbxm`

Ulangi langkah ini untuk **setiap** file di tabel atas:

1. Di Studio, buka tab **Explorer** (View > Explorer kalau belum kelihatan).
2. Klik objek tujuannya (lihat kolom "Dipasang ke" di tabel). Untuk `StarterPlayerScripts.rbxm`,
   klik dua kali untuk membuka **StarterPlayer**, lalu klik **StarterPlayerScripts** di dalamnya —
   bukan StarterPlayer itu sendiri.
3. Klik kanan objek itu > **Insert from File...**
4. Pilih file `.rbxm` yang sesuai.
5. Isinya langsung muncul sebagai anak baru dari objek yang kamu klik — **tidak perlu Ungroup**,
   Studio tidak membungkusnya dengan Model tambahan.

> Kalau menu klik-kanan kamu tidak punya "Insert from File...", cara lain: buka file `.rbxm` itu
> sekali (Roblox Studio bisa membukanya sebagai jendela Studio tersendiri), lalu **drag** objek dari
> Explorer jendela itu ke posisi yang sama di Explorer game kamu.

Setelah keenam (atau kelima, kalau Lighting dilewati) file terpasang, Explorer game kamu akan
punya:

```
ReplicatedStorage > TZKit
ServerScriptService > TZKit
ServerStorage > TZKit
StarterPlayer > StarterPlayerScripts > TZKitClient
Workspace > (Baseplate, CLUB KIT BY TZ, Donate, Panggung, RunningText, SpawnLocation,
             TZLeaderboard, TZVIPZones, TZZone)
Lighting > (Atmosphere, Sky, Bloom, DepthOfField, SunRays)   -- kalau dipasang
```

Kalau game kamu sudah punya `Baseplate`/`SpawnLocation` sendiri dan sekarang jadi dobel, hapus
salah satu (part yang lama atau yang baru, terserah kamu).

## 2. (Opsional) Samakan suasana lampu seperti demo

`Lighting.rbxm` cuma memasang objek anak (Atmosphere, Sky, dst). Beberapa pengaturan lampu adalah
**properti** `Lighting` sendiri (bukan objek anak), jadi tidak ikut file `.rbxm` dan harus diisi
manual. Buka **View > Command Bar**, tempel baris ini sekali, lalu Enter:

```lua
game.Lighting.ClockTime = 14.5
game.Lighting.Brightness = 3
game.Lighting.Ambient = Color3.fromRGB(70, 70, 70)
game.Lighting.OutdoorAmbient = Color3.fromRGB(70, 70, 70)
```

Lewati langkah ini kalau kamu mau pakai pengaturan lampu game kamu sendiri.

## 3. Isi license key

1. Buka **ServerStorage > TZKit > ServerSettings** (ModuleScript).
2. Isi `LicenseKey` dengan key yang diberikan penjual (formatnya `lic_...`), contoh:
   ```lua
   return {
       LicenseKey = "lic_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
   }
   ```
3. **Jangan membagikan key ini ke siapa pun.** Key hanya boleh dibaca server (modul ini di
   `ServerStorage`, tidak pernah terkirim ke client), dan terikat ke akun/grup pemilik game kamu.
4. Kit ini **harus dipublish** ke Roblox (bukan cuma dibuka di Studio) supaya lisensi bisa
   diverifikasi ke server TZ. Di Studio yang belum dipublish, Kit tetap bisa dites (lihat bagian 5)
   tapi fitur yang butuh koneksi langsung ke TZ (donasi Saweria asli) belum aktif.

## 4. Isi ID yang wajib diisi sendiri

Beberapa fitur perlu **Game Pass** / **Developer Product** buatanmu sendiri (harga, produk, dan
uangnya masuk ke akunmu, bukan ke TZ). Kit ini tidak bisa membuatkannya otomatis.

1. Buat Game Pass/Developer Product yang perlu di **Creator Dashboard** kamu.
2. Isi ID-nya di Config paket terkait (lihat tabel di [konfigurasi.md](konfigurasi.md) untuk lokasi
   tiap paket). Ringkasnya:
   - **VIP**: `Packages/VIP/Config` → `GamePass.VIP`, `GamePass.VVIP`, `DevProduct.VIP`, `DevProduct.VVIP`
   - **RobuxDonate**: `Packages/RobuxDonate/Config` → `Levels[i].ProductId` per nominal
   - **Emoji**: `Packages/Emoji/Config` → `GamePassId`
   - **Overhead** (Custom Title): `Packages/Overhead/Config/CustomTitle` → `PRODUCT_ID`
3. Field yang belum diisi (masih `0`) **tidak bikin error** — tombolnya saja belum bisa dipakai
   sampai diisi. Buka Studio, tekan **F9 > Output**, cari baris `[TZKit:SetupCheck]` untuk daftar
   lengkap yang masih perlu diisi (hanya muncul di Studio).

## 5. Uji coba di Studio

1. Tekan **Play** (F5) di Studio.
2. Cek Output: harus ada baris `[TZKit:Kernel] N paket aktif: ...` tanpa error di atasnya.
3. Di Studio yang belum dipublish, Kit otomatis jalan dalam **mode pengembangan** (semua fitur bisa
   dites tanpa koneksi ke server TZ, kecuali Saweria — dibiarkan mati sampai game dipublish).
   `[TZKit:SetupCheck]` menampilkan daftar hal yang masih perlu diisi.
4. Coba menu utama (tombol **M** atau ikon menu di topbar kanan atas), admin panel (kalau kamu
   terdaftar sebagai Owner/staff — lihat [konfigurasi.md](konfigurasi.md) bagian Roles), dan fitur
   lain yang kamu pakai.

## 6. Publish & pantau

1. Setelah Config diisi dan diuji, publish ke Roblox (File > Publish to Roblox, atau update kalau
   sudah pernah publish).
2. Di server live, Kit memverifikasi lisensi ke server TZ secara otomatis dan mengecek ulang
   berkala. Kalau ada masalah (key salah, jaringan bermasalah), pesannya muncul di Output server —
   lihat [faq.md](faq.md).
3. Sound/animasi tertentu bisa gagal dimuat kalau belum diizinkan Roblox untuk game kamu — lihat
   [aset-pihak-ketiga.md](aset-pihak-ketiga.md).

## Selanjutnya

- [konfigurasi.md](konfigurasi.md) — aturan Config & daftar tiap paket
- [kustomisasi-tema.md](kustomisasi-tema.md) — ganti warna, font, preset tampilan
- [pasang-copot-paket.md](pasang-copot-paket.md) — nyalakan/matikan/copot fitur
- [faq.md](faq.md) — masalah umum
