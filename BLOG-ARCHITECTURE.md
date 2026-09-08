# ATURAN BAKU STRUKTUR ARTIKEL BLOG KONTRAKTOR SURABAYA (MUTLAK)

Dokumen ini adalah aturan arsitektur & markup HTML paten untuk seluruh halaman artikel blog (`blog/*.html`).
**DILARANG KERAS** memodifikasi, memangkas, atau berimprovisasi dengan struktur di bawah ini.

---

## 1. STRUKTUR URUTAN ELEMEN DARI ATAS KE BAWAH

Setiap file `blog/{slug}.html` **HARUS** memiliki urutan elemen persis seperti berikut:

1. **`<!DOCTYPE html>` & `<html lang="id">`**
2. **`<head>`**:
   - Meta tags lengkap (Title, Description, Keywords, Author: "Erlang Sinatrya", Robots, Canonical, Alternate).
   - Open Graph tags & Twitter Card tags lengkap.
   - Preload Poppins Font.
   - CSS: `bootstrap.min.css`, `main.min.css`, `bootstrap-icons.min.css`, `aos.css`, `glightbox.min.css`, `swiper-bundle.min.css`.
   - **Schema JSON-LD Graph** (`@type: ["LocalBusiness", "GeneralContractor", "ProfessionalService"]`, `@type: "Article"` / `"BlogPosting"`, `@type: "BreadcrumbList"`, `@type: "FAQPage"`).
3. **`<body class="blog-details-page">`**
4. **`<nav id="navbar" class="navbar navbar-expand-lg fixed-top" ...>`** (Navbar standar dengan drawer offcanvas).
5. **`<main class="main" id="main-content">`**:
   - **`<div class="breadcrumb-bar">`**
   - **`<section class="section pt-4 pb-5" style="background:var(--white);">`**:
     - `<div class="container">`
       - `<div class="article-layout">`
         - **`<div class="article-main">`**:
           - `<h1 class="article-title" data-aos="fade-up">`
           - `<div class="article-top-meta" data-aos="fade-up" data-aos-delay="100">` (Author photo, publish date, reading time)
           - `<div class="featured-image-wrap" data-aos="zoom-in">` + `<div class="featured-caption">`
           - `<div class="summary-box" data-aos="fade-up">` (Ringkasan Inti + Answer Capsule + 5 bullet points)
           - `<div class="toc-box">` (Daftar Isi Otomatis)
           - **`<div class="article-body">`**:
             - Paragraf Pembuka
             - Subheading H2 / H3 bernomor dengan konten mendalam
             - Tabel komparasi / tabel data (`<div class="table-responsive">`)
             - In-article image ke-2 (`<div class="featured-image-wrap my-4" data-aos="zoom-in">` atau `<figure class="body-figure">`)
             - Subheading H2 lanjutan
             - **`<blockquote class="article-quote">`** (Quote inspiratif dari Erlang Sinatrya)
             - **`<p class="mt-4">`** (Paragraf penutup berisi internal link ke `/layanan/...` dan `/galeri`)
             - **`<!-- Centered High-Contrast Promo Banner -->`**:
               `<a href="https://wa.me/..." target="_blank" class="promo-banner" data-aos="fade-up">`
                 - `<img>` banner layanan
                 - `<div class="promo-overlay">`
                   - `<div class="promo-text">...</div>`
                   - `<div class="promo-subtext">...</div>`
                   - `<div class="promo-cta"><i class="bi bi-whatsapp"></i> Chat WhatsApp Sekarang</div>`
           - **`</div>`** (Tutup `article-body`)
           - **`<div class="article-faq" data-aos="fade-up">`** (Mini FAQ Accordion):
             - `<h3>Pertanyaan Seputar [Topik]</h3>`
             - 3–4x `<div class="faq-mini-item">`
               - `<button class="faq-mini-question">...<i class="bi bi-plus-lg"></i></button>`
               - `<div class="faq-mini-answer"><div class="faq-mini-answer-inner"><p>...</p></div></div>`
           - **`<div class="share-article-box" data-aos="fade-up">`** (4 tombol share: WhatsApp, Facebook, Twitter, LinkedIn)
           - **`<div class="article-tags-footer">`** (Tag pills: `<a href="/blog" class="tag-pill">...</a>`)
         - **`</div>`** (Tutup `article-main`)
         - **`<aside class="article-sidebar">`**:
           - `<div class="sidebar-author-card text-center">` (Foto Erlang Sinatrya + nama + sosmed + deskripsi bio)
           - `<div class="sidebar-related">` (3 item artikel terkait dengan `<a href="..." class="related-item">`)
         - **`</aside>`**
       - **`</div>`** (Tutup `article-layout`)
     - **`</div>`** (Tutup `container`)
   - **`</section>`**
   - **`<section class="related-articles-section" data-aos="fade-up">`**:
     - Grid 3 kartu layanan terkait Kontraktor Surabaya (`.related-grid` > `.related-card`)
   - **`<section id="cta" class="py-5" style="background:var(--cream);">`**:
     - Card CTA gold button WhatsApp (`.cta-card` > `.cta-content-wrap`)
