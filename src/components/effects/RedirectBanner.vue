<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const showBanner = ref(false)
const dismissed = ref(false)

// 检查是否已访问过
const checkDismissed = () => {
  const value = sessionStorage.getItem('blog-redirect-dismissed')
  dismissed.value = value === 'true'
}

// 跳转到博客
const redirectToBlog = () => {
  window.open('https://6mal.com', '_blank')
  showBanner.value = false
}

// 留在当前页面
const stayHere = () => {
  showBanner.value = false
  dismissed.value = true
  sessionStorage.setItem('blog-redirect-dismissed', 'true')
}

// 监听 Footer 元素
let observer: IntersectionObserver | null = null

const setupObserver = () => {
  const footer = document.querySelector('footer')
  if (!footer) return

  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting && !dismissed.value) {
          showBanner.value = true
        }
      })
    },
    { threshold: 0.5 }
  )

  observer.observe(footer)
}

onMounted(() => {
  checkDismissed()
  // 延迟设置 observer，确保 Footer 已渲染
  setTimeout(setupObserver, 1000)
})

onUnmounted(() => {
  if (observer) {
    observer.disconnect()
  }
})
</script>

<template>
  <Transition name="slide-up">
    <div v-if="showBanner" class="banner">
      <div class="banner-content">
        <div class="banner-text">
          <p class="banner-title">📝 想看更多内容？</p>
          <p class="banner-desc">
            访问我的博客，探索更多 AI、技术和知识管理的思考。
          </p>
        </div>
        <div class="banner-actions">
          <button @click="redirectToBlog" class="btn-primary">
            访问博客
          </button>
          <button @click="stayHere" class="btn-secondary">
            留在这里
          </button>
        </div>
      </div>
    </div>
  </Transition>
</template>

<style scoped>
.banner {
  position: fixed;
  bottom: 24px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 100;
  width: calc(100% - 48px);
  max-width: 480px;
}

.banner-content {
  background: var(--card);
  backdrop-filter: blur(40px);
  border: 1px solid var(--border);
  border-radius: 24px;
  padding: 24px;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
}

[data-theme="dark"] .banner-content {
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
}

.banner-text {
  margin-bottom: 20px;
}

.banner-title {
  font-size: 18px;
  font-weight: 600;
  color: var(--text);
  margin-bottom: 8px;
}

.banner-desc {
  font-size: 14px;
  line-height: 1.6;
  color: var(--secondary);
}

.banner-actions {
  display: flex;
  gap: 12px;
}

.btn-primary {
  flex: 1;
  padding: 12px 20px;
  border-radius: 12px;
  font-size: 14px;
  font-weight: 500;
  background: var(--text);
  color: var(--bg);
  border: none;
  cursor: pointer;
  transition: all 0.2s ease;
}

.btn-primary:hover {
  opacity: 0.9;
  transform: translateY(-1px);
}

.btn-secondary {
  flex: 1;
  padding: 12px 20px;
  border-radius: 12px;
  font-size: 14px;
  font-weight: 500;
  background: transparent;
  color: var(--secondary);
  border: 1px solid var(--border);
  cursor: pointer;
  transition: all 0.2s ease;
}

.btn-secondary:hover {
  background: var(--bg);
  color: var(--text);
}

/* 滑入动画 */
.slide-up-enter-active,
.slide-up-leave-active {
  transition: all 0.3s ease-out;
}

.slide-up-enter-from,
.slide-up-leave-to {
  transform: translateX(-50%) translateY(100%);
  opacity: 0;
}

@media (max-width: 768px) {
  .banner {
    bottom: 16px;
    width: calc(100% - 32px);
  }

  .banner-content {
    padding: 20px;
  }

  .banner-actions {
    flex-direction: column;
  }
}
</style>
