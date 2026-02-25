<p align="center">
  <h1 align="center">🌌 MY Portfolio Website GW</h1>
  <p align="center">
    Built with Vue 3 + Bootstrap 5 <br/>
    Clean • Animated • Responsive • Professional
  </p>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Vue-3.4.x-42b883?style=for-the-badge&logo=vue.js&logoColor=white"/>
  <img src="https://img.shields.io/badge/Bootstrap-5.3.3-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white"/>
  <img src="https://img.shields.io/badge/Vite-5.x-646CFF?style=for-the-badge&logo=vite&logoColor=white"/>
  <img src="https://img.shields.io/badge/Status-Completed-00ff99?style=for-the-badge"/>
</p>

---

## ✨ About This Project

A modern dark-themed portfolio website built using **Vue JS 3** and **Bootstrap 5**.  
Designed with smooth animations, neon accent styling, and a fully responsive layout.

This project demonstrates:
- Component-based architecture
- Vue reactivity system
- Dynamic filtering
- Modern UI/UX styling
- Clean code structure

---

# 🖼️ Live Preview

<img width="1917" alt="preview1" src="https://github.com/user-attachments/assets/ef8dd368-e1b5-4795-9bec-c74befecd860" />
<img width="1918" alt="preview2" src="https://github.com/user-attachments/assets/341b7421-df1a-4cf3-9d48-4245bfe9f434" />
<img width="1920" alt="preview3" src="https://github.com/user-attachments/assets/772f289a-2243-4321-97ee-bd90eda864a4" />
<img width="1920" alt="preview4" src="https://github.com/user-attachments/assets/65994724-e1dc-4cf0-915e-23483a144ff7" />
<img width="1920" alt="preview5" src="https://github.com/user-attachments/assets/71c99402-3047-492b-afa2-fc1122a60619" />

---

# 🚀 Core Features

## 🧭 Smart Navbar
- Sticky & backdrop blur
- Responsive hamburger menu
- Smooth hover animations
- Gradient CTA button

## 🌟 Hero Section
- Animated glowing background
- Gradient typography
- Dynamic social icons (Vue loop)
- Call-to-action buttons
- Floating badges
- Scroll indicator animation

## 👨‍💻 About Me
- Personal info grid
- Dynamic progress bars (Vue `:style`)
- Experience timeline
- Clean responsive layout

## 📜 Certificates
- Category filtering system
- Vue computed properties
- Responsive 3-column grid
- Empty state handling
- Interactive cards

## 🦶 Footer
- Dynamic current year
- Minimalist design
- Navigation links

---

# 🧠 Vue Concepts Implemented

```js
{{ interpolation }}
v-for
v-if
:class binding
:style binding
@click event
computed properties
data()
component system
.mount('#app')
```

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