6. **`</main>`**
7. **`<footer id="footer" role="contentinfo" aria-label="Footer Kontraktor Surabaya">`** (Footer 4 kolom standar)
8. **`<a href="https://wa.me/..." class="wa-float" id="wa-float">`**
9. **`<button class="scroll-top" id="scroll-top-btn">`**
10. **Vendor & Main Scripts** (`bootstrap.bundle.min.js`, `aos.js`, `purecounter_vanilla.js`, `glightbox.min.js`, `imagesloaded.pkgd.min.js`, `isotope.pkgd.min.js`, `swiper-bundle.min.js`, `main.js`).
11. **Inline Script**: Auto-TOC, FAQ mini accordion toggle, Share links generator, Footer year.

---

## 2. INTEGRASI SISTEMIK WAJIB SETIAP POSTING ARTIKEL
1. **`sitemap.xml`**:
   - Tambahkan URL artikel baru lengkap dengan `<image:image>`.
   - **MUTLAK**: Update `<lastmod>` pada URL `#3 Blog Index` (`https://kontraktorsurabaya.biz.id/blog`) ke tanggal artikel terbaru.
2. **`blog.html`**:
   - Tambahkan Card artikel di urutan paling pertama grid (`.portfolio-grid`) dengan filter Isotope yang sesuai.
   - Update `ItemList` Schema JSON-LD (`numberOfItems: N` dan masukkan `position: 1` artikel baru, lalu geser posisi artikel lain secara sekuensial).
3. **Validasi Gambar**:
   - Seluruh path gambar wajib diverifikasi ada secara fisik di `assets/img/blog/` atau `assets/img/layanan/` sebelum di-deploy.

---

## 3. ATURAN KHUSUS UNTUK ARTIKEL DENGAN TABEL (`<table>`)

Jika artikel memuat elemen `<table>` (seperti tabel perbandingan, komparasi harga, simulasi biaya, atau spesifikasi teknis), **WAJIB** menerapkan 3 aturan responsivitas mobile berikut agar tidak terjadi layout overflow / terpotong:

### A. Scoped CSS Isolasi di `<head>`
Tambahkan blok style ini di dalam `<head>` tepat sebelum Schema JSON-LD:
```html
<!-- Article Responsive Layout Fixes (Khusus Artikel Bertabel / Formula) -->
<style>
  .article-main {
    width: 100%;
    max-width: 100%;
    min-width: 0;
    overflow-x: clip;
  }
  .table-responsive {
    width: 100%;
    max-width: 100%;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    border: 1px solid var(--cream-border);
    border-radius: 12px;
    margin-bottom: 1.25rem;
  }
  .table-responsive table {
    margin-bottom: 0;
  }
  @media (max-width: 767.98px) {
    .formula-box {
      padding: 1.25rem 1rem !important;
    }
    .formula-box p {
      font-size: 1.02rem !important;
      word-break: break-word;
    }
  }
</style>
```

### B. Standar Markup Pembungkus & Kelas Tabel
1. **Wadah**: Tag `<table>` **HARUS** dibungkus dalam `<div class="table-responsive my-4">` (atau `my-3`).
2. **Kelas Table**: Beri kelas `class="table table-bordered table-hover align-middle mb-0"` (atau `table-striped`).
3. **Min-Width**: Beri inline style `min-width` agar kolom tidak gepeng saat digeser di HP (misal: `style="min-width: 640px;"` untuk 5 kolom, atau `540px` untuk 3 kolom).
4. **Header Style**: Tag `<thead>` menggunakan `class="table-dark" style="background:var(--maroon);"` (atau `class="table-secondary"`).
5. **No Wrap untuk Kolom Ringkas**: Kolom angka/judul pendek diberi `style="white-space:nowrap;"`.

Contoh struktur tabel baku:
```html
<div class="table-responsive my-4">
  <table class="table table-bordered table-hover align-middle mb-0" style="min-width: 640px;">
    <thead class="table-dark" style="background:var(--maroon);">
      <tr>
        <th scope="col" style="white-space:nowrap;">Kelas Spesifikasi</th>
        <th scope="col" style="white-space:nowrap;">Rentang Biaya / m²</th>
        <th scope="col">Material Lantai &amp; Dinding</th>
        <th scope="col">Struktur &amp; Atap</th>
        <th scope="col">Karakteristik Cocok Untuk</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="fw-bold text-maroon">Standar / Minimalis Sederhana</td>
        <td style="white-space:nowrap;">Rp 3.500.000 – Rp 4.500.000</td>
        <td>Keramik 40×40/50×50, Bata ringan plaster aci cat standar</td>
        <td>Pondasi batu kali/footplat ringan, baja ringan + genteng metal/beton</td>
        <td>Rumah 1 lantai, kos-kosan standar, rumah subsidi renovasi</td>
      </tr>
    </tbody>
  </table>
</div>
<small class="text-muted d-block mt-n2 mb-4 text-center d-md-none"><i class="bi bi-arrow-left-right me-1"></i>Geser tabel ke samping untuk melihat detail</small>
```

### C. Petunjuk Swipe Mobile
Tepat setelah tag penutup `</div>` dari `.table-responsive`, **WAJIB** menyertakan helper teks khusus tampilan HP:
```html
<small class="text-muted d-block mt-n2 mb-4 text-center d-md-none"><i class="bi bi-arrow-left-right me-1"></i>Geser tabel ke samping untuk melihat detail</small>
```
