# Pemberitahuan pihak ketiga (Third-Party Notices)

TZ Club Kit memakai beberapa library dan aset buatan pihak lain. Lisensi masing-masing berlaku
sendiri di luar [EULA.md](EULA.md) Kit ini. Jangan menghapus atau mengubah pemberitahuan ini.

## TopbarPlus

- **Dipakai untuk:** ikon di topbar Roblox (menu utama, admin panel, musik, dsb).
- **Lokasi di kit:** `ReplicatedStorage.TZKit` memuat TopbarPlus sebagai `Icon` (satu salinan untuk
  semua paket, lewat `Kernel.Lib`/`kit`).
- **Pembuat:** 1ForeverHD (Sitely Studios).
- **Lisensi:** Mozilla Public License 2.0 (MPL-2.0).
- **Syarat yang sudah dipenuhi kit ini:** modul `Icon.Attribute` **tidak diubah** — ini adalah cara
  MPL-2.0 TopbarPlus dipenuhi tanpa perlu mencantumkan kredit tambahan di deskripsi game. **Jangan
  hapus atau ubah `ReplicatedStorage.TZKit.Icon.Attribute`.** Kalau modul itu sampai terhapus,
  tambahkan kredit "TopbarPlus" di deskripsi game sebagai gantinya.
- Sumber: https://github.com/1ForeverHD/TopbarPlus

## Janitor

- **Dipakai untuk:** membersihkan koneksi/instance (dependensi internal TopbarPlus).
- **Lokasi di kit:** `ReplicatedStorage.TZKit.Icon.Packages.Janitor`.
- **Pembuat:** Validark, dikelola bersama howmanysmall dkk.
- **Lisensi:** MIT.
- Sumber: https://github.com/howmanysmall/Janitor

## GoodSignal

- **Dipakai untuk:** implementasi Signal ringan (dependensi internal TopbarPlus).
- **Lokasi di kit:** `ReplicatedStorage.TZKit.Icon.Packages.GoodSignal`.
- **Pembuat:** Mark Langen (stravant).
- **Lisensi:** MIT.
- Sumber: https://github.com/stravant/goodsignal

> Catatan: `ReplicatedStorage.TZKit.Shared.Signal` yang dipakai paket-paket TZ sendiri (di luar
> TopbarPlus) adalah implementasi TZ sendiri, BUKAN GoodSignal — dibuat ulang supaya bisa mengirim
> tabel/fungsi apa adanya tanpa lewat `BindableEvent`.

## CameraShaker (RbxCameraShaker)

- **Dipakai untuk:** efek getar kamera saat animasi Smite (efek donasi Saweria).
- **Lokasi di kit:** `ServerStorage.TZKit.Packages.Saweria.Client.Render.CameraShaker`.
- **Pembuat:** Stephen Leitnick (Sleitnick), port dari asset Unity3D "EZ Camera Shake" dengan izin
  tertulis dari pembuat aslinya.
- **Lisensi:** MIT.
- Sumber: https://github.com/Sleitnick/RbxCameraShaker

## GLights (Gybasoft) — TIDAK ikut dikirim

- Paket **Lights** di Kit ini hanyalah jembatan (bridge) buatan TZ ke sistem lampu **GLights**
  buatan **Gybasoft**.
- Syarat Gybasoft (https://gybasoft.dev/terms) yang berlaku begitu Pembeli memasang GLights sendiri:
  boleh dipakai di game yang menghasilkan pendapatan; **jangan hapus atau ubah logo/kredit Gybasoft**
  pada model GLights; jangan mengklaimnya sebagai buatan sendiri; jangan membagikan ulang GLights
  yang tidak dimodifikasi (unduh langsung dari Toolbox resmi Gybasoft untuk tiap game).
- TZ **tidak** melisensikan ulang GLights — ini murni pengaturan langsung antara Pembeli dan Gybasoft.

## Lisensi MIT (ringkas, untuk Janitor/GoodSignal/CameraShaker)

```
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and
associated documentation files (the "Software"), to deal in the Software without restriction,
including without limitation the rights to use, copy, modify, merge, publish, distribute,
sublicense, and/or sell copies of the Software, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or
substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT
NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT.
```

Teks lengkap masing-masing lisensi ada di repositori sumber yang ditautkan di atas.
