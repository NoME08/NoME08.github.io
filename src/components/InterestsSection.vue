<template>
  <section class="interests">
    <h2 class="section-title">Interests</h2>
    <div class="cards-grid">
      <InterestCard
        v-for="interest in interests"
        :key="interest.title"
        :icon="interest.icon"
        :title="interest.title"
        :description="interest.description"
        :highlights="interest.highlights"
        :details="interest.details"
      />
    </div>
  </section>
</template>

<script setup>
import InterestCard from './InterestCard.vue'

const interests = [
  {
    icon: 'dumbbell',
    title: 'Fitness',
    description: 'Strength training 3/week | Tracking progressive overload',
    highlights: ['Squat 140kg', 'Bench 85kg', 'Deadlift 150kg'],
    details: 'Currently chasing 500kg in total'
  },
  {
    icon: 'car',
    title: 'Cars',
    description: 'JDM enthusiast & modern performance admirer',
    highlights: ['BRZ', 'WRX', 'G82 M3', 'CT5-V'],
    details: 'Love driving'
  },
  {
    icon: 'basketball',
    title: 'Basketball',
    description: 'Weekend pick-up games at Melbourne Uni Sports Centre.',
    highlights: ['Kobe Bryant'],
    details: 'Spot-up shooter, tries to defend'
  }
]
</script>

<style scoped>
.interests {
  margin-bottom: var(--spacing-section);
}

.section-title {
  font-size: 32px;
  font-weight: 600;
  text-align: center;
  margin-bottom: 48px;
  color: var(--color-text-primary);
}

.cards-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
}

/* 响应式 */
@media (max-width: 1024px) {
  .cards-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .cards-grid {
    grid-template-columns: 1fr;
  }
}
</style>