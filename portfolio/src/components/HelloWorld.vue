<template>
  <!-- ==========================================
       HERO SECTION (Home)
       Bootstrap 5: container, row, col-lg-*, d-flex
       Vue: v-for, interpolation {{ }}
  ========================================== -->
  <section id="home" class="hero-section">

    <!-- Decorative background elements -->
    <div class="hero-bg-grid"></div>
    <div class="hero-orb hero-orb-1"></div>
    <div class="hero-orb hero-orb-2"></div>

    <div class="container">
      <div class="row align-items-center min-vh-100 py-5">

        <!-- ── Left: Text Content ── -->
        <div class="col-lg-7 hero-text-col">

          <!-- "Available" status tag -->
          <div class="hero-tag mb-3 fade-in-up delay-1">
            <span class="dot-blink"></span> {{ statusTag }}
          </div>

          <!-- Main heading with name + role -->
          <h1 class="hero-title fade-in-up delay-2">
            Hi, I'm <span class="highlight">{{ name }}</span><br/>
            <span class="hero-role">{{ role }}</span>
          </h1>

          <!-- Short tagline / bio -->
          <p class="hero-desc mt-4 fade-in-up delay-3">{{ tagline }}</p>

          <!-- CTA Buttons -->
          <div class="hero-cta mt-5 d-flex gap-3 flex-wrap fade-in-up delay-4">
            <a href="#certificates" class="btn btn-primary-custom">
              View My Work <i class="bi bi-arrow-right ms-1"></i>
            </a>
            <a href="#about" class="btn btn-ghost-custom">
              About Me
            </a>
          </div>

          <!-- Social Media Links -->
          <div class="hero-socials mt-5 d-flex gap-3 fade-in-up delay-5">
            <a
              v-for="social in socials"
              :key="social.icon"
              :href="social.url"
              class="social-link"
              target="_blank"
              :title="social.label"
            >
              <i :class="'bi bi-' + social.icon"></i>
            </a>
          </div>

        </div>

        <!-- ── Right: Profile Image ── -->
        <div class="col-lg-5 hero-img-col mt-5 mt-lg-0 text-center">
          <div class="hero-card-wrap fade-in-up delay-2">

            <!-- Circular profile photo with glowing ring -->
            <div class="hero-img-ring">
              <img
                :src="profileImage"
                :alt="'Photo of ' + name"
                class="hero-profile-img"
              />
            </div>

            <!-- Floating stat badges -->
            <div class="float-badge badge-exp">
              <i class="bi bi-star-fill me-2"></i>{{ yearsExp }}+ Yrs Exp
            </div>
            <div class="float-badge badge-proj">
              <i class="bi bi-folder2-open me-2"></i>{{ projectCount }} Projects
            </div>

          </div>
        </div>

      </div>
    </div>

    <!-- Scroll down indicator -->
    <div class="scroll-indicator">
      <span>Scroll Down</span>
      <div class="scroll-line"></div>
    </div>

  </section>
</template>

<script>

import profileImage from '../assets/foto.png'

export default {
  name: 'HelloWorld',
  data() {
    return {
      // Personal introduction data
      name:        'Iyastama',
      role:        'Frontend Developer',
      tagline:     'I craft beautiful and performant web experiences using modern technologies like Vue JS, React, and cutting-edge CSS. Passionate about clean code and creative interfaces.',
      statusTag:   'Unemployed',

      // foto lokal dari src/assets/foto.png
      profileImage,

      // Stats shown as floating badges
      yearsExp:      3,
      projectCount: 20,

      // Social media links
      socials: [
        { icon: 'github',    label: 'GitHub',    url: 'https://github.com/' },
        { icon: 'linkedin',  label: 'LinkedIn',  url: 'https://linkedin.com/' },
        { icon: 'instagram', label: 'Instagram', url: 'https://instagram.com/' },
        { icon: 'envelope',  label: 'Email',     url: 'mailto:pebe@example.com' },
      ],
    }
  },
}
</script>
