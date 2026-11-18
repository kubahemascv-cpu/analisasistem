# Monitoring CS Kubah Emas — Tahap 1

Isi: Antrean Leads, Hasil Harian, Riwayat (Manager), Pengaturan + Ekspor (Manager).
Belum ada (Tahap 2): Evaluasi 10 Chat, Evaluasi Percobaan, konversi per kohort, impor data.

## Pasang (sekali)
1. Buat Google Sheet BARU, kosong. Jangan pakai Sheet yang sudah ada.
2. Extensions > Apps Script. Hapus kode bawaan, tempel semua isi `CS_Monitor_AppsScript.gs`, Save.
3. Pilih fungsi `setupAwal`, Run, setujui izin. Terbentuk 7 tab + 2 pengguna (Lukman = Manager, Tri = CS). Pengguna lain ditambah dari menu Pengaturan di app.
4. Deploy > New deployment > Web app. Execute as: Me. Who has access: Anyone. Salin URL `/exec`.
5. Buka `index.html`, ganti `PASTE_URL_WEB_APP_DI_SINI` dengan URL itu.
6. Upload `index.html`, `sw.js`, `manifest.json`, `icon-192.png`, `icon-512.png` ke GitHub Pages. Tutup total lalu buka lagi app-nya.

## Update script di kemudian hari
Tempel kode baru, Deploy > Manage deployments > pensil > Version: New > Deploy. URL tetap.

## Perlu diketahui
- **Tanpa PIN (bawaan).** Siapa pun yang punya link app dan URL /exec bisa masuk, termasuk sebagai Manager. Jangan sebar link ke luar tim. Pengaman bisa dinyalakan kapan saja: ubah `PIN_MODE` di Apps Script jadi `'manager'` (PIN hanya Manager) atau `'semua'`, lalu Deploy versi baru. PIN ada di tab `Users`.
- Dua orang mengubah field yang sama di lead yang sama: yang terakhir menang (semua perubahan tetap ada di Riwayat).
- App butuh internet. Tidak ada antrean offline.
- Ekspor Excel memakai SheetJS dari cdnjs. Kalau gagal termuat, otomatis jadi CSV.
- Lead tidak masuk otomatis dari WhatsApp. Semua dicatat manual.
