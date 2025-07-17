# Lab7Web

Setiap controller akan me-load tampilan yang menggunakan layout utama (template), agar semua halaman punya desain yang konsisten (navbar, sidebar, footer sama).

Contoh:

// Controller: Page.php
public function about()
{
    return view('about', ['judul' => 'Tentang Kami']);
}
Di View (misal: about.php),bisa extend layout:

<?= $this->extend('layout/template'); ?>
<?= $this->section('content'); ?>
<h1><?= $judul ?></h1>
<p>Ini adalah halaman tentang kami.</p>
<?= $this->endSection(); ?>



# Modul Praktikum 1

## Deskripsi

Latihan membuat layout sederhana menggunakan CodeIgniter 4. Semua halaman seperti Home, About, Artikel, dan Kontak akan menggunakan layout yang sama dengan header dan footer tetap.

## Langkah-langkah 

1. Membuat controller Page.php
2. Membuat file layout di Views/layout/template.php
3. Membuat halaman home.php, about.php, dll dengan extend layout
4. Menambahkan routing di Config/Routes.php

![gambar](Screenshot/SS7.jpeg)

# Modul Praktikum 2

Ringkasan Instruksi:
Menghapus Data
Tambahkan method delete() ke dalam Controller Artikel: 

public function delete($id)
{
    $artikel = new ArtikelModel();
    $artikel->delete($id);
    return redirect('admin/artikel');
}

# Pertanyaan dan Tugas

Selesaikan program sesuai langkah-langkah yang diberikan.

Diperbolehkan melakukan improvisasi.

![gambar](Screenshot/SS8.jpeg) 

# Modul Praktikum 3 

# 1.File View Cell (app/View/components/artikel_terkini.php)

<?php
// Menampilkan artikel terkini dengan kategori tertentu
foreach ($artikel as $row): ?>
    <div class="artikel-item">
        <a href="<?= base_url('/artikel/' . $row['slug']) ?>">
            <h3><?= $row['Ketimpangan Ekonomi Dan Paradoks Robin Hood'] ?></h3>
        </a>
        <p>Kategori: <?= $row['kategori'] ?></p>
    </div>
<?php endforeach ?>

# 3.Output yang Diharapkan (Contoh Visual)
Keterangan Output:

Setiap artikel ditampilkan dalam bentuk card dengan:

Judul artikel (link ke detail)

Nama kategori

Hanya menampilkan artikel dengan kategori "terkini".

3. Contoh Data dari Controller/Model (PHP)

// Contoh data yang dikirim ke View Cell
$data = [
    'artikel' => [
        [
            'judul' => 'Belajar CodeIgniter 4',
            'slug' => 'belajar-ci4',
            'kategori' => 'terkini'
        ],
        [
            'judul' => 'View Cell dalam CI4',
            'slug' => 'view-cell-ci4',
            'kategori' => 'tutorial'
        ]
    ]
];

# 4.Perbedaan View Cell vs View Biasa

Fitur	View Cell	View Biasa
Scope	Komponen kecil (sidebar, widget)	Halaman penuh (index, detail)
Reusability	✅ Bisa dipakai di banyak halaman	❌ Spesifik per-halaman
Logika	Minimal (fokus tampilan)	Bisa kompleks

# 5.Catatan penting

Pastikan menggunakan CodeIgniter 4 (terlihat dari struktur folder app/View/components).

Format output bisa disesuaikan dengan CSS (contoh: Bootstrap).

Untuk gambar asli, Anda perlu menjalankan kode di lokal dan screenshot hasilnya.

![gambar](Screenshot/SS9.jpeg) 


