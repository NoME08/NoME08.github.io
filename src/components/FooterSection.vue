<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="social-links">
        <a
          v-for="link in socialLinks"
          :key="link.name"
          :href="link.url"
          target="_blank"
          rel="noopener noreferrer"
          class="social-link"
        >
          <i :class="link.icon"></i>
          <span>{{ link.name }}</span>
        </a>
      </div>

      <div class="contact-info">
        <p>Wechat: FUatto08 | Email: zilong.wang08@outlook.com</p>
      </div>

      <div class="copyright">
        <p>© 2026 Zilong Wang. Built with Vue & minimalism.</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
const socialLinks = [
  {
    name: 'GitHub',
    icon: 'fab fa-github',
    url: 'https://github.com/NoME08'
  },
  {
    name: 'Instagram',
    icon: 'fab fa-instagram',
    url: 'https://www.instagram.com/belegenddd/'
  }
]
</script>

<style scoped>
.footer {
  border-top: 1px solid var(--color-border);
  padding: 48px 32px;
  margin-top: var(--spacing-section);
}

.footer-content {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 32px;
  margin-bottom: 24px;
}

.social-link {
  display: flex;
  align-items: center;
  gap: 8px;
  color: var(--color-text-secondary);
  text-decoration: none;
  font-size: 14px;
  transition: color 0.2s ease;
}

.social-link:hover {
  color: var(--color-accent);
}

.contact-info {
  font-size: 14px;
  color: var(--color-text-secondary);
  margin-bottom: 16px;
}

.copyright {
  font-size: 14px;
  color: var(--color-text-secondary);
}
</style>