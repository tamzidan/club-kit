# Kustomisasi tampilan (Theme)

Semua UI kit (menu, admin panel, hotbar, kartu, dsb.) mengambil warna, font, dan gaya dari **satu**
tempat: `ReplicatedStorage > TZKit > Settings > Theme` (objek `Configuration`). Kamu tidak perlu
mengedit warna satu-satu di tiap paket.

## Cara paling cepat: ganti preset

1. Klik `Theme` di Explorer, buka tab **Properties**.
2. Di bagian **Attributes**, ubah `Preset` ke salah satu preset yang tersedia (lihat di bawah
   `Theme > Presets`):
   - `Monochrome` (bawaan) — hitam/putih kontras tinggi.
   - `Graphite` — abu gelap netral.
   - `Midnight` — biru gelap.
3. Perubahan langsung terlihat, termasuk saat sedang Play (Test) — tidak perlu restart.

## Bikin preset sendiri

1. Di `Theme > Presets`, klik kanan salah satu preset yang ada (mis. `Monochrome`) > **Duplicate**.
2. Ganti nama Configuration hasil duplikat, misalnya `BrandKu`.
3. Ubah Attributes-nya (lihat daftar token di bawah).
4. Set `Theme.Preset` (attribute di `Theme`, bukan di preset) ke nama preset barumu, misalnya
   `"BrandKu"`.

## Token yang tersedia (Attributes di tiap preset)

| Token | Arti |
|---|---|
| `Background` | Warna latar utama |
| `Card`, `CardTransparency` | Warna & transparansi kartu/panel |
| `Row`, `RowTransparency`, `RowHover` | Warna baris (list) & warna saat disorot mouse |
| `Stroke` | Warna garis tepi tipis |
| `Divider`, `DividerTransparency` | Garis pemisah antar bagian |
| `Highlight`, `HighlightText` | Warna tombol/elemen aktif & warna teks di atasnya |
| `Text`, `Subtext`, `Muted` | Warna teks utama, teks sekunder, teks redup |
| `PanelTransparency` | Transparansi panel besar (0 = solid) |
| `FontFamily` | Nama font (Roblox Font enum, mis. `"BuilderSans"`) |
| `GridEnabled` | Nyalakan/matikan pola grid di latar panel |
| `GridImage` | `rbxassetid://` gambar pola grid |
| `GridTileSize`, `GridTransparency`, `GridLoopTime` | Ukuran, transparansi, dan kecepatan animasi grid |

Semua warna ditulis lewat color picker Properties Studio biasa (tipe `Color3`) — tidak perlu
menulis hex manual di sini (beda dengan Config paket, yang memang teks hex).

## Yang TIDAK ikut Theme

- Warna yang sengaja tetap ("swatch" pilihan warna, preview title, dot indikator) — ini memang
  harus menampilkan warna aslinya, bukan warna tema.
- Gambar/ikon tiap paket (diatur di Config paket masing-masing, lihat
  [konfigurasi.md](konfigurasi.md)).
- Preset langit paket Sky (`Packages/Sky/Assets/Presets`) — itu preset Lighting Roblox, bukan
  Theme UI.

## Suara UI

Suara klik/hover/buka panel diatur terpisah di **Settings > UISound** (bukan bagian Theme):
`Enabled` untuk menyalakan/mematikan semua, atau matikan satu jenis suara saja. Untuk mematikan
suara di satu tombol/panel tertentu, beri Attribute `NoUISound = true` pada `GuiObject`/`ScreenGui`
itu di Studio.
