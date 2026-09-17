---
trigger: always_on
---

# BLOG STANDARD ARCHITECTURE

Dokumen ini adalah aturan arsitektur & markup HTML paten untuk seluruh halaman artikel blog (`blog/*.html`).
**DILARANG KERAS** memodifikasi, memangkas class, atau berimprovisasi dengan struktur ini.

---

## 1. STRUKTUR & KOMPONEN WAJIB ARTIKEL BLOG (`blog/*.html`)

Setiap artikel blog baru **WAJIB** mengikuti komponen baku berikut:

### A. Head & Schema JSON-LD
- **CSS Preload**: Poppins Font, `bootstrap.min.css`, `main.min.css`, `bootstrap-icons`, `aos.css`, `glightbox.min.css`, `swiper-bundle.min.css`.
- **Scoped Responsive Table CSS**:
```html
<style>
  .article-main { width:100%; max-width:100%; min-width:0; overflow-x:clip; }
  .table-responsive { width:100%; max-width:100%; overflow-x:auto; -webkit-overflow-scrolling:touch; border:1px solid var(--cream-border); border-radius:12px; margin-bottom:1.25rem; }
  .table-responsive table { margin-bottom:0; }
  @media(max-width:767.98px){ .formula-box { padding:1.25rem 1rem!important; } .formula-box p { font-size:1.02rem!important; word-break:break-word; } }
</style>
```
- **Schema JSON-LD**: Berisi 4 node (@graph): `LocalBusiness/GeneralContractor`, `Article`, `BreadcrumbList` (3 level: Beranda, Blog, Judul Artikel dengan properti `item`), dan `FAQPage`.

### B. Navbar Baku (Wajib Logo-Img 160x54)
```html
<nav id="navbar" class="navbar navbar-expand-lg fixed-top" aria-label="Navigasi Utama">
  <div class="container position-relative">
    <a class="navbar-brand d-flex align-items-center" href="/" aria-label="Kontraktor Surabaya - Beranda">
      <img src="../assets/img/logo-header.webp" alt="Logo Kontraktor Surabaya" class="logo-img" width="160" height="54" fetchpriority="high" onerror="this.style.display='none'">
    </a>
    <button class="navbar-toggler custom-toggler shadow-none" type="button" data-bs-toggle="offcanvas" data-bs-target="#navOffcanvas" aria-controls="navOffcanvas" aria-label="Buka menu navigasi">
      <span class="toggler-bar"></span><span class="toggler-bar"></span><span class="toggler-bar"></span>
    </button>
    <div class="offcanvas offcanvas-end" tabindex="-1" id="navOffcanvas" aria-labelledby="navOffcanvasLabel">
      <div class="offcanvas-header d-flex d-lg-none align-items-center justify-content-between">
        <span class="drawer-title fw-bold text-maroon fs-6 mb-0" id="navOffcanvasLabel">Menu Navigasi</span>
        <button type="button" class="btn-drawer-close shadow-none" data-bs-dismiss="offcanvas" aria-label="Tutup navigasi"><i class="bi bi-x-lg"></i></button>
      </div>
      <div class="offcanvas-body">
        <ul class="navbar-nav mx-auto align-items-lg-center gap-lg-1 mb-2 mb-lg-0">
          <li class="nav-item"><a class="nav-link" href="/">Beranda</a></li>
          <li class="nav-item"><a class="nav-link" href="/tentang-kami">Tentang Kami</a></li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="/layanan" id="layananDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">Layanan</a>
            <ul class="dropdown-menu border-0 shadow" aria-labelledby="layananDropdown">
              <li><a class="dropdown-item" href="/layanan/jasa-arsitek-surabaya"><i class="bi bi-pencil-ruler me-2 text-maroon"></i>Jasa Arsitek</a></li>
              <li><a class="dropdown-item" href="/layanan/kontraktor-rumah-surabaya"><i class="bi bi-house-door-fill me-2 text-maroon"></i>Kontraktor Rumah</a></li>
              <li><a class="dropdown-item" href="/layanan/kontraktor-bangunan-surabaya"><i class="bi bi-building me-2 text-maroon"></i>Kontraktor Bangunan</a></li>
              <li><a class="dropdown-item" href="/layanan/jasa-renovasi-surabaya"><i class="bi bi-tools me-2 text-maroon"></i>Jasa Renovasi</a></li>
              <li><a class="dropdown-item" href="/layanan/jasa-desain-interior-surabaya"><i class="bi bi-palette-fill me-2 text-maroon"></i>Desain Interior</a></li>
              <li><a class="dropdown-item" href="/layanan/rab-estimasi-biaya-surabaya"><i class="bi bi-calculator-fill me-2 text-maroon"></i>RAB &amp; Estimasi Biaya</a></li>
            </ul>
          </li>
          <li class="nav-item"><a class="nav-link" href="/galeri">Galeri</a></li>
          <li class="nav-item"><a class="nav-link active" href="/blog" aria-current="page">Blog</a></li>
        </ul>
        <div class="d-none d-lg-flex align-items-center mt-3 mt-lg-0">
          <a class="nav-link nav-cta d-inline-flex align-items-center gap-2" id="nav-wa-cta" href="https://wa.me/62088989643555?text=Halo%2C+saya+ingin+konsultasi+proyek" target="_blank" rel="noopener noreferrer">
            <i class="bi bi-telephone-fill"></i> Hubungi Kami
          </a>
        </div>
      </div>
    </div>
  </div>
</nav>
```

