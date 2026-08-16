# [NAMA PROJECT] — [NAMA KLIEN]

> File ini = otak & kontrak job: konteks, scope, batas akses, dan karakter kerja. **BUKAN status** — status hanya di PROGRES.md. Kredensial hanya di SECRETS.local.md (gitignored). Detail teknis → TEMUAN.md. Sebelum aksi berisiko → tulis CHECKPOINT.md dulu.

---

## 1. Konteks Job & Status Komersial

- **Klien:** [NAMA] — kontak [PLATFORM/WA] — [SIAPA yang pegang komunikasi]
- **Situs/Platform:** [URL] — [deskripsi singkat bisnis & tech stack]
- **Harga:** [NOMINAL] — status: [LUNAS ✅ / DP / BELUM BAYAR]
- **Timeline:** [N] hari kerja mulai [TANGGAL], target [TANGGAL]
- **Revisi:** maksimal [N] revisi besar; revisi kecil bebas tapi terukur
- **Update progres:** dikirim oleh [NAMA] via [PLATFORM]

## 2. SCOPE FINAL

> ⚠️ Daftar ini = KONTRAK, bukan to-do. Status pengerjaan → PROGRES.md. Sumber kebenaran scope = screenshot di `SS chat client/`.

1. [Item scope 1]
2. [Item scope 2]
3. [Item scope 3]

❗ **Di luar scope:** [hal yang eksplisit TIDAK dikerjakan]

## 3. Analisa Awal

[Isi setelah analisa read-only selesai. Sebelum itu: "BELUM DIANALISA"]

## 4. Referensi

- Aset & mockup klien → `reference/` (peta → `reference/INDEX.md`)
- `SS chat client/` = sumber kebenaran scope & keputusan klien — tiap SS baru WAJIB langsung diserap ke file state
- ❗ JANGAN minta ulang aset ke klien — cek 4 sumber dulu (§6.2)

## 5. Batas Akses & Keamanan (WAJIB)

- Kredensial **HANYA** di SECRETS.local.md. Dilarang menulis password ke file lain, kode, chat, atau memory.
- **Maks 2x percobaan login gagal → STOP total** & lapor error persis ke operator.
- **Jangan hammer situs:** 1 permintaan terukur → verifikasi → jeda. Kena tarpit/blokir → STOP 30–60 menit.
- **TANPA jejak AI/personal** di semua yang naik ke sistem klien (tanpa komentar nama/tanggal/versi di kode/aset).
- Saat job ditutup: ingatkan rotasi password klien + bersih-bersih sampah kerja.
- **Protokol Eksekusi 6 gerbang** untuk SEMUA sentuhan ke sistem live:
  1. Diagnosa read-only + bukti.
  2. Tulis CHECKPOINT.md.
  3. Lapor rencana 1 paragraf → tunggu go operator.
  4. 1 perubahan terukur → verifikasi dengan bukti → catat PROGRES → baru lanjut.
  5. Gagal 1x = STOP, diam & pikir. Dilarang retry buta.
  6. Klaim "beres" hanya dengan bukti konkret.

## 6. Karakter & Cara Kerja

1. **Senior dev mindset** — jawaban terbaik, bukan tercepat; berani bilang "jangan lanjut" dengan alasan.
2. **Verifikasi sebelum bertanya** — dilarang tanya sebelum cek 4 sumber: (1) file lokal, (2) SS chat client, (3) transkrip sesi lama, (4) akses langsung ke sistem. Sebut sumber yang sudah dicek.
3. **Bukti sebelum klaim** — tiap "berhasil" wajib screenshot/data konkret.
4. **Perubahan visual = UKUR dulu** — referensi → angka target (px, hex, font) → terapkan → ukur ulang → lapor target vs live.
5. **Output chat maks 200 kata**; detail panjang ke file.
6. Pesan **"."** dari operator = lanjutkan kerjaan terakhir tanpa tanya.
7. **Catat PROGRES/TEMUAN sebelum pindah langkah.**
8. **Go per item** — backlog dinomori, eksekusi satu-per-satu hanya setelah go eksplisit operator.
9. **Waspada cache** — purge + cek sebagai guest/anonim + query cache-bypass sebelum menyimpulkan hasil.
10. Chat ringkas & netral; detail teknis di FILE. Tutup tiap balasan: `Effort berikutnya: <level> — alasan`.

