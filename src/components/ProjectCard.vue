<template>
  <div class="project-card">
    <h3 class="project-title">{{ title }}</h3>
    <p class="project-description">{{ description }}</p>

    <div class="project-tech">
      <span
        v-for="(tech, index) in tech"
        :key="index"
        class="tech-tag"
      >
        {{ tech }}
      </span>
    </div>

    <a
      :href="github"
      target="_blank"
      rel="noopener noreferrer"
      class="project-link"
    >
      <i class="fab fa-github"></i>
      View on GitHub
    </a>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  tech: {
    type: Array,
    default: () => []
  },
  github: {
    type: String,
    default: '#'
  }
})
</script>

<style scoped>
.project-card {
  background-color: var(--color-bg-secondary);
  border-radius: var(--border-radius-card);
  padding: var(--spacing-card);
  box-shadow: var(--shadow-card);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.project-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 30px rgba(0,0,0,0.05), 0 4px 10px rgba(0,0,0,0.08);
}

.project-title {
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 12px;
  color: var(--color-text-primary);
}

.project-description {
  font-size: 16px;
  line-height: 1.5;
  color: var(--color-text-secondary);
  margin-bottom: 20px;
  flex-grow: 1;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 24px;
}

.tech-tag {
  background-color: rgba(0, 102, 204, 0.1);
  color: var(--color-accent);
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 14px;
  font-weight: 500;
}

.project-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: var(--color-accent);
  text-decoration: none;
  font-size: 14px;
  font-weight: 500;
  transition: color 0.2s ease;
}

.project-link:hover {
  color: var(--color-text-primary);
}
</style>