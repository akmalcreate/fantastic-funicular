# 🐠 fantastic-funicular

Web edukasi interaktif tentang ekosistem laut. Laut dalam web ini **rusak sedikit demi sedikit sesuai waktu nyata** sejak pengguna pertama kali membuka halaman. Pengguna bisa mengetuk ikan untuk belajar tentang spesiesnya, dan membaca materi yang terbuka seiring kondisi laut memburuk.

🔗 **Demo:** https://GANTI-DENGAN-URL-VERCEL-KAMU.vercel.app

> Dibuat dengan bantuan Claude (Anthropic). Dirancang dan dikembangkan oleh **Moch Akmal Almagribi**.

## Tujuan

Banyak orang tahu sampah plastik berbahaya, tetapi sulit membayangkan dampaknya yang terjadi pelan-pelan. Proyek ini menunjukkan prosesnya: satu botol yang dibuang hari ini tampak sepele, tetapi hari demi hari menumpuk sampai terumbu karang memutih, ikan menghilang, dan rantai makanan terputus.

## Fitur

- **Laut hidup:** ikan, penyu, dan ubur-ubur berenang sendiri ke sana kemari dengan arah dan kecepatan masing-masing.
- **Ekosistem lengkap:** rumput laut yang bergoyang, terumbu karang, batu, kapal karam, gelembung udara, dan sinar matahari dari permukaan.
- **Kapal feri wisata:** bolak-balik di permukaan dan wisatawan membuang sampah ke laut. Semakin rusak lautnya, semakin sering sampah dibuang.
- **Pencemaran berbasis waktu nyata:** kerusakan bertambah dalam 10 hari dan tersimpan di browser, jadi tetap berlanjut walau web ditutup.
- **Dampak yang terlihat:** air keruh kehijauan, karang memutih, rumput laut menguning, sampah menumpuk dan mengambang, ikan berkurang dan yang mati melayang ke permukaan.
- **Kartu spesies:** ketuk makhluk laut untuk melihat nama, nama latin, habitat, kebiasaan, fakta unik, dan dampak pencemaran terhadap spesies itu.
- **Pemberitahuan materi:** ikon chat di pojok kanan atas berisi 9 materi yang terbuka bertahap sesuai tingkat kerusakan laut, lengkap dengan lencana angka dan notifikasi.
- **Mode simulasi:** tombol "+1 hari" untuk melihat kerusakan tanpa menunggu, dan "Pulihkan laut" untuk mengulang dari awal.
- **Responsif** untuk HP dan desktop, mendukung mode gelap pada panel, dan menghormati `prefers-reduced-motion`.

## Cara kerja

| Bagian          | Penjelasan                                                                                                                                                                   |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Waktu nyata     | Saat pertama dibuka, waktu kunjungan disimpan di `localStorage` (`laut_first`). Tingkat pencemaran `p` dihitung dari selisih waktu sekarang, dari 0 sampai 1 selama 10 hari. |
| Efek visual     | Nilai `p` mengatur opasitas lapisan keruh, warna karang dan rumput laut (variabel CSS), jumlah ikan, dan banyaknya sampah.                                                   |
| Gerakan makhluk | Setiap makhluk memilih titik tujuan acak, bergerak dengan percepatan halus, lalu memilih titik baru. Arah hadap dan kemiringan badan menyesuaikan gerakan.                   |
| Sampah          | Sampah dilempar dari feri dengan gerak parabola, lalu tenggelam, mengambang, atau diam di dasar sesuai jenisnya (botol, kantong, kaleng).                                    |
| Materi          | Setiap materi punya ambang pencemaran. Materi yang sudah terbuka dan belum dibaca dicatat di `localStorage` (`laut_seen`) untuk lencana notifikasi.                          |
| Performa        | Animasi per frame hanya memakai `transform` dan `opacity` dengan `requestAnimationFrame`, supaya tetap halus dan ringan.                                                     |

## Teknologi

- HTML, CSS, dan JavaScript murni, tanpa framework dan tanpa library.
- Semua gambar dibuat sebagai SVG inline.
- Font: Bricolage Grotesque (Google Fonts).
- Penyimpanan: `localStorage`.
- Hosting: Vercel atau GitHub Pages.

## Menjalankan di komputer sendiri

Proyek ini hanya satu file. Cukup unduh repo ini lalu buka `index.html` di browser. Tidak perlu instalasi apa pun.

```bash
git clone https://github.com/akmalcreate/fantastic-funicular.git
cd fantastic-funicular
# buka index.html di browser
```

## Struktur

```
.
├── index.html   # seluruh aplikasi (markup, gaya, dan logika)
└── README.md
```

## Rencana pengembangan

- [ ] Tambah spesies (pari, hiu, kuda laut)
- [ ] Suara ombak dan musik latar
- [ ] Mode bersih-bersih: pengguna mengambil sampah untuk memulihkan laut
- [ ] Penyimpanan online agar progres ikut di semua perangkat

## Catatan pembuatan

Proyek ini dikerjakan dengan bantuan AI (Claude) untuk menulis kode awal. Konsep, arah desain, materi edukasi, dan penyesuaian dilakukan oleh pembuat.

## Pembuat

**Moch Akmal Almagribi**

- GitHub: https://github.com/akmalcreate
- Proyek lain: [Gemini MathSolver](https://gemini-mathsolver-git-main-moch-akmal-almagribi.vercel.app/)

## Lisensi

MIT. Silakan dipakai dan dipelajari dengan tetap mencantumkan nama pembuat.
