<template>
  <section class="about">
    <div class="about-content">
      <p class="about-text">
        I'm a second-year computer science student at the University of Melbourne.
        I believe in building things that matter — whether it's clean code, a stronger
        deadlift, or a connection with the car I'm driving. Off the screen, you'll
        find me on the court or exploring Melbourne's automotive scene.
      </p>
    </div>
  </section>
</template>

<script setup>
// No script needed for responsive spacing - handled by CSS
</script>

<style scoped>
.about {
  margin-bottom: var(--spacing-section);
  display: flex;
  justify-content: center;
}

.about-content {
  max-width: 700px;
  text-align: center;
}

.about-text {
  font-size: 20px;
  line-height: 1.6;
  color: var(--color-text-primary);
}

/* 响应式 */
@media (max-width: 768px) {
  .about-text {
    font-size: 18px;
  }
}
</style>