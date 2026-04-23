<script setup>
import { ref, onMounted } from 'vue'

const isDark = ref(true)

onMounted(() => {
  isDark.value = document.documentElement.getAttribute('data-theme') !== 'light'
})

function toggleTheme() {
  isDark.value = !isDark.value
  const theme = isDark.value ? 'dark' : 'light'
  document.documentElement.setAttribute('data-theme', theme)
  localStorage.setItem('theme', theme)
}

const skills = [
  { title: 'Frontend', desc: 'Vue 3, React, TypeScript, Tailwind CSS.' },
  { title: 'Backend', desc: 'Node.js, Python, REST & GraphQL APIs, PostgreSQL, Redis.' },
  { title: 'Cloud & DevOps', desc: 'AWS, Docker, CI/CD, GitHub Actions, Terraform.' },
  { title: 'Design Systems', desc: 'Component libraries, design tokens, Figma to code.' },
  { title: 'Mobile', desc: 'React Native cross-platform apps.' },
  { title: 'Security', desc: 'OWASP best practices, auth flows, dependency auditing.' },
]
</script>

<template>
  <div id="app">
    <nav>
      <span class="nav-logo">pnamng.dev</span>
      <div class="nav-right">
        <ul class="nav-links">
          <li><a href="#skills">Skills</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
        <button class="theme-btn" @click="toggleTheme" :aria-label="isDark ? 'Light mode' : 'Dark mode'">
          <svg v-if="isDark" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="5"/><line x1="12" y1="1" x2="12" y2="3"/><line x1="12" y1="21" x2="12" y2="23"/><line x1="4.22" y1="4.22" x2="5.64" y2="5.64"/><line x1="18.36" y1="18.36" x2="19.78" y2="19.78"/><line x1="1" y1="12" x2="3" y2="12"/><line x1="21" y1="12" x2="23" y2="12"/><line x1="4.22" y1="19.78" x2="5.64" y2="18.36"/><line x1="18.36" y1="5.64" x2="19.78" y2="4.22"/></svg>
          <svg v-else width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/></svg>
        </button>
      </div>
    </nav>

    <section class="hero">
      <div class="badge">
        <span class="dot"></span>
        Open to opportunities
      </div>
      <h1>Building things<br>for the web.</h1>
      <p>Full-stack developer focused on clean, performant products.<br>6+ years turning ideas into production software.</p>
      <div class="hero-actions">
        <a href="#contact" class="btn btn-primary">Get in touch</a>
        <a href="#skills" class="btn btn-ghost">See what I do</a>
      </div>
    </section>

    <hr class="divider" />

    <section id="skills">
      <p class="label">Expertise</p>
      <h2 class="section-title">Skills</h2>
      <div class="skills-grid">
        <div v-for="s in skills" :key="s.title" class="skill-card">
          <h3>{{ s.title }}</h3>
          <p>{{ s.desc }}</p>
        </div>
      </div>
    </section>

    <hr class="divider" />

    <section id="contact">
      <p class="label">Get in touch</p>
      <h2 class="section-title">Contact</h2>
      <p class="section-sub">Happy to chat about projects, freelance, or full-time roles.</p>
      <div class="contact-list">
        <a href="mailto:pnam2311@gmail.com" class="contact-row">
          <span class="contact-type">Email</span>
          <span class="contact-val">pnam2311@gmail.com <span class="arrow">↗</span></span>
        </a>
        <a href="https://github.com/pnamng" class="contact-row" target="_blank" rel="noopener">
          <span class="contact-type">GitHub</span>
          <span class="contact-val">pnamng <span class="arrow">↗</span></span>
        </a>
        <a href="https://linkedin.com" class="contact-row" target="_blank" rel="noopener">
          <span class="contact-type">LinkedIn</span>
          <span class="contact-val">LinkedIn <span class="arrow">↗</span></span>
        </a>
      </div>
    </section>

    <footer>
      Built with Vue 3 + Vite · {{ new Date().getFullYear() }}
    </footer>
  </div>
</template>
