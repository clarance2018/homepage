<script setup lang="ts">
const steps = [
  { icon: '📚', title: '阅读' },
  { icon: '🧠', title: '理解' },
  { icon: '💭', title: '思考' },
  { icon: '✍️', title: '记录' },
  { icon: '🌱', title: '沉淀' },
]
</script>

<template>
  <section>
    <div class="container">
      <h2 class="section-title">我的数字花园</h2>

      <div class="timeline">
        <div v-for="step in steps" :key="step.title" class="step">
          <div class="circle">{{ step.icon }}</div>
          <h4>{{ step.title }}</h4>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.container {
  width: min(1180px, 92%);
  margin: auto;
}

section {
  padding: 120px 0;
}

.section-title {
  font-size: 52px;
  margin-bottom: 60px;
  letter-spacing: -2px;
  color: var(--text);
}

.timeline {
  display: flex;
  justify-content: space-between;
  position: relative;
}

.timeline::before {
  content: '';
  position: absolute;
  top: 40px;
  left: 80px;
  right: 80px;
  height: 2px;
  background: linear-gradient(90deg, #ddd, var(--green));
}

.step {
  position: relative;
  text-align: center;
  width: 160px;
}

.circle {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  margin: auto;
  background: var(--card);
  backdrop-filter: blur(30px);
  border: 1px solid var(--border);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 30px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.06);
  transition: all 0.3s ease;
}

[data-theme="dark"] .circle {
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}

.circle:hover {
  transform: scale(1.1);
  border-color: var(--green);
}

.step h4 {
  margin-top: 24px;
  font-size: 22px;
  font-weight: 600;
  color: var(--text);
}

@media (max-width: 768px) {
  .section-title {
    font-size: 36px;
  }

  .timeline {
    flex-direction: column;
    gap: 50px;
  }

  .timeline::before {
    display: none;
  }

  .step {
    width: auto;
  }
}
</style>
