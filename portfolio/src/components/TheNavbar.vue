<template>
  <!-- ==========================================
       NAVBAR COMPONENT
       Bootstrap 5: navbar, navbar-expand-lg,
       fixed-top, navbar-brand, nav-link
  ========================================== -->
  <nav class="navbar navbar-expand-lg fixed-top">
    <div class="container">

      <!-- Brand Logo -->
      <a class="navbar-brand" href="#home">
        <span class="brand-dot"></span>{{ brand }}<span class="brand-accent">.</span>
      </a>

      <!-- Mobile Toggler -->
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navMenu"
        aria-controls="navMenu"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <i class="bi bi-list" style="color: var(--clr-text); font-size: 1.4rem;"></i>
      </button>

      <!-- Nav Links -->
      <div class="collapse navbar-collapse" id="navMenu">
        <ul class="navbar-nav ms-auto gap-lg-1 align-items-lg-center">
          <li class="nav-item" v-for="link in navLinks" :key="link.href">
            <a class="nav-link" :href="link.href">{{ link.label }}</a>
          </li>
          <li class="nav-item ms-lg-2">
            <a class="btn btn-hire" href="mailto:pebe@example.com">Hire Me</a>
          </li>
        </ul>
      </div>

    </div>
  </nav>
</template>

<script>
export default {
  name: 'TheNavbar',
  data() {
    return {
      // Brand text shown in navbar logo
      brand: 'IYAS',

      // Navigation links array — easy to extend
      navLinks: [
        { label: 'Home',         href: '#home' },
        { label: 'About Me',     href: '#about' },
        { label: 'Certificates', href: '#certificates' },
      ],
    }
  },
}
</script>
