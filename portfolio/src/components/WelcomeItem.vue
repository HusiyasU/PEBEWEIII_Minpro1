<template>
  <!-- ==========================================
       CERTIFICATES SECTION
       Bootstrap 5: container, row, col-sm-6,
       col-lg-4, card layout, btn, badge
       Vue: v-for, v-if, :style, :class, @click,
       computed (filteredCerts)
  ========================================== -->
  <section id="certificates" class="cert-section">
    <div class="container py-5">

      <!-- Section Header -->
      <div class="section-header mb-5">
        <span class="section-tag">Achievements</span>
        <h2 class="section-title">My <span class="highlight">Certificates</span></h2>
      </div>

      <!-- ── Category Filter Buttons ── -->
      <div class="cert-filter d-flex gap-2 flex-wrap justify-content-center mb-5">
        <button
          v-for="cat in certCategories"
          :key="cat"
          class="btn btn-filter"
          :class="{ active: activeCategory === cat }"
          @click="activeCategory = cat"
        >
          {{ cat }}
        </button>
      </div>

      <!-- ── Certificate Cards Grid ── -->
      <div class="row g-4">
        <div
          v-for="cert in filteredCerts"
          :key="cert.title"
          class="col-sm-6 col-lg-4"
        >
          <!-- Card with hover lift effect -->
          <div class="cert-card h-100">

            <!-- Colorful card top with icon -->
            <div
              class="cert-card-top"
              :style="{ background: cert.gradient }"
            >
              <i :class="'bi bi-' + cert.icon + ' cert-icon'"></i>
              <span class="cert-category-badge">{{ cert.category }}</span>
            </div>

            <!-- Card body: title, issuer, date, CTA -->
            <div class="cert-card-body d-flex flex-column">
              <h5 class="cert-title">{{ cert.title }}</h5>
              <p class="cert-issuer">
                <i class="bi bi-award me-1"></i>{{ cert.issuer }}
              </p>
              <p class="cert-date">
                <i class="bi bi-calendar3 me-1"></i>{{ cert.date }}
              </p>
              <a
                :href="cert.link"
                target="_blank"
                class="btn btn-cert-view mt-auto"
              >
                View Certificate <i class="bi bi-box-arrow-up-right ms-1"></i>
              </a>
            </div>

          </div>
        </div>
      </div>

      <!-- Empty state when filter has no results -->
      <div v-if="filteredCerts.length === 0" class="text-center py-5 no-cert">
        <i class="bi bi-emoji-frown fs-1 mb-3 d-block" style="color: var(--clr-muted);"></i>
        <p style="color: var(--clr-muted);">No certificates in this category yet.</p>
      </div>

    </div>
  </section>
</template>

<script>
export default {
  name: 'WelcomeItem',
  data() {
    return {
      // Currently active filter category
      activeCategory: 'All',

      // All certificate data
      certificates: [
        {
          title:    'Front-End Web Development Fundamentals',
          issuer:   'Dicoding Indonesia',
          date:     'Maret 2024',
          category: 'Web Dev',
          icon:     'code-slash',
          gradient: 'linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%)',
          link:     '#',
        },
        {
          title:    'Vue JS – The Complete Guide',
          issuer:   'Udemy',
          date:     'Januari 2024',
          category: 'Vue JS',
          icon:     'layers',
          gradient: 'linear-gradient(135deg, #0d2137 0%, #1a4a3a 100%)',
          link:     '#',
        },
        {
          title:    'Bootstrap 5 Mastery Course',
          issuer:   'Coursera',
          date:     'November 2023',
          category: 'CSS',
          icon:     'grid-1x2-fill',
          gradient: 'linear-gradient(135deg, #2d0a6b 0%, #5a189a 100%)',
          link:     '#',
        },
        {
          title:    'JavaScript Algorithms & Data Structures',
          issuer:   'freeCodeCamp',
          date:     'September 2023',
          category: 'Web Dev',
          icon:     'braces',
          gradient: 'linear-gradient(135deg, #1a2600 0%, #2d4a00 100%)',
          link:     '#',
        },
        {
          title:    'UI/UX Design Essentials with Figma',
          issuer:   'Dicoding Indonesia',
          date:     'Juli 2023',
          category: 'Design',
          icon:     'palette2',
          gradient: 'linear-gradient(135deg, #3d0030 0%, #6d003a 100%)',
          link:     '#',
        },
        {
          title:    'Responsive Web Design Certification',
          issuer:   'freeCodeCamp',
          date:     'Mei 2023',
          category: 'CSS',
          icon:     'phone',
          gradient: 'linear-gradient(135deg, #001a3d 0%, #003080 100%)',
          link:     '#',
        },
        {
          title:    'Git & GitHub for Beginners',
          issuer:   'Udemy',
          date:     'April 2023',
          category: 'DevOps',
          icon:     'git',
          gradient: 'linear-gradient(135deg, #1a0a00 0%, #3d1c00 100%)',
          link:     '#',
        },
        {
          title:    'Google Analytics Certification',
          issuer:   'Google',
          date:     'Februari 2023',
          category: 'Design',
          icon:     'bar-chart-line',
          gradient: 'linear-gradient(135deg, #001a1a 0%, #003d3d 100%)',
          link:     '#',
        },
        {
          title:    'Node.js & Express Backend Basics',
          issuer:   'Coursera',
          date:     'Desember 2022',
          category: 'DevOps',
          icon:     'server',
          gradient: 'linear-gradient(135deg, #0a1a00 0%, #1a3300 100%)',
          link:     '#',
        },
      ],
    }
  },

  computed: {
    // Unique category list derived from certificates data
    certCategories() {
      const cats = ['All', ...new Set(this.certificates.map(c => c.category))]
      return cats
    },

    // Filtered list based on active category tab
    filteredCerts() {
      if (this.activeCategory === 'All') return this.certificates
      return this.certificates.filter(c => c.category === this.activeCategory)
    },
  },
}
</script>
