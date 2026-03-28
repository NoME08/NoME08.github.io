<template>
  <div id="app">
    <HeroSection />
    <AboutSection />
    <InterestsSection />
    <div class="section-divider"></div>
    <ProjectsSection />
    <FooterSection />
  </div>
</template>

<script setup>
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import InterestsSection from './components/InterestsSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<style>
/* 全局CSS变量和重置 */
:root {
  --color-bg-primary: #FFFFFF;
  --color-bg-secondary: #F5F5F7;
  --color-text-primary: #1D1D1F;
  --color-text-secondary: #86868B;
  --color-accent: #0066CC;
  --color-border: #E8E8ED;
  --border-radius-card: 18px;
  --border-radius-button: 40px;
  --shadow-card: 0 8px 20px rgba(0,0,0,0.02), 0 2px 6px rgba(0,0,0,0.05);
  --spacing-section: 120px;
  --spacing-card: 32px;
  --font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", "SF Pro Display", "Helvetica Neue", Helvetica, Arial, sans-serif;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: var(--font-family);
  background-color: var(--color-bg-primary);
  color: var(--color-text-primary);
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#app {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* 响应式间距 */
@media (max-width: 768px) {
  :root {
    --spacing-section: 80px;
  }
}

.section-divider {
  height: 1px;
  background-color: var(--color-border);
  margin: 60px auto;
  max-width: 200px;
}
</style>