### C. Urutan Konten Utama (`article-main`)
1. **Title & Meta**: `h1.article-title`, `.article-top-meta` (Foto Erlang Sinatrya + Tanggal + Waktu baca).
2. **Featured Image**: `.featured-image-wrap` + `.featured-caption`.
3. **Summary Box**: `.summary-box` (Answer Capsule + 5 bullet points).
4. **Auto-TOC Box**: `.toc-box` dengan tombol toggle dan list `#auto-toc-list`.
5. **Article Body**:
   - Paragraf pengantar, H2 bernomor (`id="slug-heading"`), H3 jika ada.
   - **Tabel Responsif** (jika ada): Dibungkus `<div class="table-responsive my-4">` + `<table class="table table-bordered table-hover align-middle mb-0" style="min-width:640px;">` + `<thead class="table-dark" style="background:var(--maroon);">` + helper teks mobile `<small class="text-muted d-block mt-n2 mb-4 text-center d-md-none"><i class="bi bi-arrow-left-right me-1"></i>Geser tabel ke samping untuk melihat detail</small>`.
   - In-Article Image 2: `.featured-image-wrap.my-4`.
   - Quote: `<blockquote class="article-quote">"..."<cite>&mdash; Erlang Sinatrya, Lead Project Engineer Kontraktor Surabaya</cite></blockquote>`.
   - Internal linking: Mengarah ke `/layanan/...` dan `/galeri`.
   - Promo Banner: `<a href="https://wa.me/..." target="_blank" class="promo-banner" data-aos="fade-up"><img src="../assets/img/layanan/..." alt="..."><div class="promo-overlay"><div class="promo-text">...</div><div class="promo-subtext">...</div><div class="promo-cta"><i class="bi bi-whatsapp"></i> Chat WhatsApp Sekarang</div></div></a>`.
6. **FAQ Accordion**: `.article-faq` dengan 3-4 item `.faq-mini-item` (`.faq-mini-question` + `.faq-mini-answer`).
7. **Share Box & Tags Footer**: `.share-article-box` (WA, FB, X, LinkedIn) & `.article-tags-footer` (`.tag-pill`).

### D. Sidebar Paten (Author + Verified Images)
```html
<aside class="article-sidebar">
  <div class="sidebar-author-card text-center">
    <img src="../assets/img/person/erlang.webp" alt="Erlang Sinatrya" class="mx-auto d-block" onerror="this.src='../assets/img/favicon-logo.webp'">
    <h4>Erlang Sinatrya</h4>
    <div class="sidebar-social">
      <a href="https://wa.me/62088989643555" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp"><i class="bi bi-whatsapp"></i></a>
      <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" aria-label="Instagram"><i class="bi bi-instagram"></i></a>
      <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" aria-label="Facebook"><i class="bi bi-facebook"></i></a>
    </div>
    <p class="desc">Erlang Sinatrya adalah Lead Project Engineer di Kontraktor Surabaya dengan keahlian khusus pada perancangan arsitektur, estimasi RAB akurat, dan manajemen konstruksi di Jawa Timur.</p>
  </div>
  <div class="sidebar-related">
    <h4>Artikel Terkait</h4>
    <!-- HANYA GUNAKAN GAMBAR YANG BENAR-BENAR ADA SECARA FISIK DI ASSETS/IMG/BLOG/ -->
    <a href="/blog/slug-artikel" class="related-item">
      <img src="../assets/img/blog/nama-gambar-valid.webp" alt="Judul">
      <div><h5>Judul Ringkas</h5><span>Tanggal</span></div>
    </a>
  </div>
</aside>
```

### E. Layanan Terkait, CTA Card, & Footer 4 Kolom
- **Related Services**: `<section class="related-articles-section"><div class="container"><h3 class="related-heading">...</h3><div class="related-grid"><article class="related-card"><a href="..."><img src="../assets/img/layanan/..." loading="lazy"></a><div class="related-card-content"><h4><a href="...">...</a></h4><p>...</p><a href="..." class="related-read-more">Lihat Layanan <i class="bi bi-arrow-right"></i></a></div></article></div></div></section>`.
- **CTA Section**: `<section id="cta" class="py-5" style="background:var(--cream);"><div class="container py-lg-4"><div class="cta-card" data-aos="zoom-in"><div class="cta-shape-1"></div><div class="cta-shape-2"></div><div class="cta-shape-3"></div><div class="cta-content-wrap"><span class="cta-label"><i class="bi bi-tools"></i> ...</span><h2 class="cta-title">...</h2><p class="cta-desc">...</p><div class="d-flex justify-content-center"><a id="cta-wa-primary" href="..." class="btn-gold" target="_blank"><i class="bi bi-whatsapp"></i> Konsultasi Proyek via WhatsApp</a></div></div></div></div></section>`.
- **Footer**: `<footer id="footer" role="contentinfo">` dengan 4 kolom (`.footer-brand`, Layanan, Navigasi, Area Layanan & Artikel) dan `.footer-bottom`.
- **Floating WA & Scroll Top**: `<a class="wa-float" id="wa-float">` & `<button class="scroll-top" id="scroll-top-btn"><i class="bi bi-chevron-up"></i></button>`.

---

## 2. INTEGRASI SISTEMIK WAJIB SETIAP POSTING ARTIKEL
1. **`sitemap.xml`**: Tambahkan URL format bersih tanpa `<image:image>` dan update `<lastmod>` pada `https://kontraktorsurabaya.biz.id/blog`.
2. **`blog.html`**: Tambahkan Card artikel baru di urutan pertama `.portfolio-grid` dan update `ItemList` Schema JSON-LD (`numberOfItems: N`, posisi artikel 1..N).
3. **`llms.txt`**: Tambahkan artikel baru ke dalam klaster topiknya di file `llms.txt` (`- [Judul](URL): Deskripsi`).
4. **Validasi Gambar Fisik**: Seluruh gambar (`<img src="...">`) **WAJIB diverifikasi ada secara fisik** di `assets/img/blog/` atau `assets/img/layanan/` sebelum commit.
