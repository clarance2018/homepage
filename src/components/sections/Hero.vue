<script setup lang="ts">
const tags = ['AI Product', 'Agent', 'Data Intelligence', 'Knowledge Management']
</script>

<template>
  <section class="hero">
    <div class="container">
      <div class="hero-grid">
        <div>
          <h1>飞鲤</h1>
          <div class="subtitle">AI 时代的个人操作系统实践者</div>
          <div class="desc">
            研究 AI，构建系统，记录思考。<br />
            关注 AI 产品、知识管理、数据智能和未来工作。
          </div>
          <div class="tags">
            <span v-for="tag in tags" :key="tag" class="tag">{{ tag }}</span>
          </div>
        </div>

        <div class="network">
          <div class="node n1">AI Agent</div>
          <div class="node n2">Memory & MCP</div>
          <div class="node n3">Context Engineering</div>
          <div class="node n4">Enterprise AI</div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
}

.container {
  width: min(1180px, 92%);
  margin: auto;
}

.hero-grid {
  display: grid;
  grid-template-columns: 1.3fr 1fr;
  gap: 100px;
  align-items: center;
}

h1 {
  font-size: 96px;
  letter-spacing: -5px;
  margin-bottom: 24px;
  color: var(--text);
}

.subtitle {
  font-size: 32px;
  color: var(--text);
}

.desc {
  margin-top: 30px;
  color: var(--secondary);
  line-height: 2;
  font-size: 20px;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin-top: 40px;
}

.tag {
  padding: 12px 22px;
  border-radius: 999px;
  background: var(--card);
  backdrop-filter: blur(30px);
  border: 1px solid var(--border);
  font-size: 14px;
  color: var(--secondary);
  transition: all 0.2s ease;
}

.tag:hover {
  border-color: var(--green);
  color: var(--green);
}

/* 知识网络 */
.network {
  position: relative;
  height: 500px;
}

.node {
  position: absolute;
  padding: 18px 28px;
  border-radius: 999px;
  background: var(--card);
  backdrop-filter: blur(30px);
  border: 1px solid var(--border);
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.05);
  animation: float 6s ease-in-out infinite;
  font-size: 15px;
  font-weight: 500;
  color: var(--text);
  white-space: nowrap;
}

[data-theme="dark"] .node {
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
}

.node:nth-child(2) {
  animation-delay: 1s;
}

.node:nth-child(3) {
  animation-delay: 2s;
}

.node:nth-child(4) {
  animation-delay: 3s;
}

@keyframes float {
  50% {
    transform: translateY(-15px);
  }
}

.n1 {
  top: 50px;
  left: 0;
}

.n2 {
  top: 180px;
  right: 20px;
}

.n3 {
  top: 300px;
  left: 80px;
}

.n4 {
  top: 380px;
  right: 100px;
}

@media (max-width: 768px) {
  .hero-grid {
    grid-template-columns: 1fr;
    gap: 48px;
  }

  h1 {
    font-size: 64px;
    letter-spacing: -3px;
  }

  .subtitle {
    font-size: 24px;
  }

  .desc {
    font-size: 18px;
  }

  .network {
    display: none;
  }
}
</style>
