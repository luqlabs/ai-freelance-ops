# ai-freelance-ops

> Metodologi operasional AI-assisted freelance untuk pekerjaan di sistem live klien.

Bukan framework baru. Bukan plugin. Ini **template kerja** yang bisa langsung di-clone dan dipakai untuk project freelance berbasis AI — terutama yang menyentuh sistem live (WordPress, CMS, server).

---

## Masalah yang diselesaikan

Saat menggunakan AI agent (Claude Code, Codex, dll) untuk kerja freelance di sistem live klien, ada risiko nyata:
- Sesi mati di tengah jalan → tidak tahu apa yang sudah berubah
- Retry buta → IP block, data rusak, site down
- Cache menyembunyikan hasil → klaim "sudah beres" yang salah
- Dua agen bentrok → file overwrite, state tidak konsisten
- Kredensial bocor lewat chat/kode

Framework ini menjawab semua itu dengan 5 komponen unik.

---

## 5 Komponen Inti

### 1. CHECKPOINT.md — Dead-Man's Switch
Sebelum tiap aksi berisiko, tulis 4 field:
- **(a)** aksi persis yang akan dijalankan
- **(b)** state saat ini
- **(c)** cara verifikasi apakah aksi sudah terjadi (read-only)
- **(d)** tindakan untuk tiap hasil cek

Kalau sesi mati kacau, sesi baru bisa resume tanpa tanya — tinggal baca CHECKPOINT.md.

### 2. PROGRES.md — Single Source of Truth
Log kronologis, terbaru di atas, dengan penanda TITIK HENTI di akhir tiap sesi. Tidak ada status di file lain.

### 3. TEMUAN.md — Immutable Issue Tracker
Fakta teknis ber-ID (T1, T2, ...). Tidak pernah dihapus — hanya DITUTUP atau SUPERSEDED dengan forward reference. Membuat audit trail permanen untuk klien.

### 4. Protokol Eksekusi 6 Gerbang
Untuk SEMUA sentuhan ke sistem live:
1. Diagnosa read-only + bukti
2. Tulis CHECKPOINT.md
3. Lapor rencana → tunggu go operator
4. 1 perubahan → verifikasi dengan bukti → catat PROGRES → baru lanjut
5. Gagal 1x = STOP & pikir (bukan retry buta)
6. Klaim "beres" hanya dengan bukti konkret

### 5. Split Agen Berdasarkan Reversibilitas
Bukan split berdasarkan skill, tapi berdasarkan **risiko**:
- **Agen Lead (model mahal):** semua yang menyentuh live, login, keputusan arsitektur
- **Agen Support (model murah/free):** semua yang reversibel — riset, backup, verifikasi pasca-aksi, housekeeping

---

## Cara Pakai

```bash
git clone https://github.com/luqlabs/ai-freelance-ops.git nama-project-klien
cd nama-project-klien
rm -rf .git
git init
```

Kemudian isi:
1. `CLAUDE.md` — konteks klien, scope, timeline
2. `SECRETS.local.md` — kredensial (sudah masuk .gitignore)
3. Mulai log di `PROGRES.md`

---

## Struktur File

```
CLAUDE.md           ← otak & kontrak job
PROGRES.md          ← satu-satunya sumber status
TEMUAN.md           ← temuan teknis ber-ID (immutable)
CHECKPOINT.md       ← dead-man's switch pre-aksi
SECRETS.local.md    ← kredensial (gitignored)
SS chat client/     ← screenshot chat klien (gitignored)
reference/          ← aset & mockup klien
scratchpad/         ← artefak kerja sementara
hasil-preview/      ← PNG sebelum/sesudah untuk klien
assets/             ← artefak final ke sistem klien
```

---

## Contoh Nyata

Folder `example-anonymized/` berisi contoh dari project WordPress redesign UI katalog — semua data klien sudah dianonimkan.

---

## Lisensi

MIT