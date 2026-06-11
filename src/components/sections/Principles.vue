<script setup lang="ts">
import { onMounted } from 'vue'

const principles = [
  {
    quote: '真正重要的事情，需要时间积累。',
    title: 'Long-term Thinking',
    height: 'tall',
  },
  {
    quote: '回到问题本身，而不是停留在经验。',
    title: 'First Principles',
    height: 'short',
  },
  {
    quote: 'AI 的价值，在于放大人的能力。',
    title: 'Human × AI',
    height: 'short',
  },
  {
    quote: '保持好奇心，持续进化。',
    title: 'Continuous Learning',
    height: 'tall',
  },
]

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
  <section class="principles-section">
    <div class="container">
      <p class="section-label">Principles</p>
      <h2 class="section-title">原则</h2>

      <div class="principles-grid">
        <div
          v-for="(item, index) in principles"
          :key="index"
          class="principle-card fade-in"
          :class="item.height"
        >
          <p class="principle-quote">{{ item.quote }}</p>
          <p class="principle-title">{{ item.title }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.principles-section {
  padding: 120px 0;
}

.container {
  width: min(1180px, 92%);
  margin: auto;
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
  margin-bottom: 60px;
  color: var(--text);
}

.principles-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}

.principle-card {
  background: var(--card);
  backdrop-filter: blur(40px);
  border: 1px solid var(--border);
  border-radius: 40px;
  padding: 48px;
  transition: all 0.4s ease;
}

.principle-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 30px 60px rgba(0, 0, 0, 0.08);
}

[data-theme="dark"] .principle-card:hover {
  box-shadow: 0 30px 60px rgba(0, 0, 0, 0.4);
}

/* 不同高度形成杂志风 */
.tall {
  padding: 60px 48px;
}

.short {
  padding: 40px 48px;
}

.principle-quote {
  font-size: 32px;
  font-weight: 500;
  line-height: 1.5;
  color: var(--text);
  margin-bottom: 24px;
  letter-spacing: -0.01em;
}

.principle-title {
  font-size: 14px;
  color: var(--secondary);
  letter-spacing: 0.05em;
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

/* 交错动画延迟 */
.fade-in:nth-child(1) { transition-delay: 0s; }
.fade-in:nth-child(2) { transition-delay: 0.1s; }
.fade-in:nth-child(3) { transition-delay: 0.2s; }
.fade-in:nth-child(4) { transition-delay: 0.3s; }

@media (max-width: 768px) {
  .section-title {
    font-size: 36px;
  }

  .principles-grid {
    grid-template-columns: 1fr;
  }

  .principle-quote {
    font-size: 24px;
  }
}
</style>
