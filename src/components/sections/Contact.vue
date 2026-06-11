<script setup lang="ts">
import { onMounted } from 'vue'

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible')
        }
      })
    },
    { threshold: 0.1 }
  )

  document.querySelectorAll('.fade-in').forEach((el) => {
    observer.observe(el)
  })
})
</script>

<template>
  <section class="contact-section">
    <div class="container">
      <div class="contact-content fade-in">
        <p class="section-label">Connect</p>
        <h2 class="section-title">联系我</h2>

        <div class="contact-text">
          <p>感谢你的到来。</p>
          <p>如果这里的内容对你有所启发，欢迎交流。</p>
        </div>

        <a href="mailto:hcshi@outlook.com" class="email">
          📮 hcshi@outlook.com
        </a>

        <div class="social-links">
          <a
            href="https://github.com/clarance2018"
            target="_blank"
            rel="noopener noreferrer"
            class="social-link"
          >
            Github
          </a>
          <span class="divider">·</span>
          <a
            href="https://6mal.com/atom.xml"
            target="_blank"
            rel="noopener noreferrer"
            class="social-link"
          >
            RSS
          </a>
          <span class="divider">·</span>
          <span class="social-link">微信公众号</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-section {
  padding: 120px 0;
}

.container {
  width: min(1180px, 92%);
  margin: auto;
}

.contact-content {
  text-align: center;
  max-width: 600px;
  margin: 0 auto;
}

.section-label {
  font-size: 13px;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--secondary);
  margin-bottom: 16px;
}

.section-title {
  font-size: 52px;
  font-weight: 700;
  letter-spacing: -2px;
  margin-bottom: 48px;
  color: var(--text);
}

.contact-text {
  display: flex;
  flex-direction: column;
  gap: 12px;
  margin-bottom: 48px;
}

.contact-text p {
  font-size: 22px;
  line-height: 2;
  color: var(--secondary);
}

.email {
  display: inline-block;
  font-size: 28px;
  color: var(--text);
  text-decoration: none;
  margin-bottom: 48px;
  transition: all 0.2s ease;
}

.email:hover {
  color: #22c55e;
}

.social-links {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
}

.social-link {
  font-size: 16px;
  color: var(--secondary);
  text-decoration: none;
  transition: color 0.2s ease;
  cursor: pointer;
}

.social-link:hover {
  color: var(--text);
}

.divider {
  color: var(--border);
  font-size: 20px;
}

/* 滚动淡入动画 */
.fade-in {
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.8s ease-out, transform 0.8s ease-out;
}

.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}

@media (max-width: 768px) {
  .section-title {
    font-size: 36px;
  }

  .contact-text p {
    font-size: 18px;
  }

  .email {
    font-size: 22px;
  }
}
</style>
