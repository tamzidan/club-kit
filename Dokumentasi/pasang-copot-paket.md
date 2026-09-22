# Pasang / copot paket (fitur "seperti Lego")

Setiap fitur TZ Club Kit adalah **paket** mandiri: satu folder di `ServerStorage > TZKit > Packages`.
Kit dirancang supaya paket bisa dinyalakan, dimatikan, atau dihapus sepenuhnya tanpa merusak
paket lain atau perlu mengedit kode.

## Cara 1 — Matikan sementara (paling gampang, bisa dinyalakan lagi kapan saja)

1. Buka **ReplicatedStorage > TZKit > Settings > Features**.
2. Ubah baris paket yang mau dimatikan jadi `false`, misalnya:
   ```lua
   Music = false,
   ```
3. Selesai — Play ulang. Semua UI/tab yang berasal dari paket itu otomatis hilang, tanpa error dari
   paket lain.
4. Untuk menyalakan lagi, ubah kembali ke `true` (atau hapus barisnya — fitur yang tidak ada di
   daftar `Features` otomatis MENYALA selama foldernya masih terpasang).

## Cara 2 — Copot sepenuhnya (menghapus fitur dari game)

1. Hapus folder paketnya di `ServerStorage > TZKit > Packages > <Nama>`.
2. Play ulang untuk memastikan tidak ada error.

Paket lain yang **opsional** terhadap paket yang dihapus (lihat tabel "Bergantung pada" di
[konfigurasi.md](konfigurasi.md)) otomatis menyesuaikan diri: tab/notifikasi yang berasal dari
paket itu hilang sendiri, paket lainnya tetap jalan normal. Contoh: mencopot **RobuxDonate** membuat
tab "Fake Donate" & notifikasi sultan di Admin Panel ikut hilang, tapi Admin Panel sendiri tetap
berjalan.

## Paket yang TIDAK boleh dicopot sendirian

Beberapa paket dibutuhkan paket lain secara wajib (bukan opsional):

| Kalau mau copot... | ...harus ikut copot juga |
|---|---|
| NoCollision | Carry (butuh NoCollision) |

Kalau mencopot paket yang masih dibutuhkan paket lain tanpa ikut mencopot paket yang bergantung
padanya, Kit tetap berjalan (paket yang bergantung itu otomatis dilewati/dimatikan dan tercatat di
Output), tapi lebih rapi kalau keduanya dicopot bersamaan.

## Yang TIDAK boleh dicopot / diubah sama sekali

- **`ServerScriptService.TZKit.Boot`** dan **`ServerScriptService.TZKit.Kernel`** — ini gerbang
  utama semua fitur. Menghapusnya = mematikan seluruh Kit, bukan mempercepat boot.
- **`ReplicatedStorage.TZKit.ClientKernel`** dan **`StarterPlayer.StarterPlayerScripts.TZKitClient`**
  — titik masuk sisi client, sama seperti di atas.
- **`ServerStorage.TZKit.ServerSettings`** — berisi license key kamu.

## Menambah fitur sendiri di atas Kit

Kamu boleh membuat paket sendiri di luar 23 paket bawaan (mengikuti Manifest/Config/Server/Client
seperti paket yang ada) selama tidak mengubah kode paket bawaan atau Kernel. Ini di luar cakupan
dukungan TZ, tapi tidak melanggar lisensi (lihat [EULA.md](EULA.md) butir 4).
