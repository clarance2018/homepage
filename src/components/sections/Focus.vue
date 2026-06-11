<script setup lang="ts">
const focuses = [
  { title: 'AI Agent', desc: '关注智能体架构、设计模式以及工程实践。' },
  { title: 'Memory 与 MCP', desc: '探索长期记忆系统与上下文协议。' },
  { title: '企业 AI', desc: '研究 AI 在真实业务中的落地方式。' },
  { title: '数据智能', desc: '让数据分析拥有更强的自主能力。' },
  { title: 'Context Engineering', desc: '上下文管理决定 AI 的能力边界。' },
]
</script>

<template>
  <section>
    <div class="container">
      <h2 class="section-title">最近关注</h2>

      <div class="grid">
        <div
          v-for="(item, index) in focuses"
          :key="item.title"
          class="card"
          :class="{ big: index === focuses.length - 1 }"
        >
          <h3>{{ item.title }}</h3>
          <p>{{ item.desc }}</p>
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

.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 28px;
}

.card {
  background: var(--card);
  backdrop-filter: blur(40px);
  border: 1px solid var(--border);
  border-radius: 36px;
  padding: 42px;
  transition: 0.4s;
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 30px 60px rgba(0, 0, 0, 0.08);
}

[data-theme="dark"] .card:hover {
  box-shadow: 0 30px 60px rgba(0, 0, 0, 0.4);
}

.card h3 {
  font-size: 30px;
  margin-bottom: 20px;
  color: var(--text);
}

.card p {
  line-height: 2;
  color: var(--secondary);
}

.big {
  grid-column: span 2;
}

@media (max-width: 768px) {
  .section-title {
    font-size: 36px;
  }

  .grid {
    grid-template-columns: 1fr;
  }

  .big {
    grid-column: auto;
  }

  .card h3 {
    font-size: 24px;
  }
}
</style>
