<template>
  <section class="philosophy">
    <div>
      <div class="quote">
        技术变化很快。<br />
        原则会不断复利。<br />
        系统能够穿越时间。
      </div>
      <div class="small">构建系统 · 分享思考 · 持续学习</div>
    </div>
  </section>
</template>

<style scoped>
.philosophy {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 120px 0;
}

.quote {
  font-size: 78px;
  line-height: 1.4;
  letter-spacing: -3px;
  font-weight: 700;
  color: var(--text);
}

.small {
  margin-top: 40px;
  color: var(--secondary);
  font-size: 24px;
}

@media (max-width: 768px) {
  .quote {
    font-size: 44px;
    letter-spacing: -2px;
  }

  .small {
    font-size: 18px;
  }
}
</style>
