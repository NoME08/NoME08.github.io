<template>
  <section class="hero">
    <!-- 可选：非常微妙的背景渐变 -->
    <div class="hero-background"></div>

    <div class="hero-content">
      <!-- 个人照片（圆形） -->
      <div class="hero-photo">
        <!--
          替换为你自己的照片：
          1. 将src属性改为你自己的照片URL或路径
          2. 建议使用正方形图片，尺寸至少400x400像素
          3. 推荐使用黑白或低饱和度风格以符合Apple美学
        -->
        <!--
          重要：HEIC格式在Web浏览器中支持有限，当前图片可能无法显示
        -->
        <img
          src="/IMG_3261.jpeg"
          alt="Zilong Wang - Computer Science Student"
          class="photo-image"
          loading="lazy"
          @error="handleImageError"
        />
      </div>

      <h1 class="hero-title">Zilong Wang</h1>
      <p class="hero-subtitle">Computer Science Student @ UniMelb</p>
      <p class="hero-tagline">No More Excuse.</p>

      <!-- 滚动提示 -->
      <div class="scroll-hint">
        <div class="scroll-dot"></div>
      </div>
    </div>
  </section>
</template>

<script setup>
// 图片加载错误处理
const handleImageError = (event) => {
  console.log('❌ HEIC图片加载失败，请转换为JPG格式')
  console.log('💡 转换方法：使用Mac预览应用打开 public/IMG_3261.heic，导出为JPEG格式')
  console.log('📁 保存为 public/IMG_3261.jpg 并修改 src 属性')

  // 替换为备用图片（符合Apple美学的黑白肖像）
  event.target.src = 'https://images.unsplash.com/photo-1564564321837-a57b7070ac4f?w=400&h=400&fit=crop&crop=face&auto=format'
  event.target.alt = 'Zilong Wang - Default portrait (请替换为你的照片)'

  // 显示转换提示（可选，更友好的用户体验）
  const photoElement = document.querySelector('.hero-photo')
  if (photoElement) {
    const tooltip = document.createElement('div')
    tooltip.className = 'photo-tooltip'
    tooltip.innerHTML = '💡 点击查看如何添加个人照片'
    tooltip.style.cssText = `
      position: absolute;
      bottom: -30px;
      left: 50%;
      transform: translateX(-50%);
      background: rgba(0,102,204,0.9);
      color: white;
      padding: 4px 8px;
      border-radius: 4px;
      font-size: 12px;
      white-space: nowrap;
      cursor: pointer;
      z-index: 10;
    `
    tooltip.onclick = () => {
      alert('请将 public/IMG_3261.heic 转换为 JPG 格式：\n\n1. 双击打开该文件\n2. 文件 → 导出...\n3. 格式选择 JPEG\n4. 保存为 public/IMG_3261.jpg\n5. 修改代码中 src="/IMG_3261.heic" 为 src="/IMG_3261.jpg"')
    }
    photoElement.style.position = 'relative'
    photoElement.appendChild(tooltip)
  }
}
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 0 20px;
  margin-bottom: var(--spacing-section);
  position: relative;
}

.hero-background {
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(245,245,247,0.2) 0%, rgba(255,255,255,0) 100%);
  z-index: -1;
}

.hero-content {
  max-width: 800px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.hero-photo {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  overflow: hidden;
  margin-bottom: 32px;
  border: 4px solid var(--color-bg-secondary);
  box-shadow: var(--shadow-card);
}

.photo-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.hero-title {
  font-size: 64px;
  font-weight: 700;
  line-height: 1.1;
  margin-bottom: 16px;
  letter-spacing: -0.02em;
}

.hero-subtitle {
  font-size: 24px;
  color: var(--color-text-secondary);
  margin-bottom: 24px;
  font-weight: 400;
}

.hero-tagline {
  font-size: 20px;
  color: var(--color-text-secondary);
  font-style: italic;
  margin-bottom: 48px;
}

.scroll-hint {
  display: flex;
  justify-content: center;
  margin-top: 48px;
}

.scroll-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background-color: var(--color-text-secondary);
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(10px);
  }
}

/* 响应式 */
@media (max-width: 768px) {
  .hero-photo {
    width: 120px;
    height: 120px;
    margin-bottom: 24px;
  }

  .hero-title {
    font-size: 48px;
  }

  .hero-subtitle {
    font-size: 20px;
  }

  .hero-tagline {
    font-size: 18px;
  }
}
</style>