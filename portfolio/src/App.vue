<template>
  <!-- ==========================================
       APP.VUE — Root Component
       Mounts all section components in order:
       Navbar → Hero → About → Certificates → Footer
  ========================================== -->
  <div id="portfolio-app">

    <!-- Sticky Navigation Bar -->
    <TheNavbar />

    <!-- Main Content Sections -->
    <main>
      <!-- Section 1: Hero / Home -->
      <HelloWorld />

      <!-- Section 2: About Me -->
      <TheWelcome />

      <!-- Section 3: Certificates -->
      <WelcomeItem />
    </main>

    <!-- Footer -->
    <footer class="site-footer">
      <div class="container">
        <div class="row align-items-center py-4">
          <div class="col-md-6 text-center text-md-start mb-3 mb-md-0">
            <span class="footer-brand">IYAS<span class="brand-accent">.</span></span>
            <p class="footer-copy mt-1 mb-0">© {{ currentYear }} Pebe Weiii. All rights reserved.</p>
          </div>
          <div class="col-md-6 text-center text-md-end">
            <div class="footer-links d-flex gap-3 justify-content-center justify-content-md-end">
              <a href="#home">Home</a>
              <a href="#about">About</a>
              <a href="#certificates">Certificates</a>
            </div>
          </div>
        </div>
      </div>
    </footer>

  </div>
</template>

<script>
// Import all section components
import TheNavbar    from './components/TheNavbar.vue'
import HelloWorld   from './components/HelloWorld.vue'
import TheWelcome   from './components/TheWelcome.vue'
import WelcomeItem  from './components/WelcomeItem.vue'

export default {
  name: 'App',

  // Register child components
  components: {
    TheNavbar,
    HelloWorld,
    TheWelcome,
    WelcomeItem,
  },

  data() {
    return {
      // Dynamic year for footer copyright
      currentYear: new Date().getFullYear(),
    }
  },
}
</script>
