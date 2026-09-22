# Perjanjian Lisensi Pengguna Akhir (EULA) — TZ Club Kit

Berlaku sejak versi 2.0.0. Bahasa Indonesia adalah versi yang mengikat.

Dengan membuka, memasang, atau menggunakan TZ Club Kit ("Kit"), kamu ("Pembeli") setuju dengan
ketentuan di bawah ini. Kalau tidak setuju, jangan gunakan Kit ini dan hubungi TZ untuk pengembalian
dana sesuai kebijakan yang berlaku saat pembelian.

## 1. Pemberi lisensi & objek lisensi

Kit ini dijual oleh **TZ** ("Penjual", "TZ", "kami"). Yang dilisensikan adalah kode, aset, dan
dokumentasi di dalam file `.rbxm` yang dikirim ke Pembeli, KECUALI komponen pihak ketiga yang
disebut di [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) (lisensinya masing-masing berlaku
sendiri) dan aset yang menurut Config Kit harus di-upload ulang oleh Pembeli (lihat
[aset-pihak-ketiga.md](aset-pihak-ketiga.md)).

## 2. Lisensi yang diberikan

TZ memberi Pembeli lisensi **non-eksklusif, tidak bisa dipindahtangankan, dan terikat pada satu
license key** untuk:

1. Memasang dan menjalankan Kit di game (universe) milik akun atau grup Roblox yang **terdaftar**
   pada license key tersebut (lihat butir 3).
2. Mengubah Config, Theme, dan aset di dalam game itu untuk kebutuhan game tersebut.
3. Membuat game yang menghasilkan pendapatan (Game Pass, Developer Product, donasi) menggunakan Kit
   ini, selama Kit itu sendiri tidak dijual atau dibagikan ulang (lihat butir 4).

Lisensi ini **per pembelian**, bukan per game. Satu license key boleh dipakai di beberapa game milik
akun/grup yang sama (dengan batas wajar yang dicatat sistem TZ), tetapi tidak boleh dipakai oleh
pihak lain di luar akun/grup yang terdaftar.

## 3. Pendaftaran & verifikasi otomatis

- License key hanya berlaku untuk akun atau grup Roblox pemilik game (`owners`) yang didaftarkan TZ
  saat pembelian, dan terikat ke kit ini seperti tercatat di `ServerStorage.TZKit.ServerSettings`.
- Setiap kali Kit berjalan di server live, Kit menghubungi server lisensi TZ untuk memverifikasi
  key dan pemilik game secara otomatis. Ini **bukan pengawasan konten atau pemain**; yang dikirim
  hanya license key dan ID game (dipasang Roblox sendiri, bukan dari script).
- Kalau verifikasi gagal berulang kali (key salah, dicabut, atau game dipindah ke akun/grup yang
  tidak terdaftar), Kit berhenti menjalankan fitur-fiturnya sampai masalahnya selesai.
- Percobaan pemakaian di luar akun/grup yang terdaftar tercatat di sistem TZ dan bisa dipakai
  sebagai bukti pelanggaran (lihat butir 8).

## 4. Yang DILARANG

Pembeli **dilarang**:

1. Menjual kembali, menyewakan, atau membagikan (reshare) Kit ini — baik utuh maupun sebagian, baik
   gratis maupun berbayar — ke pihak lain di luar akun/grup yang terdaftar pada license key.
2. Mempublikasikan Kit (atau bagian mana pun dari kode/asetnya) sebagai model publik, "free model",
   atau melalui Creator Store / `require(assetId)` yang bisa diakses pihak lain.
3. Membongkar (reverse-engineer), mendekompilasi, atau mencoba membuka proteksi obfuscation pada
   bagian Kit yang di-obfuscate, kecuali sejauh hukum yang berlaku secara tegas mengizinkannya.
4. Menghapus, mengubah, atau menyamarkan pemberitahuan lisensi/hak cipta yang ada di file terbuka
   Kit ini, termasuk di [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
5. Mengklaim Kit ini (atau turunannya) sebagai karya asli milik sendiri untuk dijual atau dilisensikan
   ke pihak lain.
6. Memindahkan license key ke akun/grup lain tanpa persetujuan tertulis dari TZ.

Modifikasi Config, Theme, atau penambahan fitur sendiri di ATAS Kit ini untuk dipakai di game
Pembeli **diperbolehkan** dan tidak melanggar butir di atas.

## 5. Pencabutan lisensi

TZ berhak mencabut license key tanpa pengembalian dana penuh apabila Pembeli terbukti melanggar
butir 4, termasuk (tapi tidak terbatas pada) key yang dipakai di akun/grup yang tidak terdaftar
lebih dari sekali setelah diperingatkan, atau bukti Kit dibagikan/dijual ulang. Setelah key dicabut,
semua fitur Kit berhenti berjalan di server live sampai lisensi dipulihkan atau diganti.

## 6. Jaminan & tanggung jawab

- Kit ini diberikan "sebagaimana adanya" (as-is). TZ tidak menjamin Kit bebas bug 100% atau cocok
  untuk tujuan tertentu, tetapi berkomitmen memperbaiki masalah yang dilaporkan sesuai kewajaran.
- TZ tidak bertanggung jawab atas kerugian tidak langsung (kehilangan pendapatan, data pemain, dsb.)
  akibat penggunaan Kit ini, sejauh diizinkan hukum yang berlaku.
- Aset yang gagal dimuat karena masalah izin akses Roblox (lihat
  [aset-pihak-ketiga.md](aset-pihak-ketiga.md)) adalah tanggung jawab Pembeli untuk mengganti atau
  meminta izin akses, bukan cacat pada Kit.
- Pembeli bertanggung jawab menjaga kerahasiaan license key sendiri.

## 7. Dukungan & pembaruan

- TZ menyediakan pembaruan Kit dari waktu ke waktu. Server lisensi memberi tahu Kit saat versi baru
  tersedia (muncul di Output Studio: "Versi baru TZ Club Kit tersedia").
- Cakupan dukungan (durasi, saluran kontak) mengikuti kesepakatan saat pembelian.
- Kontak dukungan resmi: **[isi kontak TZ — Discord/email]**.

## 8. Pelanggaran & jalur hukum

TZ mencatat pemakaian license key per game (universe) dan menandai pemakaian di luar akun/grup
terdaftar sebagai pelanggaran. Bukti ini dapat dipakai untuk:

- mencabut license key yang bersangkutan (butir 5);
- mengajukan laporan DMCA ke Roblox terhadap game/tempat yang memuat Kit tanpa lisensi yang sah;
- upaya hukum lain yang tersedia berdasarkan hukum yang berlaku di Indonesia.

## 9. Lain-lain

- EULA ini berlaku untuk versi Kit yang sedang dipakai Pembeli beserta pembaruannya, kecuali TZ
  menerbitkan versi EULA baru yang secara eksplisit menggantikannya.
- Kalau ada bagian dari EULA ini yang dianggap tidak berlaku oleh pengadilan, bagian lainnya tetap
  berlaku.
- Pertanyaan soal lisensi ini bisa diajukan lewat kontak di butir 7.

© TZ. Seluruh hak cipta pada kode dan aset asli Kit ini dipegang TZ, kecuali komponen pihak ketiga
yang disebut di [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
