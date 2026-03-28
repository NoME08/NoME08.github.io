<template>
  <section class="projects">
    <h2 class="section-title">Projects</h2>
    <div class="projects-grid">
      <ProjectCard
        v-for="project in projects"
        :key="project.title"
        :title="project.title"
        :description="project.description"
        :tech="project.tech"
        :github="project.github"
      />
    </div>
  </section>
</template>

<script setup>
import ProjectCard from './ProjectCard.vue'

const projects = [
  {
    title: 'This Site',
    description: 'Personal portfolio built with Vue 3 and Vite, featuring Apple-inspired minimalist design.',
    tech: ['Vue 3', 'Vite', 'CSS3'],
    github: 'https://github.com/NoME08/NoME08.github.io'
  },
  {
    title: 'Password manager',
    description: 'A simple client and server password management system.',
    tech: ['Python', 'MySQL'],
    github: 'https://github.com/NoME08/password_manager'
  },
  {
    title: 'Driving style analyzer',
    description: 'A Python-based tool for analyzing driving behavior using public datasets and simulated data.',
    tech: ['Python','Jupyter'],
    github: 'https://github.com/NoME08/Driving_style_analyzer'
  },
  {
    title: 'NoME08',
    description: 'Introduce myself',
    tech: ['Markdown'],
    github: 'https://github.com/NoME08'
  }
]
</script>

<style scoped>
.projects {
  margin-bottom: var(--spacing-section);
}

.section-title {
  font-size: 32px;
  font-weight: 600;
  text-align: center;
  margin-bottom: 48px;
  color: var(--color-text-primary);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 32px;
}

/* 响应式 */
@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>