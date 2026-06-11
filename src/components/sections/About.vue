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
  <section class="about-section">
    <div class="container">
      <div class="about-content fade-in">
        <p class="section-label">About</p>
        <h2 class="section-title">关于我</h2>

        <div class="about-text">
          <p>欢迎来到我的数字花园。</p>
          <p>
            这里记录我对 AI 产品、知识管理、数据智能和未来工作的思考。
            相比追逐热点，我更相信长期主义、第一性原理以及人与 AI 的协作。
          </p>
          <p>这个网站既是公开知识库，也是持续演进的个人操作系统。</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  padding: 120px 0;
}

.container {
  width: min(1180px, 92%);
  margin: auto;
}

.about-content {
  max-width: 760px;
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

.about-text {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.about-text p {
  font-size: 24px;
  line-height: 2;
  color: var(--secondary);
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

  .about-text p {
    font-size: 18px;
  }
}
</style>
