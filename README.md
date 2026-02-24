# 🚀 Portfolio Website — Pebe Weiii

> Website Portfolio statis berbasis **Vue JS 3** + **Bootstrap 5** dengan tiga section utama: Home, About Me, dan Certificates.

---

## 🖼️ Tampilan Setiap Section / Fitur

### 1. Navbar
- Fixed sticky navbar dengan backdrop blur
- Brand logo dengan dot animasi
- Responsive collapse pada mobile (hamburger menu)
- Tombol **Hire Me** dengan gradient styling
- Active link highlighting saat hover

### 2. Section Home (Hero)
- Animated grid background + glowing orbs
- Status badge "Available for work" dengan dot blink animation
- Heading besar dengan nama dan role (gradient text)
- Tagline / bio singkat
- Dua tombol CTA: **View My Work** & **About Me**
- Social media icon links (GitHub, LinkedIn, Instagram, Email)
- Foto profil dengan glowing ring animation
- Floating badges: Years of Experience & Total Projects
- Scroll down indicator dengan line animation

### 3. Section About Me
- Foto profil dengan dekorasi offset border
- Info grid (Nama, Lokasi, Degree, Email, Freelance, Languages)
- Deskripsi diri dalam paragraf
- **Technical Skills** menggunakan Bootstrap 5 Progress Bar dengan warna gradient berbeda per skill
- **Experience Timeline** dengan garis vertikal, dot glowing, periode, posisi, perusahaan, dan deskripsi

### 4. Section Certificates
- Filter tab per kategori (All, Web Dev, Vue JS, CSS, Design, DevOps)
- Grid 3 kolom (responsif: 1 → 2 → 3 kolom)
- Setiap card memiliki:
  - Colorful top section dengan ikon Bootstrap Icons
  - Category badge
  - Judul sertifikat, nama issuer, dan tanggal
  - Tombol "View Certificate"
- Empty state ketika filter tidak ada hasil

### 5. Footer
- Brand logo
- Copyright dengan tahun dinamis
- Navigation links

---

## 💻 Penjelasan Code Setiap Section

### `src/main.js`
```js
import { createApp } from 'vue'
import App from './App.vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap/dist/js/bootstrap.bundle.min.js'
import './assets/style.css'

createApp(App).mount('#app')  // Mount Vue ke elemen #app
```
Entry point aplikasi. Mengimport Bootstrap 5, CSS global, dan me-mount App ke DOM.

---

### `src/App.vue` — Root Component
```vue
<template>
  <div id="portfolio-app">
    <TheNavbar />
    <HelloWorld />    <!-- Hero Section -->
    <TheWelcome />    <!-- About Me Section -->
    <WelcomeItem />   <!-- Certificates Section -->
    <footer>...</footer>
  </div>
</template>

<script>
export default {
  components: { TheNavbar, HelloWorld, TheWelcome, WelcomeItem },
  data() {
    return { currentYear: new Date().getFullYear() }
  }
}
</script>
```
Merakit semua komponen menjadi satu halaman. `currentYear` digenerate dinamis.

---

### `src/components/TheNavbar.vue` — Navbar
```vue
<!-- Bootstrap 5: navbar navbar-expand-lg fixed-top -->
<nav class="navbar navbar-expand-lg fixed-top">
  <a class="navbar-brand">{{ brand }}<span class="brand-accent">.</span></a>
  <!-- v-for untuk render nav links -->
  <li v-for="link in navLinks" :key="link.href">
    <a class="nav-link" :href="link.href">{{ link.label }}</a>
  </li>
</nav>
```
Menggunakan **Bootstrap 5 navbar** untuk responsive navigation. Data `navLinks` array di-render dengan `v-for`.

---

### `src/components/HelloWorld.vue` — Hero Section
```vue
<h1 class="hero-title">
  Hi, I'm <span class="highlight">{{ name }}</span>
  <span class="hero-role">{{ role }}</span>
</h1>

<!-- v-for untuk social media links -->
<a v-for="s in socials" :key="s.icon" :href="s.url">
  <i :class="'bi bi-' + s.icon"></i>
</a>
```
**Interpolasi Vue** `{{ }}` untuk nama dan role. `v-for` untuk merender social links secara dinamis. `:class` binding untuk icon Bootstrap Icons.

---

