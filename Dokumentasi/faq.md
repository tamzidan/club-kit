# FAQ — pertanyaan umum

## Instalasi & setup

**Q: Kenapa dikirim 6 file `.rbxm` terpisah, bukan satu file `.rbxl`?**
Supaya kamu bisa memasang kit ini ke game yang sudah kamu buat/kembangkan sendiri, tanpa harus
menggabungkan dua Studio secara manual. Tiap file tinggal di-**Insert from File** ke service yang
namanya sama (lihat [instalasi.md](instalasi.md)) — tidak ada langkah gabung/pindah manual.

**Q: Klik kanan di Explorer tidak ada "Insert from File..."?**
Coba klik objek servicenya dulu (mis. klik `ReplicatedStorage`) baru klik kanan — menu ini hanya
muncul untuk objek yang bisa menampung instance lain. Kalau tetap tidak ada, buka file `.rbxm` itu
sebagai jendela Studio terpisah lalu drag isinya secara manual (lihat [instalasi.md](instalasi.md)).

**Q: Setelah pasang `Workspace.rbxm`, saya punya dua `Baseplate`/`SpawnLocation`?**
Wajar — game kamu sudah punya sendiri sebelumnya. Hapus salah satu (bebas mana yang dipertahankan).

**Q: Output menunjukkan `[TZKit:SetupCheck] N hal perlu dicek` — apa itu bahaya?**
Tidak. `SetupCheck` hanya muncul di Studio dan mendaftar hal yang *sebaiknya* diisi (ID Game Pass/
Product yang masih 0, HTTP belum aktif, dsb). Kit tetap berjalan normal; fitur yang ID-nya belum
diisi hanya tombolnya belum bisa dipakai. Lihat [instalasi.md](instalasi.md) bagian 3.

**Q: "Studio tanpa akses DataStore" — muncul di Output, apa perlu diperbaiki?**
Ini normal di Studio. Aktifkan lewat **Game Settings > Security > Enable Studio Access to API
Services** kalau kamu mau data (VIP, love, level, dst.) tersimpan permanen saat playtest. Tanpa
itu, data tersimpan sementara di memori selama sesi Play saja — tidak memengaruhi game yang sudah
dipublish (server live selalu punya akses DataStore).

**Q: Server list, MessagingService, atau lisensi online tidak jalan di Studio?**
Beberapa fitur (pindah server, verifikasi lisensi online) memang hanya aktif di server yang sudah
dipublish. Ini bukan bug — Roblox sendiri membatasi API ini di Studio.

## Lisensi

**Q: Apa arti pesan-pesan lisensi di Output?**

| Pesan | Artinya |
|---|---|
| `License key belum diisi...` | Isi `LicenseKey` di ServerSettings — [instalasi.md](instalasi.md) |
| `License key tidak dikenal...` | Key salah ketik, atau memang belum terdaftar — hubungi TZ |
| `Lisensi ini sudah dicabut...` | Key dicabut TZ (biasanya karena pelanggaran EULA) — hubungi TZ |
| `Game ini tidak dimiliki akun/grup yang terdaftar...` | Game kamu belum didaftarkan ke key ini, atau kepemilikan game sudah pindah ke akun lain — hubungi TZ untuk update |
| `Place belum dipublish...` | Publish dulu ke Roblox; sebelum itu Kit jalan dalam mode pengembangan Studio |
| `Allow HTTP Requests belum aktif...` | Aktifkan di Game Settings > Security |
| `Server lisensi tidak bisa dihubungi...` | Gangguan jaringan sementara; Kit memakai lisensi valid terakhir sampai 72 jam sebelum berhenti (lihat di bawah) |

**Q: Internet/server TZ sempat down, apa game langsung berhenti?**
Tidak. Kit menyimpan hasil verifikasi valid terakhir dan tetap berjalan sampai **72 jam** meski
server lisensi tidak terjangkau, selama Allow HTTP Requests tetap aktif. Setelah itu (atau kalau
HTTP dimatikan), Kit berhenti sampai bisa menghubungi server lagi.

**Q: Saya pindahkan game ke akun/grup lain, apa yang terjadi?**
Lisensi terikat akun/grup yang didaftarkan saat pembelian. Kalau kepemilikan game pindah, hubungi
TZ untuk update daftar akun/grup pada key kamu — lihat [EULA.md](EULA.md) butir 3 & 7. Sebelum
diupdate, Kit akan menampilkan "Game ini tidak dimiliki akun/grup yang terdaftar" dan berhenti.

**Q: Donasi Saweria saya tidak masuk saat masih di Studio (belum publish)?**
Memang begitu — donasi Saweria asli baru aktif setelah game dipublish (server TZ perlu tahu game
ini benar milik kamu). Sebelum publish, dipakai fitur **Fake Donate** di Admin Panel untuk
mensimulasikan tampilan donasi saat playtest.

## Tampilan & konten

**Q: Saya ganti warna di Theme tapi sebagian elemen tidak ikut berubah?**
Beberapa warna memang sengaja tidak ikut tema (swatch pilihan warna, preview title, dsb) — lihat
[kustomisasi-tema.md](kustomisasi-tema.md) bagian "Yang TIDAK ikut Theme". Kalau elemen lain juga
tidak ikut berubah setelah beberapa detik, coba Play ulang.

**Q: Suara/animasi/lagu tertentu tidak jalan, muncul "doesn't have access permission"?**
Aset itu diupload dari akun TZ dan belum diizinkan untuk game kamu. Lihat
[aset-pihak-ketiga.md](aset-pihak-ketiga.md) untuk daftar yang sudah diketahui dan cara
memperbaikinya.

**Q: Lampu (Lights) tidak muncul / tab GLights hilang dari Admin Panel?**
GLights **tidak ikut dikirim** di Kit ini — kamu pasang sendiri dari Toolbox. Tanpa GLights
terpasang di Workspace (nama foldernya harus `GLights`), paket Lights diam saja dan tabnya memang
sengaja disembunyikan. Lihat [instalasi.md](instalasi.md) dan
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

## Update

**Q: Bagaimana saya tahu ada versi baru?**
Kalau ada, Output server menampilkan `[TZKit:Kernel] Versi baru TZ Club Kit tersedia: X.X.X`. TZ
akan menginformasikan lewat kontak yang dipakai saat pembelian juga.

## Lain-lain

Pertanyaan yang tidak terjawab di sini bisa diajukan lewat kontak di [EULA.md](EULA.md) butir 7.
