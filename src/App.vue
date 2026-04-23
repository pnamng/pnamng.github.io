<script setup>
const skills = [
  { icon: '⚡', title: 'Frontend', desc: 'Vue 3, React, TypeScript, Tailwind CSS — building fast, accessible UIs.' },
  { icon: '🛠', title: 'Backend', desc: 'Node.js, Python, REST & GraphQL APIs, PostgreSQL, Redis.' },
  { icon: '☁️', title: 'Cloud & DevOps', desc: 'AWS, Docker, CI/CD pipelines, GitHub Actions, Terraform.' },
  { icon: '🎨', title: 'Design Systems', desc: 'Component libraries, design tokens, Figma to code workflows.' },
  { icon: '📱', title: 'Mobile', desc: 'React Native cross-platform apps with native-feel performance.' },
  { icon: '🔒', title: 'Security', desc: 'OWASP best practices, auth flows, dependency auditing.' },
]

const projects = [
  {
    emoji: '🚀',
    bg: 'linear-gradient(135deg,#1a1a2e,#16213e)',
    title: 'Launchpad',
    desc: 'A SaaS boilerplate with auth, billing, and a feature-flag system built on Next.js + Stripe.',
    tags: ['Next.js', 'TypeScript', 'Stripe'],
    demo: '#',
    repo: '#',
  },
  {
    emoji: '🤖',
    bg: 'linear-gradient(135deg,#0d1117,#161b22)',
    title: 'AI Chat CLI',
    desc: 'Terminal-based chat client for Claude and GPT models with streaming, history, and plugin support.',
    tags: ['Python', 'Rich', 'Claude API'],
    demo: '#',
    repo: '#',
  },
  {
    emoji: '📊',
    bg: 'linear-gradient(135deg,#0f2027,#203a43)',
    title: 'Dataflow',
    desc: 'Real-time analytics dashboard with WebSocket feeds, D3 charts, and role-based access control.',
    tags: ['Vue 3', 'D3.js', 'WebSockets'],
    demo: '#',
    repo: '#',
  },
]
</script>

<template>
  <div id="app">
    <!-- Nav -->
    <nav>
      <span class="nav-logo">pnamng.dev</span>
      <ul class="nav-links">
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>

    <!-- Hero -->
    <section class="hero">
      <div class="hero-badge">
        <span class="dot"></span>
        Open to opportunities
      </div>
      <h1>Hi, I'm <span>Nam</span> —<br>I build things for the web.</h1>
      <p>
        Full-stack developer focused on crafting clean, performant products that users love.
        6+ years turning ideas into production software.
      </p>
      <div class="hero-cta">
        <a href="#projects" class="btn btn-primary">View my work ↓</a>
        <a href="#contact" class="btn btn-ghost">Get in touch</a>
      </div>
    </section>

    <hr class="divider" />

    <!-- Skills -->
    <section id="skills">
      <p class="section-label">What I do</p>
      <h2 class="section-title">Skills & Expertise</h2>
      <p class="section-sub">A toolkit refined across startups, agencies, and open source.</p>
      <div class="skills-grid">
        <div v-for="s in skills" :key="s.title" class="skill-card">
          <div class="skill-icon">{{ s.icon }}</div>
          <h3>{{ s.title }}</h3>
          <p>{{ s.desc }}</p>
        </div>
      </div>
    </section>

    <hr class="divider" />

    <!-- Projects -->
    <section id="projects">
      <p class="section-label">Selected work</p>
      <h2 class="section-title">Projects</h2>
      <p class="section-sub">A few things I've built recently. More on GitHub.</p>
      <div class="projects-grid">
        <div v-for="p in projects" :key="p.title" class="project-card">
          <div class="project-thumb" :style="{ background: p.bg }">{{ p.emoji }}</div>
          <div class="project-body">
            <div class="project-tags">
              <span v-for="t in p.tags" :key="t" class="tag">{{ t }}</span>
            </div>
            <h3>{{ p.title }}</h3>
            <p>{{ p.desc }}</p>
            <div class="project-links">
              <a :href="p.demo">↗ Live demo</a>
              <a :href="p.repo">⌥ Source</a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <hr class="divider" />

    <!-- Contact -->
    <section id="contact">
      <div class="contact-card">
        <h2>Let's work together</h2>
        <p>I'm always happy to chat about interesting projects, freelance work, or full-time roles.</p>
        <a href="mailto:pnam2311@gmail.com" class="btn btn-primary">pnam2311@gmail.com</a>
        <div class="social-links">
          <a href="https://github.com/pnamng" class="social-link" target="_blank" rel="noopener">
            ⌥ GitHub
          </a>
          <a href="https://linkedin.com" class="social-link" target="_blank" rel="noopener">
            in LinkedIn
          </a>
          <a href="https://twitter.com" class="social-link" target="_blank" rel="noopener">
            𝕏 Twitter
          </a>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer>
      Built with Vue 3 + Vite · © {{ new Date().getFullYear() }} Nam Pham
    </footer>
  </div>
</template>
