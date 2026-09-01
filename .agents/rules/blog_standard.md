# Standard Template & Aturan Baku Pembuatan Artikel Blog Kontraktor Surabaya

Aturan ini bersifat **MUTLAK & PATEN**. Dilarang mengubah, menambah, menghapus, atau mengutak-atik struktur HTML, CSS (`main.css`/`main.min.css`), dan JS (`main.js`).

## 1. Jadwal & Volume Publikasi
- **Volume:** Tepat 3 artikel per hari kalender.
- **Penulis Mutlak:** `Erlang Sinatrya` (`../assets/img/person/erlang.webp`).

## 2. Struktur HTML Baku Artikel Blog (`blog/*.html`)

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
  <link rel="preload" as="style" href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,600&display=swap">
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,600&display=swap" media="print" onload="this.media='all'">
  <noscript><link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,600&display=swap"></noscript>

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

  <!-- Schema Markup JSON-LD (LocalBusiness, Article, BreadcrumbList, FAQPage) -->
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

  <!-- Navbar -->
  <!-- Breadcrumb Bar -->
  <div class="breadcrumb-bar">
    <div class="container">
      <a href="/"><i class="bi bi-house-door-fill me-1"></i> Beranda</a>
      <span class="separator"><i class="bi bi-chevron-right"></i></span>
      <a href="/blog">Blog</a>
      <span class="separator"><i class="bi bi-chevron-right"></i></span>
      <span>{{Short Title}}</span>
    </div>
  </div>

  <main class="main" id="main-content">
    <section class="section pt-4 pb-5" style="background:var(--white);">
      <div class="container">
        <div class="article-layout">
          <div class="article-main">

            <h1 class="article-title" data-aos="fade-up">{{H1 Title}}</h1>

            <div class="article-top-meta" data-aos="fade-up" data-aos-delay="100">
              <div class="meta-author">
                <img src="../assets/img/person/erlang.webp" alt="Erlang Sinatrya" onerror="this.src='../assets/img/favicon-logo.webp'">
                <span>Erlang Sinatrya</span>
              </div>
              <span><i class="bi bi-calendar4-week text-gold"></i> {{Formatted Date}}</span>
              <span><i class="bi bi-clock text-gold"></i> 5 menit baca</span>
            </div>

            <!-- Featured Image -->
            <div class="featured-image-wrap" data-aos="zoom-in">
              <img src="../assets/img/blog/{{Image1}}" alt="{{Image1 Alt}}" loading="lazy" decoding="async" onerror="this.src='../assets/img/hero/hero.webp'">
              <div class="featured-caption">{{Image1 Alt}}</div>
            </div>

            <!-- Summary Box -->
            <div class="summary-box" data-aos="fade-up">
              <h3>Ringkasan Inti</h3>
              <p><strong>Answer Capsule:</strong> {{Answer Capsule}}</p>
              <ul>
                {{Summary Bullet Points}}
              </ul>
            </div>

            <!-- TOC Box -->
            <div class="toc-box">
              <button class="toc-toggle" onclick="this.classList.toggle('active'); this.nextElementSibling.classList.toggle('show')">
                Daftar Isi Artikel <i class="bi bi-chevron-right"></i>
              </button>
              <div class="toc-content">
                <ul id="auto-toc-list"></ul>
              </div>
            </div>

            <!-- Article Body -->
            <div class="article-body">
              {{Intro Paragraph}}

              <h2 id="{{id-1}}">1. {{Heading 1}}</h2>
              {{Content 1}}

              <h2 id="{{id-2}}">2. {{Heading 2}}</h2>
              {{Content 2}}

              <!-- In-Article Second Image -->
              <figure class="body-figure" data-aos="fade-up">
                <img src="../assets/img/blog/{{Image2}}" alt="{{Image2 Alt}}" loading="lazy" decoding="async">
                <figcaption>{{Image2 Alt}}</figcaption>
              </figure>

              <h2 id="{{id-3}}">3. {{Heading 3}}</h2>
              {{Content 3}}

              <h2 id="{{id-4}}">4. {{Heading 4}}</h2>
              {{Content 4}}

              <h2 id="{{id-5}}">5. {{Heading 5}}</h2>
              {{Content 5}}

              <h2 id="{{id-6}}">6. {{Heading 6}}</h2>
              {{Content 6}}

              <blockquote class="article-quote">
                <p>"{{Quote Text}}"</p>
                <span class="quote-author">— Erlang Sinatrya, Lead Project Engineer Kontraktor Surabaya</span>
              </blockquote>

              <p class="mt-4">
                {{Closing Paragraph with <a href="/galeri" class="fw-bold text-maroon">galeri proyek kami</a> dan link layanan}}
              </p>

              <!-- Centered High-Contrast Promo Banner -->
              <a href="https://wa.me/62088989643555?text={{WA Text}}" target="_blank" class="promo-banner" data-aos="fade-up">
                <img src="../assets/img/layanan/{{Relevant Service Banner}}" alt="{{Banner Alt}}" loading="lazy">
                <div class="promo-overlay">
                  <div class="promo-text">{{Banner Title}}</div>
                  <div class="promo-subtext">{{Banner Subtext}}</div>
                  <div class="promo-cta"><i class="bi bi-whatsapp"></i> Chat WhatsApp Sekarang</div>
                </div>
              </a>

            </div> <!-- /article-body -->

            <!-- Mini FAQ Accordion -->
            <div class="article-faq" data-aos="fade-up">
              <h3>Pertanyaan Seputar {{Topik}}</h3>
              {{FAQ Items HTML with class .faq-mini-item, .faq-mini-question, .faq-mini-answer}}
            </div>

            <!-- Share Buttons -->
            <div class="share-article-box" data-aos="fade-up">
              <h4>Bagikan Artikel Ini</h4>
              <div class="share-buttons-row">
                <a href="#" target="_blank" class="share-btn whatsapp" data-share="whatsapp"><i class="bi bi-whatsapp"></i> WhatsApp</a>
                <a href="#" target="_blank" class="share-btn facebook" data-share="facebook"><i class="bi bi-facebook"></i> Facebook</a>
                <a href="#" target="_blank" class="share-btn twitter" data-share="twitter"><i class="bi bi-twitter-x"></i> Twitter</a>
                <a href="#" target="_blank" class="share-btn linkedin" data-share="linkedin"><i class="bi bi-linkedin"></i> LinkedIn</a>
              </div>
            </div>

            <!-- Tags Footer -->
            <div class="article-tags-footer">
              {{Tag Pills}}
            </div>

          </div> <!-- /article-main -->

          <!-- Sidebar -->
          <aside class="article-sidebar">
            <div class="sidebar-author-card text-center">
              <img src="../assets/img/person/erlang.webp" alt="Erlang Sinatrya" class="mx-auto d-block" onerror="this.src='../assets/img/favicon-logo.webp'">
              <h4>Erlang Sinatrya</h4>
              <div class="sidebar-social">
                <a href="https://wa.me/62088989643555" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp"><i class="bi bi-whatsapp"></i></a>
                <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" aria-label="Instagram"><i class="bi bi-instagram"></i></a>
                <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" aria-label="Facebook"><i class="bi bi-facebook"></i></a>
              </div>
              <p class="desc">
                Erlang Sinatrya adalah Lead Project Engineer di Kontraktor Surabaya dengan keahlian khusus pada perancangan arsitektur, perhitungan estimasi RAB akurat, dan manajemen konstruksi di wilayah Jawa Timur.
              </p>
            </div>
            <div class="sidebar-related">
              <h4>Artikel Terkait</h4>
              {{Related Items}}
            </div>
          </aside>
        </div>
      </div>
    </section>

    <!-- Related Services -->
    <!-- CTA Section -->
  </main>

  <!-- Footer -->

  <!-- Standard Scripts -->
  <script src="../assets/vendor/bootstrap/js/bootstrap.bundle.min.js" defer></script>
  <script src="../assets/vendor/aos/aos.js" defer></script>
  <script src="../assets/vendor/purecounter/purecounter_vanilla.js" defer></script>
  <script src="../assets/vendor/glightbox/js/glightbox.min.js" defer></script>
  <script src="../assets/vendor/imagesloaded/imagesloaded.pkgd.min.js" defer></script>
  <script src="../assets/vendor/isotope-layout/isotope.pkgd.min.js" defer></script>
  <script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js" defer></script>
  <script src="../assets/js/main.js" defer></script>

  <!-- Article Interactive Scripts -->
  <script>
    document.addEventListener('DOMContentLoaded', function () {
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

      document.querySelectorAll('.faq-mini-question').forEach(function (btn) {
        btn.addEventListener('click', function () {
          const item = btn.closest('.faq-mini-item');
          if (item) item.classList.toggle('active');
        });
      });

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

      var yearEl = document.getElementById('footer-year');
      if (yearEl) yearEl.textContent = new Date().getFullYear();
    });
  </script>
</body>
</html>
```

## 3. Integrasi Wajib untuk Setiap Artikel Baru
1. Daftarkan kartu artikel di **bagian teratas** grid artikel di [`blog.html`](file:///d:/TUGAS%20KULIAH/Project%20MKI/ProjectBootstrapAktif/kontraktorsurabaya/blog.html) dengan filter class yang sesuai (`filter-arsitek`, `filter-rumah`, `filter-bangunan`, `filter-renovasi`, `filter-interior`, `filter-rab`).
2. Tambahkan entri URL baru di [`sitemap.xml`](file:///d:/TUGAS%20KULIAH/Project%20MKI/ProjectBootstrapAktif/kontraktorsurabaya/sitemap.xml) lengkap dengan tag `<image:image>` dan perbarui `<lastmod>` halaman `blog.html`.
3. **JANGAN PERNAH** memodifikasi `main.css`, `main.min.css`, ataupun `main.js`.
