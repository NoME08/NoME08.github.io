<template>
  <div class="interest-card">
    <div class="card-icon">
      <i :class="`fa-solid fa-${icon}`"></i>
    </div>
    <h3 class="card-title">{{ title }}</h3>
    <p class="card-description">{{ description }}</p>

    <div class="card-highlights">
      <span
        v-for="(highlight, index) in highlights"
        :key="index"
        class="highlight"
      >
        {{ highlight }}
      </span>
    </div>

    <p class="card-details">{{ details }}</p>

    <button class="card-button" v-if="showButton">
      Read more
    </button>
  </div>
</template>

<script setup>
defineProps({
  icon: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  highlights: {
    type: Array,
    default: () => []
  },
  details: {
    type: String,
    default: ''
  },
  showButton: {
    type: Boolean,
    default: false
  }
})
</script>

<style scoped>
.interest-card {
  background-color: var(--color-bg-secondary);
  border-radius: var(--border-radius-card);
  padding: var(--spacing-card);
  box-shadow: var(--shadow-card);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.interest-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 30px rgba(0,0,0,0.05), 0 4px 10px rgba(0,0,0,0.08);
}

.card-icon {
  font-size: 32px;
  color: var(--color-accent);
  margin-bottom: 20px;
}

.card-title {
  font-size: 24px;
  font-weight: 600;
  margin-bottom: 12px;
  color: var(--color-text-primary);
}

.card-description {
  font-size: 16px;
  line-height: 1.5;
  color: var(--color-text-secondary);
  margin-bottom: 20px;
}

.card-highlights {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 16px;
}

.highlight {
  background-color: rgba(0, 102, 204, 0.1);
  color: var(--color-accent);
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 14px;
  font-weight: 500;
}

.card-details {
  font-size: 14px;
  color: var(--color-text-secondary);
  margin-bottom: 24px;
  font-style: italic;
}

.card-button {
  background-color: transparent;
  color: var(--color-accent);
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius-button);
  padding: 8px 24px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s ease;
  margin-top: auto;
}

.card-button:hover {
  background-color: var(--color-accent);
  color: white;
  border-color: var(--color-accent);
}
</style>