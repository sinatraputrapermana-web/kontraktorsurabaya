# ATURAN BAKU STRUKTUR ARTIKEL BLOG KONTRAKTOR SURABAYA (MUTLAK)

Dokumen ini adalah aturan arsitektur & markup HTML paten untuk seluruh halaman artikel blog (`blog/*.html`).
**DILARANG KERAS** memodifikasi, memangkas, atau berimprovisasi dengan struktur di bawah ini.

---

## 1. TEMPLATE BAKU LENGKAP ARTIKEL BLOG (`blog/*.html`)

Setiap file artikel blog baru **WAJIB** menyalin persis template di bawah ini tanpa mengubah nama class atau tag:

```html
<!DOCTYPE html>
<html lang="id">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{Meta Title}} | Kontraktor Surabaya</title>
  <meta name="description" content="{{Meta Description}}">
  <meta name="keywords" content="{{Keywords}}">
  <meta name="author" content="Erlang Sinatrya">
  <meta name="robots" content="index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1">
  <meta name="googlebot" content="index, follow">
  <link rel="canonical" href="https://kontraktorsurabaya.biz.id/blog/{{Slug}}">
  <link rel="alternate" hreflang="id-ID" href="https://kontraktorsurabaya.biz.id/blog/{{Slug}}">

  <!-- Open Graph -->
  <meta property="og:locale" content="id_ID">
  <meta property="og:type" content="article">
  <meta property="og:title" content="{{Meta Title}}">
  <meta property="og:description" content="{{Meta Description}}">
  <meta property="og:url" content="https://kontraktorsurabaya.biz.id/blog/{{Slug}}">
  <meta property="og:site_name" content="Kontraktor Surabaya">
  <meta property="og:image" content="https://kontraktorsurabaya.biz.id/assets/img/blog/{{Image1}}">
  <meta property="og:image:type" content="image/webp">
  <meta property="og:image:width" content="1200">
  <meta property="og:image:height" content="630">
  <meta property="og:image:alt" content="{{Image1 Alt}}">
  <meta property="article:published_time" content="{{Published Time ISO}}">
  <meta property="article:modified_time" content="{{Modified Time ISO}}">
  <meta property="article:author" content="Erlang Sinatrya">
  <meta property="article:section" content="{{Section}}">
  <meta property="article:tag" content="{{Tag}}">

  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:title" content="{{Meta Title}}">
  <meta name="twitter:description" content="{{Meta Description}}">
  <meta name="twitter:image" content="https://kontraktorsurabaya.biz.id/assets/img/blog/{{Image1}}">

  <link rel="icon" type="image/webp" href="../assets/img/favicon-logo.webp">
  <link rel="apple-touch-icon" href="../assets/img/favicon-logo.webp">

  <!-- Google Fonts: Poppins -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link rel="preload" as="style"
    href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,600&display=swap">
  <link rel="stylesheet"
    href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,600&display=swap"
    media="print" onload="this.media='all'">
  <noscript>
    <link rel="stylesheet"
      href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,600&display=swap">
  </noscript>

  <!-- Core & Vendor CSS -->
  <link rel="stylesheet" href="../assets/vendor/bootstrap/css/bootstrap.min.css">
  <link rel="stylesheet" href="../assets/css/main.min.css">
  <link rel="preload" href="../assets/vendor/bootstrap-icons/bootstrap-icons.min.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
  <noscript><link rel="stylesheet" href="../assets/vendor/bootstrap-icons/bootstrap-icons.min.css"></noscript>
  <link rel="preload" href="../assets/vendor/aos/aos.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
  <noscript><link rel="stylesheet" href="../assets/vendor/aos/aos.css"></noscript>
  <link rel="preload" href="../assets/vendor/glightbox/css/glightbox.min.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
  <noscript><link rel="stylesheet" href="../assets/vendor/glightbox/css/glightbox.min.css"></noscript>
  <link rel="preload" href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
  <noscript><link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css"></noscript>

  <!-- Article Responsive Layout Fixes -->
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

  <!-- Schema Markup JSON-LD -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@graph": [
      {
        "@type": ["LocalBusiness", "GeneralContractor", "ProfessionalService"],
        "@id": "https://kontraktorsurabaya.biz.id/#organization",
        "name": "Kontraktor Surabaya",
        "alternateName": "PT Kontraktor Surabaya Jaya",
        "url": "https://kontraktorsurabaya.biz.id/",
        "logo": {
          "@type": "ImageObject",
          "@id": "https://kontraktorsurabaya.biz.id/#logo",
          "url": "https://kontraktorsurabaya.biz.id/assets/img/logo-header.webp"
        },
        "image": [
          "https://kontraktorsurabaya.biz.id/assets/img/hero/hero.webp",
          "https://kontraktorsurabaya.biz.id/assets/img/logo-header.webp"
        ],
        "telephone": "+62088989643555",
        "priceRange": "Rp 3.500.000 - Rp 10.000.000 per m²",
        "address": {
          "@type": "PostalAddress",
          "streetAddress": "Jl. Raya Rungkut Madya No. 88, Rungkut",
          "addressLocality": "Surabaya Timur",
          "addressRegion": "Jawa Timur",
          "postalCode": "60293",
          "addressCountry": "ID"
        },
        "geo": {
          "@type": "GeoCoordinates",
          "latitude": -7.3195,
          "longitude": 112.7842
        },
        "areaServed": [
          {"@type": "AdministrativeArea", "name": "Surabaya"},
          {"@type": "AdministrativeArea", "name": "Sidoarjo"},
          {"@type": "AdministrativeArea", "name": "Gresik"},
          {"@type": "AdministrativeArea", "name": "Mojokerto"},
          {"@type": "AdministrativeArea", "name": "Madura"}
        ]
      },
      {
        "@type": "Article",
        "@id": "https://kontraktorsurabaya.biz.id/blog/{{Slug}}#article",
        "isPartOf": {
          "@type": "WebPage",
          "@id": "https://kontraktorsurabaya.biz.id/blog/{{Slug}}"
        },
        "headline": "{{H1 Title}}",
        "description": "{{Meta Description}}",
        "url": "https://kontraktorsurabaya.biz.id/blog/{{Slug}}",
        "mainEntityOfPage": {
          "@type": "WebPage",
          "@id": "https://kontraktorsurabaya.biz.id/blog/{{Slug}}"
        },
        "datePublished": "{{Published Time ISO}}",
        "dateModified": "{{Modified Time ISO}}",
        "author": {
          "@type": "Person",
          "name": "Erlang Sinatrya",
          "url": "https://kontraktorsurabaya.biz.id/tentang-kami",
          "jobTitle": "Lead Project Engineer",
          "worksFor": {
            "@type": "Organization",
            "name": "Kontraktor Surabaya"
          }
        },
        "publisher": {
          "@id": "https://kontraktorsurabaya.biz.id/#organization"
        },
        "image": {
          "@type": "ImageObject",
          "url": "https://kontraktorsurabaya.biz.id/assets/img/blog/{{Image1}}",
          "width": 1200,
          "height": 630
        },
        "inLanguage": "id-ID",
        "articleSection": ["{{Section}}"],
        "keywords": ["{{Keywords}}"]
      },
      {
        "@type": "BreadcrumbList",
        "itemListElement": [
          { "@type": "ListItem", "position": 1, "name": "Beranda", "item": "https://kontraktorsurabaya.biz.id/" },
          { "@type": "ListItem", "position": 2, "name": "Blog", "item": "https://kontraktorsurabaya.biz.id/blog" },
          { "@type": "ListItem", "position": 3, "name": "{{Short Title}}", "item": "https://kontraktorsurabaya.biz.id/blog/{{Slug}}" }
        ]
      },
      {
        "@type": "FAQPage",
        "mainEntity": [
          {{FAQ Items}}
        ]
      }
    ]
  }
  </script>
</head>

<body class="blog-details-page">

  <!-- ══ NAVBAR (PATEN: LOGO & DRAWER TOGGLER) ═════════════════════════════════ -->
  <nav id="navbar" class="navbar navbar-expand-lg fixed-top" aria-label="Navigasi Utama">
    <div class="container position-relative">

      <a class="navbar-brand d-flex align-items-center" href="/" aria-label="Kontraktor Surabaya - Beranda">
        <img src="../assets/img/logo-header.webp" alt="Logo Kontraktor Surabaya" class="logo-img" width="160" height="54" fetchpriority="high" onerror="this.style.display='none'">
      </a>

      <!-- Custom Modern Hamburger Toggler -->
      <button class="navbar-toggler custom-toggler shadow-none" type="button" data-bs-toggle="offcanvas"
        data-bs-target="#navOffcanvas" aria-controls="navOffcanvas" aria-label="Buka menu navigasi">
        <span class="toggler-bar"></span>
        <span class="toggler-bar"></span>
        <span class="toggler-bar"></span>
      </button>

      <div class="offcanvas offcanvas-end" tabindex="-1" id="navOffcanvas" aria-labelledby="navOffcanvasLabel">

        <div class="offcanvas-header d-flex d-lg-none align-items-center justify-content-between">
          <span class="drawer-title fw-bold text-maroon fs-6 mb-0" id="navOffcanvasLabel">Menu Navigasi</span>
          <button type="button" class="btn-drawer-close shadow-none" data-bs-dismiss="offcanvas" aria-label="Tutup navigasi">
            <i class="bi bi-x-lg"></i>
          </button>
        </div>

        <div class="offcanvas-body">
          <ul class="navbar-nav mx-auto align-items-lg-center gap-lg-1 mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link" href="/">Beranda</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/tentang-kami">Tentang Kami</a>
            </li>
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle" href="/layanan" id="layananDropdown" role="button"
                data-bs-toggle="dropdown" aria-expanded="false">
                Layanan
              </a>
              <ul class="dropdown-menu border-0 shadow" aria-labelledby="layananDropdown">
                <li><a class="dropdown-item" href="/layanan/jasa-arsitek-surabaya"><i
                      class="bi bi-pencil-ruler me-2 text-maroon"></i>Jasa Arsitek</a></li>
                <li><a class="dropdown-item" href="/layanan/kontraktor-rumah-surabaya"><i
                      class="bi bi-house-door-fill me-2 text-maroon"></i>Kontraktor Rumah</a></li>
                <li><a class="dropdown-item" href="/layanan/kontraktor-bangunan-surabaya"><i
                      class="bi bi-building me-2 text-maroon"></i>Kontraktor Bangunan</a></li>
                <li><a class="dropdown-item" href="/layanan/jasa-renovasi-surabaya"><i
                      class="bi bi-tools me-2 text-maroon"></i>Jasa Renovasi</a></li>
                <li><a class="dropdown-item" href="/layanan/jasa-desain-interior-surabaya"><i
                      class="bi bi-palette-fill me-2 text-maroon"></i>Desain Interior</a></li>
                <li><a class="dropdown-item" href="/layanan/rab-estimasi-biaya-surabaya"><i
                      class="bi bi-calculator-fill me-2 text-maroon"></i>RAB &amp; Estimasi Biaya</a></li>
              </ul>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/galeri">Galeri</a>
            </li>
            <li class="nav-item">
              <a class="nav-link active" href="/blog" aria-current="page">Blog</a>
            </li>
          </ul>

          <div class="d-none d-lg-flex align-items-center mt-3 mt-lg-0">
            <a class="nav-link nav-cta d-inline-flex align-items-center gap-2" id="nav-wa-cta"
              href="https://wa.me/62088989643555?text=Halo%2C+saya+ingin+konsultasi+proyek" target="_blank"
              rel="noopener noreferrer">
              <i class="bi bi-telephone-fill"></i> Hubungi Kami
            </a>
          </div>

        </div>
      </div>

    </div>
  </nav>

  <!-- ══ BREADCRUMB BAR ════════════════════════════════════════════════════════ -->
  <div class="breadcrumb-bar">
    <div class="container">
      <a href="/"><i class="bi bi-house-door-fill me-1"></i> Beranda</a>
      <span class="separator"><i class="bi bi-chevron-right"></i></span>
      <a href="/blog">Blog</a>
      <span class="separator"><i class="bi bi-chevron-right"></i></span>
      <span>{{Short Title}}</span>
    </div>
  </div>

  <!-- ══ MAIN CONTENT ══════════════════════════════════════════════════════════ -->
  <main class="main" id="main-content">

    <section class="section pt-4 pb-5" style="background:var(--white);">
      <div class="container">
        <div class="article-layout">

          <!-- ── ARTICLE MAIN COLUMN ────────────────────────────────────────── -->
          <div class="article-main">

            <h1 class="article-title" data-aos="fade-up">
              {{H1 Title}}
            </h1>

            <div class="article-top-meta" data-aos="fade-up" data-aos-delay="100">
              <div class="meta-author">
                <img src="../assets/img/person/erlang.webp" alt="Erlang Sinatrya" onerror="this.src='../assets/img/favicon-logo.webp'">
                <span>Erlang Sinatrya</span>
              </div>
              <span><i class="bi bi-calendar4-week text-gold"></i> {{Formatted Date}}</span>
              <span><i class="bi bi-clock text-gold"></i> 7 menit baca</span>
            </div>

            <!-- Featured Image -->
            <div class="featured-image-wrap" data-aos="zoom-in">
              <img src="../assets/img/blog/{{Image1}}"
                alt="{{Image1 Alt}}" loading="lazy" decoding="async"
                onerror="this.src='../assets/img/hero/hero.webp'">
              <div class="featured-caption">{{Image1 Caption}}</div>
            </div>

            <!-- Summary Box -->
            <div class="summary-box" data-aos="fade-up">
              <h3>Ringkasan Inti</h3>
              <p><strong>Answer Capsule:</strong> {{Answer Capsule}}</p>
              <ul>
                {{Summary Bullets}}
              </ul>
            </div>

            <!-- Table of Contents Box -->
            <div class="toc-box">
              <button class="toc-toggle"
                onclick="this.classList.toggle('active'); this.nextElementSibling.classList.toggle('show')">
                Daftar Isi Artikel <i class="bi bi-chevron-right"></i>
              </button>
              <div class="toc-content">
                <ul id="auto-toc-list"></ul>
              </div>
            </div>

            <!-- Article Body Content -->
            <div class="article-body">

              {{Intro Paragraphs}}

              <h2 id="{{id-1}}">1. {{Heading 1}}</h2>
              {{Content 1}}

              <h2 id="{{id-2}}">2. {{Heading 2}}</h2>
              {{Content 2}}

              <!-- TABLE RESPONSIVE IF ANY -->
              {{Table Responsive}}

              <!-- In-Article Image 2 -->
              <div class="featured-image-wrap my-4" data-aos="zoom-in">
                <img src="../assets/img/blog/{{Image2}}"
                  alt="{{Image2 Alt}}" loading="lazy" decoding="async"
                  onerror="this.src='../assets/img/hero/hero.webp'">
                <div class="featured-caption">{{Image2 Caption}}</div>
              </div>

              <h2 id="{{id-3}}">3. {{Heading 3}}</h2>
              {{Content 3}}

              <blockquote class="article-quote">
                "{{Quote Text}}"
                <cite>&mdash; Erlang Sinatrya, Lead Project Engineer Kontraktor Surabaya</cite>
              </blockquote>

              <p class="mt-4">
                {{Closing Paragraph with internal links to /layanan/... and /galeri}}
              </p>

              <!-- Centered High-Contrast Promo Banner -->
              <a href="https://wa.me/62088989643555?text={{WA Prefilled Text}}"
                target="_blank" rel="noopener noreferrer" class="promo-banner" data-aos="fade-up">
                <img src="../assets/img/layanan/{{Banner Image}}" alt="{{Banner Alt}}" loading="lazy">
                <div class="promo-overlay">
                  <div class="promo-text">{{Banner Title}}</div>
                  <div class="promo-subtext">{{Banner Subtext}}</div>
                  <div class="promo-cta"><i class="bi bi-whatsapp"></i> Konsultasi via WhatsApp Sekarang</div>
                </div>
              </a>

            </div><!-- end article-body -->

            <!-- FAQ Mini Accordion Section -->
            <div class="article-faq" data-aos="fade-up">
              <h3>Pertanyaan Seputar {{Topic}}</h3>

              {{FAQ Items HTML}}

            </div>

            <!-- Share Buttons -->
            <div class="share-article-box" data-aos="fade-up">
              <h4>Bagikan Artikel Ini</h4>
              <div class="share-buttons-row">
                <a href="#" target="_blank" class="share-btn whatsapp" data-share="whatsapp"><i
                    class="bi bi-whatsapp"></i> WhatsApp</a>
                <a href="#" target="_blank" class="share-btn facebook" data-share="facebook"><i
                    class="bi bi-facebook"></i> Facebook</a>
                <a href="#" target="_blank" class="share-btn twitter" data-share="twitter"><i
                    class="bi bi-twitter-x"></i> Twitter</a>
                <a href="#" target="_blank" class="share-btn linkedin" data-share="linkedin"><i
                    class="bi bi-linkedin"></i> LinkedIn</a>
              </div>
            </div>

            <!-- Tags Footer -->
            <div class="article-tags-footer">
              {{Tag Pills}}
            </div>

          </div><!-- end article-main -->

          <!-- ── SIDEBAR (PATEN: AUTHOR & VERIFIED RELATED ITEMS) ───────────── -->
          <aside class="article-sidebar">

            <div class="sidebar-author-card text-center">
              <img src="../assets/img/person/erlang.webp" alt="Erlang Sinatrya" class="mx-auto d-block" onerror="this.src='../assets/img/favicon-logo.webp'">
              <h4>Erlang Sinatrya</h4>
              <div class="sidebar-social">
                <a href="https://wa.me/62088989643555" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp"><i
                    class="bi bi-whatsapp"></i></a>
                <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" aria-label="Instagram"><i
                    class="bi bi-instagram"></i></a>
                <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" aria-label="Facebook"><i
                    class="bi bi-facebook"></i></a>
              </div>
              <p class="desc">
                Erlang Sinatrya adalah Lead Project Engineer di Kontraktor Surabaya dengan keahlian khusus pada perancangan arsitektur, perhitungan estimasi RAB akurat, dan manajemen konstruksi di wilayah Jawa Timur.
              </p>
            </div>

            <div class="sidebar-related">
              <h4>Artikel Terkait</h4>

              <!-- HANYA GUNAKAN GAMBAR YANG BENAR-BENAR ADA DI ASSETS/IMG/BLOG/ -->
              {{Sidebar Related Items with <h5> and <span>}}
            </div>

          </aside>

        </div><!-- end article-layout -->
      </div>
    </section>

    <!-- ══ RELATED SERVICES & PORTFOLIO SECTION ═══════════════════════════════ -->
    <section class="related-articles-section" data-aos="fade-up">
      <div class="container">
        <h3 class="related-heading">Layanan Terkait dari Kontraktor Surabaya</h3>
        <div class="related-grid">

          <article class="related-card">
            <a href="/layanan/jasa-renovasi-surabaya">
              <img src="../assets/img/layanan/proses-renovasi-rumah-surabaya.webp"
                alt="Jasa Renovasi Bangunan &amp; Rumah Surabaya" loading="lazy">
            </a>
            <div class="related-card-content">
              <h4><a href="/layanan/jasa-renovasi-surabaya">Jasa Renovasi Bangunan</a></h4>
              <p>Solusi peremajaan rumah, peninggian lantai anti-banjir, fasad modern, dan perbaikan struktur bergaransi.</p>
              <a href="/layanan/jasa-renovasi-surabaya" class="related-read-more">Lihat Layanan <i class="bi bi-arrow-right"></i></a>
            </div>
          </article>

          <article class="related-card">
            <a href="/layanan/kontraktor-rumah-surabaya">
              <img src="../assets/img/layanan/pembangunan-rumah-modern-surabaya.webp"
                alt="Jasa Kontraktor Bangun Rumah Surabaya" loading="lazy">
            </a>
            <div class="related-card-content">
              <h4><a href="/layanan/kontraktor-rumah-surabaya">Kontraktor Bangun Rumah</a></h4>
              <p>Pembangunan rumah baru dari nol mulai tipe minimalis hingga rumah mewah dengan material SNI dan garansi struktur.</p>
              <a href="/layanan/kontraktor-rumah-surabaya" class="related-read-more">Lihat Layanan <i class="bi bi-arrow-right"></i></a>
            </div>
          </article>

          <article class="related-card">
            <a href="/layanan/rab-estimasi-biaya-surabaya">
              <img src="../assets/img/layanan/dokumen-rab-estimasi-biaya.webp"
                alt="Jasa Hitung RAB Bangunan Surabaya" loading="lazy">
            </a>
            <div class="related-card-content">
              <h4><a href="/layanan/rab-estimasi-biaya-surabaya">RAB &amp; Estimasi Biaya</a></h4>
              <p>Perhitungan estimasi anggaran transparan, analisa harga satuan AHSP, dan rincian tanpa biaya siluman.</p>
              <a href="/layanan/rab-estimasi-biaya-surabaya" class="related-read-more">Lihat Layanan <i class="bi bi-arrow-right"></i></a>
            </div>
          </article>

        </div>
      </div>
    </section>

    <!-- ══ CTA SECTION ══════════════════════════════════════════════════════════ -->
    <section id="cta" class="py-5" style="background:var(--cream);">
      <div class="container py-lg-4">
        <div class="cta-card" data-aos="zoom-in">
          <div class="cta-shape-1" aria-hidden="true"></div>
          <div class="cta-shape-2" aria-hidden="true"></div>
          <div class="cta-shape-3" aria-hidden="true"></div>

          <div class="cta-content-wrap">
            <span class="cta-label"><i class="bi bi-tools"></i> {{CTA Label}}</span>
            <h2 class="cta-title">
              {{CTA Title}}
            </h2>
            <p class="cta-desc">
              {{CTA Description}}
            </p>
            <div class="d-flex justify-content-center">
              <a id="cta-wa-primary"
                href="https://wa.me/62088989643555?text={{WA Prefilled Text}}" class="btn-gold"
                target="_blank" rel="noopener noreferrer">
                <i class="bi bi-whatsapp"></i> Konsultasi Proyek via WhatsApp
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- ══ FOOTER (PATEN: 4 KOLOM) ════════════════════════════════════════════════ -->
  <footer id="footer" role="contentinfo" aria-label="Footer Kontraktor Surabaya">
    <div class="container">
      <div class="row gy-5">

        <!-- Brand Col -->
        <div class="col-lg-4">
          <div class="footer-brand">
            <div class="footer-logo-text">Kontraktor Surabaya</div>
            <div class="footer-tagline">Jasa Konstruksi &amp; Renovasi Profesional</div>
          </div>
          <p class="footer-desc">
            Kontraktor Surabaya adalah perusahaan jasa arsitektur, konstruksi rumah, bangunan komersial,
            dan estimasi RAB profesional berbasis di Surabaya Timur yang melayani seluruh kawasan Jawa Timur.
          </p>
          <address>
            <div class="footer-contact-item">
              <i class="bi bi-whatsapp" aria-hidden="true"></i>
              <a href="https://wa.me/62088989643555" target="_blank" rel="noopener noreferrer"
                aria-label="WhatsApp Kontraktor Surabaya">0889-8964-3555</a>
            </div>
            <div class="footer-contact-item">
              <i class="bi bi-geo-alt" aria-hidden="true"></i>
              <span>Surabaya Timur, Jawa Timur, Indonesia</span>
            </div>
            <div class="footer-contact-item">
              <i class="bi bi-globe2" aria-hidden="true"></i>
              <span>kontraktorsurabaya.biz.id</span>
            </div>
          </address>
        </div>

        <!-- Layanan -->
        <div class="col-lg-2 col-md-4 col-6">
          <h3 class="footer-heading">Layanan</h3>
          <ul class="footer-links">
            <li><a href="/layanan/jasa-arsitek-surabaya">Jasa Arsitek</a></li>
            <li><a href="/layanan/kontraktor-rumah-surabaya">Kontraktor Rumah</a></li>
            <li><a href="/layanan/kontraktor-bangunan-surabaya">Kontraktor Bangunan</a></li>
            <li><a href="/layanan/jasa-renovasi-surabaya">Jasa Renovasi</a></li>
            <li><a href="/layanan/jasa-desain-interior-surabaya">Desain Interior</a></li>
            <li><a href="/layanan/rab-estimasi-biaya-surabaya">RAB &amp; Biaya</a></li>
          </ul>
        </div>

        <!-- Navigasi -->
        <div class="col-lg-2 col-md-4 col-6">
          <h3 class="footer-heading">Navigasi</h3>
          <ul class="footer-links">
            <li><a href="/">Beranda</a></li>
            <li><a href="/tentang-kami">Tentang Kami</a></li>
            <li><a href="/galeri">Galeri</a></li>
            <li><a href="/blog">Blog</a></li>
            <li><a href="/#faq">FAQ</a></li>
          </ul>
        </div>

        <!-- Area Layanan & Artikel -->
        <div class="col-lg-4 col-md-4">
          <h3 class="footer-heading">Area Layanan Jatim</h3>
          <p style="font-size:.85rem;color:rgba(250,245,237,.65);margin-bottom:1rem;">
            Melayani Surabaya, Sidoarjo, Gresik, Mojokerto, dan Madura
          </p>
          <div class="footer-area-tags mb-4">
            <span class="area-tag">Surabaya</span>
            <span class="area-tag">Surabaya Timur</span>
            <span class="area-tag">Sidoarjo</span>
            <span class="area-tag">Gresik</span>
            <span class="area-tag">Mojokerto</span>
            <span class="area-tag">Madura</span>
          </div>

          <h3 class="footer-heading" style="margin-top:1.5rem;">Artikel Populer</h3>
          <ul class="footer-links">
            <li><a href="/blog/sop-pembangunan-cafe-restoran-mep"><i class="bi bi-chevron-right"></i> SOP MEP Cafe Restoran</a></li>
            <li><a href="/blog/cara-memantau-progres-kontraktor-online"><i class="bi bi-chevron-right"></i> Memantau Progres Kontraktor</a></li>
            <li><a href="/blog/jasa-desain-rumah-2-lantai-surabaya"><i class="bi bi-chevron-right"></i> Desain Rumah 2 Lantai Surabaya</a></li>
          </ul>
        </div>

      </div>
    </div>

    <div class="container">
      <div class="footer-bottom d-flex flex-column flex-md-row justify-content-between align-items-center gap-2">
        <p>
          &copy; <span id="footer-year">2026</span> <strong>Kontraktor Surabaya</strong>. Hak cipta dilindungi
          undang-undang.
        </p>
        <p style="font-size:0.8rem;color:rgba(250,245,237,.5);">
          Jasa Kontraktor Surabaya &mdash; Berbasis Surabaya Timur, Jawa Timur
        </p>
      </div>
    </div>

  </footer>

  <!-- WhatsApp Floating Button -->
  <a href="https://wa.me/62088989643555?text={{WA Prefilled Text}}" class="wa-float" id="wa-float"
    aria-label="Hubungi Kontraktor Surabaya via WhatsApp" target="_blank" rel="noopener noreferrer">
    <i class="bi bi-whatsapp" aria-hidden="true"></i>
  </a>

  <!-- Scroll to top -->
  <button class="scroll-top" id="scroll-top-btn" aria-label="Kembali ke atas">
    <i class="bi bi-chevron-up" aria-hidden="true"></i>
  </button>

  <!-- ══ VENDOR JS ══════════════════════════════════════════════════════════ -->
  <script src="../assets/vendor/bootstrap/js/bootstrap.bundle.min.js" defer></script>
  <script src="../assets/vendor/aos/aos.js" defer></script>
  <script src="../assets/vendor/purecounter/purecounter_vanilla.js" defer></script>
  <script src="../assets/vendor/glightbox/js/glightbox.min.js" defer></script>
  <script src="../assets/vendor/imagesloaded/imagesloaded.pkgd.min.js" defer></script>
  <script src="../assets/vendor/isotope-layout/isotope.pkgd.min.js" defer></script>
  <script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js" defer></script>

  <!-- Main JS -->
  <script src="../assets/js/main.js" defer></script>

  <!-- Article Interactive Scripts -->
  <script>
    document.addEventListener('DOMContentLoaded', function () {
      // 1. Auto-generate Table of Contents dari H2 & H3
      const tocList = document.getElementById('auto-toc-list');
      const headings = document.querySelectorAll('.article-body h2, .article-body h3');

      headings.forEach(function (heading, index) {
        if (!heading.id) heading.id = 'section-' + index;

        const li = document.createElement('li');
        if (heading.tagName === 'H3') li.style.paddingLeft = '16px';

        const a = document.createElement('a');
        a.href = '#' + heading.id;
        a.textContent = heading.textContent;
        li.appendChild(a);
        if (tocList) tocList.appendChild(li);
      });

      // 2. FAQ mini accordion toggle
      document.querySelectorAll('.faq-mini-question').forEach(function (btn) {
        btn.addEventListener('click', function () {
          const item = btn.closest('.faq-mini-item');
          if (item) item.classList.toggle('active');
        });
      });

      // 3. Auto-populate share button URLs
      const pageUrl = encodeURIComponent(window.location.href);
      const pageTitle = encodeURIComponent(document.title);

      const shareLinks = {
        whatsapp: 'https://wa.me/?text=' + pageTitle + '%20' + pageUrl,
        facebook: 'https://www.facebook.com/sharer/sharer.php?u=' + pageUrl,
        twitter: 'https://twitter.com/intent/tweet?url=' + pageUrl + '&text=' + pageTitle,
        linkedin: 'https://www.linkedin.com/sharing/share-offsite/?url=' + pageUrl
      };

      document.querySelectorAll('[data-share]').forEach(function (btn) {
        const type = btn.getAttribute('data-share');
        if (shareLinks[type]) btn.setAttribute('href', shareLinks[type]);
      });

      // 4. Footer year
      var yearEl = document.getElementById('footer-year');
      if (yearEl) yearEl.textContent = new Date().getFullYear();
    });
  </script>

</body>

</html>
```