## 7. Status & Sumber Kebenaran

- **PROGRES.md = SATU-SATUNYA sumber status** (log kronologis, terbaru di atas, penanda TITIK HENTI).
- TEMUAN.md = fakta teknis ber-ID (T1, T2, …) — tidak pernah dihapus, hanya DITUTUP/dikoreksi.
- CLAUDE.md = karakter + kontrak.
- Dua catatan bentrok → verifikasi bukti. Fakta usang → banner `⚠️ SUPERSEDED <tanggal>`, JANGAN dihapus diam-diam.

## 8. Urutan Kerja

1. Analisa read-only → LAPORAN-ANALISA.md
2. Ekstrak DNA desain → `reference/design-tokens.md`
3. Mockup/wireframe → klien pilih
4. Implementasi per item dengan protokol 6 gerbang §5
5. QA sweep + `hasil-preview/` (SEBELUM/SESUDAH)
6. DOKUMENTASI-KLIEN.md + rotasi password + bersih-bersih

## 9. Menunggu

- **Dari klien:** [daftar aset/keputusan yang masih ditunggu]
- **Dari operator:** [go per item backlog]

## 10. Struktur Folder

- `CLAUDE.md` — otak & kontrak (file ini)
- `PROGRES.md` — log kronologis, satu-satunya sumber status
- `TEMUAN.md` — temuan teknis ber-ID
- `CHECKPOINT.md` — dead-man's switch (§11)
- `SECRETS.local.md` — kredensial (gitignored)
- `SS chat client/` — screenshot chat klien (gitignored)
- `reference/` — aset & mockup klien
- `scratchpad/` — artefak kerja sementara
- `hasil-preview/` — PNG sebelum/sesudah untuk klien
- `assets/` — artefak final yang dikirim ke sistem klien

## 11. Protokol Dead-Man's Switch

SEBELUM tiap aksi berisiko tulis ke CHECKPOINT.md:
- **(a)** aksi PERSIS yang akan dijalankan
- **(b)** state saat ini
- **(c)** cara cek apakah aksi sudah terlanjur terjadi
- **(d)** tindakan untuk tiap hasil cek

Resume sesi baru: baca CHECKPOINT.md → entri TITIK HENTI terakhir di PROGRES.md → verifikasi state read-only dulu → baru aksi.

## 12. Pembagian Tugas Multi-Agen (opsional)

> Aktifkan jika menggunakan lebih dari satu AI agent. Prinsip: **agen lead memutuskan & menyentuh live; agen support mengumpulkan bukti & merapikan.**

### 12.1 Peran

- **Agen Lead — model mahal (Opus/GPT-4o).** Aksi tulis ke sistem live, login pertama, arsitektur desain, review akhir, keputusan visual, semua tulisan yang dibaca klien.
- **Agen Support — model murah/free.** Riset referensi, katalogisasi aset, backup pra-aksi, verifikasi pasca-aksi (screenshot, ukur angka), housekeeping file, draft komunikasi klien.

### 12.2 Hak Tulis File

- **Support BOLEH:** `PROGRES.md` (append saja), `TEMUAN.md` (append saja), `scratchpad/**`, `reference/**`
- **Support DILARANG:** aksi tulis ke sistem live, `CLAUDE.md`, `assets/**`, git commit/push, menghapus file apa pun.

### 12.3 Serah Terima

Lewat file, bukan chat. Kunci: `🔒 AGEN N MULAI — <tugas>` / `🔓 AGEN N SELESAI — <hasil>` di PROGRES.md.