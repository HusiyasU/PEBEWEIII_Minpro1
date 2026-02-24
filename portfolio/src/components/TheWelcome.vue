<template>
  <!-- ==========================================
       ABOUT ME SECTION
       Bootstrap 5: container, row, col-lg-*,
       progress, progress-bar, d-flex, gap-*
       Vue: v-for, interpolation {{ }}, :style
  ========================================== -->
  <section id="about" class="about-section">
    <div class="container py-5">

      <!-- Section Header -->
      <div class="section-header mb-5">
        <span class="section-tag">Get to know me</span>
        <h2 class="section-title">About <span class="highlight">Me</span></h2>
      </div>

      <div class="row g-5 align-items-start">

        <!-- ── Left Column: Image + Personal Info ── -->
        <div class="col-lg-5">

          <!-- Profile image with decorative offset border -->
          <div class="about-img-wrapper mb-4">
            <img
              :src="aboutImage"
              :alt="'Profile image of ' + name"
              class="about-img"
            />
            <div class="about-img-decoration"></div>
          </div>

          <!-- Personal info grid (Bootstrap grid inside) -->
          <div class="info-grid">
            <div
              v-for="info in personalInfo"
              :key="info.label"
              class="info-item"
            >
              <span class="info-label">{{ info.label }}</span>
              <span class="info-value">{{ info.value }}</span>
            </div>
          </div>

        </div>

        <!-- ── Right Column: Bio + Skills + Experience ── -->
        <div class="col-lg-7">

          <!-- Bio description -->
          <p class="about-desc">{{ aboutDesc }}</p>

          <!-- ──── SKILLS with Bootstrap Progress Bars ──── -->
          <h4 class="skills-heading mt-5 mb-4">Technical Skills</h4>
          <div class="skills-list">
            <div
              v-for="skill in skills"
              :key="skill.name"
              class="skill-item mb-3"
            >
              <div class="d-flex justify-content-between mb-1">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-pct">{{ skill.pct }}%</span>
              </div>
              <!-- Bootstrap 5 progress bar with dynamic width & color -->
              <div class="progress skill-progress" role="progressbar" :aria-valuenow="skill.pct" aria-valuemin="0" aria-valuemax="100">
                <div
                  class="progress-bar"
                  :style="{ width: skill.pct + '%', background: skill.color }"
                ></div>
              </div>
            </div>
          </div>

          <!-- ──── EXPERIENCE Timeline ──── -->
          <h4 class="skills-heading mt-5 mb-4">Experience</h4>
          <div class="experience-timeline">
            <div
              v-for="exp in experience"
              :key="exp.title"
              class="exp-item"
            >
              <div class="exp-dot"></div>
              <div class="exp-body">
                <span class="exp-period">{{ exp.period }}</span>
                <h5 class="exp-title">{{ exp.title }}</h5>
                <p class="exp-company">
                  <i class="bi bi-building me-1"></i>{{ exp.company }}
                </p>
                <p class="exp-desc">{{ exp.desc }}</p>
              </div>
            </div>
          </div>

        </div>

      </div>
    </div>
  </section>
</template>

<script>

import aboutImage from '../assets/foto1.jfif'

export default {
  name: 'TheWelcome',
  data() {
    return {
      name:       'Husaini Iyastama',

      // foto lokal dari src/assets/foto.jpg
      aboutImage,

      // Short biography paragraph
      aboutDesc: 'I am a passionate Frontend Developer with 3+ years of experience building modern, responsive, and user-friendly web applications. I specialize in Vue JS, React, and enjoy bridging creative design with clean, maintainable code. When I\'m not coding, I\'m exploring UI design trends and contributing to open-source projects.',

      // Quick facts table
      personalInfo: [
        { label: 'Name',       value: 'Husaini Iyastama' },
        { label: 'Location',   value: 'Kalimantan, ID' },
        { label: 'Degree',     value: 'S1 Jurusan Pangan' },
        { label: 'Email',      value: 'husaini@iyas.com' },
        { label: 'Freelance',  value: 'Available' },
        { label: 'Languages',  value: 'ID, EN' },
      ],

      // Skills with percentage and gradient color
      skills: [
        { name: 'HTML & CSS',    pct: 92, color: 'linear-gradient(90deg, #ff6b6b, #feca57)' },
        { name: 'Vue JS',        pct: 85, color: 'linear-gradient(90deg, #4fffb0, #00b8ff)' },
        { name: 'JavaScript',    pct: 80, color: 'linear-gradient(90deg, #f7df1e, #ff9f43)' },
        { name: 'Bootstrap 5',   pct: 88, color: 'linear-gradient(90deg, #7c3aed, #a78bfa)' },
        { name: 'React',         pct: 72, color: 'linear-gradient(90deg, #00b8ff, #0984e3)' },
        { name: 'Figma / UI/UX', pct: 70, color: 'linear-gradient(90deg, #fd79a8, #e84393)' },
      ],

      // Work experience entries
      experience: [
        {
          period:  '2023 – Present',
          title:   'Frontend Developer',
          company: 'Tech Startup — Balikpapan',
          desc:    'Building responsive web apps with Vue JS and Nuxt. Leading UI architecture decisions and conducting code reviews.',
        },
        {
          period:  '2022 – 2023',
          title:   'Junior Web Developer',
          company: 'Digital Agency — Samarinda',
          desc:    'Developed landing pages and e-commerce templates using Bootstrap 5. Collaborated closely with UI designers to implement pixel-perfect interfaces.',
        },
        {
          period:  '2021 – 2022',
          title:   'Internship — Frontend Dev',
          company: 'PT. Kreasi Digital',
          desc:    'Assisted in building internal dashboards using HTML, CSS, and vanilla JavaScript. Gained hands-on experience with Git workflow.',
        },
      ],
    }
  },
}
</script>
