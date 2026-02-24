# 🌌 MY Portofolio gw - PEBEWEI  
> Built with Vue 3 + Bootstrap 5  
> Clean. Responsive. Interactive.

---

## 🚀 Overview

Portfolio website statis dengan desain modern bertema dark neon.  
Menggunakan **Vue JS 3** untuk reaktivitas dan **Bootstrap 5** untuk layout & UI system.

Website ini terdiri dari 3 section utama:
- 🏠 Home (Hero Section)
- 👨‍💻 About Me
- 📜 Certificates

Dirancang dengan animasi halus, gradient styling, dan tampilan profesional.

---

## 🖼️ Preview

<img width="1917" alt="preview1" src="https://github.com/user-attachments/assets/ef8dd368-e1b5-4795-9bec-c74befecd860" />
<img width="1918" alt="preview2" src="https://github.com/user-attachments/assets/341b7421-df1a-4cf3-9d48-4245bfe9f434" />
<img width="1920" alt="preview3" src="https://github.com/user-attachments/assets/772f289a-2243-4321-97ee-bd90eda864a4" />
<img width="1920" alt="preview4" src="https://github.com/user-attachments/assets/65994724-e1dc-4cf0-915e-23483a144ff7" />
<img width="1920" alt="preview5" src="https://github.com/user-attachments/assets/71c99402-3047-492b-afa2-fc1122a60619" />

---

# ✨ Features

## 🔹 Navbar
- Sticky fixed navigation
- Backdrop blur effect
- Responsive hamburger menu
- Active link highlighting
- Gradient "Hire Me" button

## 🔹 Hero Section
- Animated glowing background
- Gradient name text
- Dynamic social media icons
- CTA buttons (View Work & About Me)
- Profile image with glow animation
- Floating badges
- Scroll indicator animation

## 🔹 About Me
- Personal information grid
- Technical skills with dynamic progress bar
- Experience timeline
- Clean responsive layout

## 🔹 Certificates
- Category filter tabs
- Computed property filtering (Vue)
- Responsive grid layout
- Certificate cards with icon & badge
- Empty state handling

## 🔹 Footer
- Dynamic current year
- Navigation links
- Clean minimal design

---

# 🛠️ Tech Stack

| Technology | Purpose |
|------------|----------|
| Vue JS 3 | Reactive UI & Components |
| Bootstrap 5 | Layout & UI Utilities |
| Bootstrap Icons | Icon Library |
| Vite | Dev Server & Build Tool |
| CSS3 | Custom Styling & Animations |
| Google Fonts | Typography |

---

# 🧠 Vue Concepts Used

- `{{ interpolation }}`
- `v-for`
- `v-if`
- `:class` binding
- `:style` binding
- `@click` event handling
- `computed`
- `data()`
- Component system
- `.mount('#app')`

---

# 📁 Project Structure

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
