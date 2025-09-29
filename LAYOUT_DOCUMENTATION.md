# NaviKarir - Layout Documentation

## Struktur Layout

Proyek ini menggunakan sistem layout yang dapat di-extend untuk membuat halaman-halaman yang konsisten. Terdapat dua layout utama:

### 1. Layout Pemberi Kerja (`pemberi_kerja/layout.html`)
Layout untuk dashboard dan halaman-halaman yang berkaitan dengan manajemen lowongan kerja.

### 2. Layout Pencari Kerja (`pencari_kerja/layout.html`)  
Layout untuk pencari kerja dengan fitur pencarian dan manajemen lamaran.

## Fitur Layout

### Komponen Utama:
- **Header Navigation**: Navigation bar dengan menu utama dan user dropdown
- **Sidebar**: Menu navigasi samping dengan ikon dan status aktif
- **Main Content Area**: Area konten utama dengan sistem grid Bootstrap
- **Footer**: Footer dengan informasi copyright dan link bantuan
- **Responsive Design**: Optimized untuk desktop, tablet, dan mobile

### CSS Framework:
- **Bootstrap 5.3.0**: Untuk grid system dan komponen UI
- **Font Awesome 6.4.0**: Untuk ikon
- **Google Fonts (Inter)**: Typography yang modern
- **Custom CSS Variables**: Untuk konsistensi warna dan theming

### JavaScript Features:
- Mobile sidebar toggle
- Active navigation highlighting  
- Alert auto-hide functionality
- Utility functions untuk interaksi umum

## Cara Menggunakan Layout

### Template Block System

Layout menggunakan sistem template block yang dapat di-override:

```html
<!-- Dalam halaman yang meng-extend layout -->

{% block title %}Judul Halaman - NaviKarir{% endblock %}

{% block page_title %}Judul Halaman{% endblock %}

{% block page_subtitle %}Deskripsi singkat halaman{% endblock %}

{% block breadcrumb_active %}Nama Halaman{% endblock %}

{% block content %}
<!-- Konten halaman spesifik di sini -->
{% endblock %}

{% block extra_css %}
<!-- CSS tambahan spesifik halaman -->
{% endblock %}

{% block extra_js %}  
<!-- JavaScript tambahan spesifik halaman -->
{% endblock %}
```

### Active Navigation

Untuk mengaktifkan menu navigasi yang sesuai:

```html
{% block nav_dashboard %}active{% endblock %}
{% block nav_lowongan %}active{% endblock %}
{% block nav_pelamar %}active{% endblock %}
<!-- dll sesuai menu yang aktif -->
```

## Contoh Implementasi

### 1. Dashboard Pemberi Kerja (`pemberi_kerja/dashboard.html`)

Contoh halaman dashboard lengkap dengan:
- Statistics cards
- Chart visualisasi
- Recent activities  
- Quick actions
- Responsive layout

### 2. Halaman Pencari Kerja

Untuk membuat halaman pencari kerja, copy struktur dari layout dan sesuaikan:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <!-- Include semua CSS dari layout -->
</head>
<body>
    <!-- Include semua struktur dari layout -->
    
    <!-- Override konten di main content -->
    <main class="col-md-9 col-lg-10 ms-sm-auto">
        <div class="main-content">
            <div class="page-header">
                <h1 class="page-title">Judul Halaman Anda</h1>
                <p class="page-subtitle">Deskripsi halaman</p>
            </div>
            
            <!-- Konten spesifik halaman -->
            
        </div>
    </main>
</body>
</html>
```

## CSS Variables

Layout menggunakan CSS custom properties untuk konsistensi:

```css
:root {
    --primary-color: #2563eb;      /* Biru untuk pemberi kerja */
    --primary-color: #059669;      /* Hijau untuk pencari kerja */
    --secondary-color: #64748b;
    --accent-color: #f59e0b;
    --success-color: #10b981;
    --danger-color: #ef4444;
    --light-bg: #f8fafc;
    --dark-text: #1e293b;
    --border-color: #e2e8f0;
}
```

## Komponen UI yang Tersedia

### 1. Cards
- `.card`: Card dasar dengan hover effect
- `.job-card`: Card khusus untuk lowongan kerja
- `.stats-card`: Card untuk statistik dengan gradient background

### 2. Buttons  
- `.btn-primary`: Button utama
- `.btn-outline-primary`: Button outline
- Berbagai ukuran: `.btn-sm`, `.btn-lg`

### 3. Alerts
- Function `showAlert(message, type)` untuk menampilkan notifikasi
- Auto-hide setelah 5 detik

### 4. Status Badges
- `.badge-applied`: Status lamaran dikirim
- `.badge-interview`: Status interview
- `.badge-accepted`: Status diterima  
- `.badge-rejected`: Status ditolak

## Responsivitas

Layout fully responsive dengan breakpoints:
- **Mobile (< 768px)**: Sidebar collapse, stack layout
- **Tablet (768px - 1024px)**: Sidebar visible, responsive grid
- **Desktop (> 1024px)**: Full layout dengan sidebar expanded

## Browser Support

- Chrome 90+
- Firefox 88+  
- Safari 14+
- Edge 90+

## Development Notes

1. **File Organization**: Pisahkan layout dari halaman spesifik
2. **CSS Modularity**: Gunakan CSS variables untuk konsistensi
3. **JavaScript**: Modular functions yang reusable
4. **Performance**: Optimized dengan CDN dan minimal custom CSS
5. **Accessibility**: Semantic HTML dan ARIA labels

## Update dan Maintenance

Untuk mengupdate layout:
1. Edit file layout utama (`layout.html`)
2. Test pada semua halaman yang meng-extend layout
3. Update dokumentasi jika ada perubahan major
4. Maintain backward compatibility untuk halaman existing

---

**Catatan**: Layout ini dirancang untuk kemudahan penggunaan dan maintenance. Semua halaman baru disarankan untuk meng-extend salah satu dari layout yang tersedia.