### `src/components/TheWelcome.vue` — About Me
```vue
<!-- Bootstrap 5 Progress Bar dengan :style binding -->
<div class="progress skill-progress">
  <div class="progress-bar"
       :style="{ width: skill.pct + '%', background: skill.color }">
  </div>
</div>

<!-- v-for untuk experience timeline -->
<div v-for="exp in experience" :key="exp.title" class="exp-item">
  <span class="exp-period">{{ exp.period }}</span>
  <h5 class="exp-title">{{ exp.title }}</h5>
</div>
```
**Bootstrap 5 Progress Bar** dikontrol dengan `:style` binding Vue untuk width dan warna dinamis per skill. Experience dirender dengan `v-for`.

---

### `src/components/WelcomeItem.vue` — Certificates
```vue
<!-- Filter dengan @click dan :class binding -->
<button v-for="cat in certCategories" :key="cat"
        :class="{ active: activeCategory === cat }"
        @click="activeCategory = cat">
  {{ cat }}
</button>

<!-- Computed property untuk filtering -->
computed: {
  filteredCerts() {
    if (this.activeCategory === 'All') return this.certificates
    return this.certificates.filter(c => c.category === this.activeCategory)
  }
}
```
Filter interaktif menggunakan **Vue event handler** `@click`, **class binding** `:class`, dan **computed property** untuk memo-filter data sertifikat.

---

### `src/assets/style.css` — Global Styles
- CSS Variables (`:root`) untuk konsistensi warna dan font
- Dark theme dengan `--clr-bg: #0a0c10`
- Accent color `--clr-accent: #4fffb0` (neon green)
- Keyframe animations: `floatOrb`, `blinkPulse`, `ringGlow`, `floatBadge`
- Media queries untuk responsive design

---

## 🛠️ Teknologi yang Digunakan

| Teknologi | Versi | Kegunaan |
|---|---|---|
| **HTML5** | — | Struktur dasar halaman web |
| **CSS3** | — | Styling, animasi, CSS Variables, media queries |
| **Bootstrap 5** | 5.3.3 | Grid system, navbar, progress bar, cards, utilities |
| **Bootstrap Icons** | 1.11.3 | Icon set untuk UI elements |
| **Vue JS** | 3.4.x | Reaktivitas data, interpolasi, v-for, computed, events |
| **Vite** | 5.x | Build tool & dev server |
| **Google Fonts** | — | Font Syne (display) + Outfit (body) |

---

## 📁 Struktur Project

```
PEBEWEIII_MINPRO1/
├── index.html              # Entry HTML (Vite)
├── package.json            # Dependencies
├── vite.config.js          # Vite configuration
├── preview.html            # Standalone preview (CDN, tanpa npm)
└── src/
    ├── main.js             # Vue app entry point + .mount('#app')
    ├── App.vue             # Root component
    ├── assets/
    │   └── style.css       # Global CSS styles
    └── components/
        ├── TheNavbar.vue   # Sticky navigation bar
        ├── HelloWorld.vue  # Hero / Home section
        ├── TheWelcome.vue  # About Me section
        └── WelcomeItem.vue # Certificates section
```

---

## ⚙️ Cara Menjalankan

### Dengan Vite (development):
```bash
npm install
npm run dev
```
Buka `http://localhost:5173`

### Tanpa npm (langsung buka):
Buka file `preview.html` langsung di browser — sudah menggunakan CDN untuk Vue 3 dan Bootstrap 5.

---

## ✨ Fitur Vue JS yang Digunakan

| Fitur | Contoh Penggunaan |
|---|---|
| `{{ interpolation }}` | `{{ name }}`, `{{ role }}`, `{{ cert.title }}` |
| `v-for` | Render navLinks, socials, skills, experience, certificates |
| `v-if` | Tampilkan empty state jika filteredCerts kosong |
| `:class` (v-bind) | Active state pada filter button |
| `:style` (v-bind) | Dynamic width & color pada progress bar |
| `@click` (v-on) | Filter category selection |
| `computed` | `filteredCerts`, `certCategories` |
| `data()` | Semua data statis (nama, skills, certificates, dll) |
| `.mount('#app')` | Menghubungkan Vue ke DOM element |
| `components: {}` | Registrasi child components di App.vue |

---

## ✨ Fitur Bootstrap 5 yang Digunakan

- `navbar`, `navbar-expand-lg`, `navbar-brand`, `navbar-toggler`, `collapse`
- `container`, `row`, `col-*`, `col-sm-*`, `col-lg-*` (Grid System)
- `d-flex`, `gap-*`, `justify-content-*`, `align-items-*`
- `progress`, `progress-bar` (Skills)
- `btn`, `btn-*` (CTA buttons, filter)
- `h-100`, `mt-*`, `mb-*`, `py-*`, `ms-auto` (Spacing utilities)
- Responsive breakpoints: `sm`, `lg`, `md`