---

## 2. INTEGRASI SISTEMIK WAJIB SETIAP POSTING ARTIKEL
1. **`sitemap.xml`**:
   - Tambahkan URL artikel baru dengan format standar link halaman (`<loc>`, `<lastmod>`, `<changefreq>`, `<priority>`) tanpa menyertakan tag `<image:image>`.
   - **MUTLAK**: Update `<lastmod>` pada URL `#3 Blog Index` (`https://kontraktorsurabaya.biz.id/blog`) ke tanggal artikel terbaru.
2. **`blog.html`**:
   - Tambahkan Card artikel di urutan paling pertama grid (`.portfolio-grid`) dengan filter Isotope yang sesuai.
   - Update `ItemList` Schema JSON-LD (`numberOfItems: N` dan masukkan `position: 1` artikel baru, lalu geser posisi artikel lain secara sekuensial).
3. **`llms.txt`**:
   - Tambahkan artikel baru ke dalam klaster topiknya masing-masing di file `llms.txt` dengan format: `- [Judul Artikel](URL): Ringkasan deskripsi`.
4. **Validasi Fisik Gambar**:
   - Seluruh path gambar (`<img src="...">`) di dalam artikel, banner, sidebar, dan kartu terkait **WAJIB diverifikasi ada secara fisik** di `assets/img/blog/` atau `assets/img/layanan/` sebelum di-deploy.
