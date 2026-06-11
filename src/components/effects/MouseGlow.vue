<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const glowRef = ref<HTMLDivElement | null>(null)
let mouseX = 0
let mouseY = 0
let currentX = 0
let currentY = 0

const handleMouseMove = (e: MouseEvent) => {
  mouseX = e.clientX
  mouseY = e.clientY
}

const animate = () => {
  // 平滑跟随
  currentX += (mouseX - currentX) * 0.1
  currentY += (mouseY - currentY) * 0.1

  if (glowRef.value) {
    glowRef.value.style.transform = `translate(${currentX - 200}px, ${currentY - 200}px)`
  }

  requestAnimationFrame(animate)
}

onMounted(() => {
  window.addEventListener('mousemove', handleMouseMove)
  animate()
})

onUnmounted(() => {
  window.removeEventListener('mousemove', handleMouseMove)
})
</script>

<template>
  <div ref="glowRef" class="mouse-glow"></div>
</template>

<style scoped>
.mouse-glow {
  position: fixed;
  width: 400px;
  height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(34, 197, 94, 0.15), transparent 70%);
  filter: blur(120px);
  pointer-events: none;
  z-index: 0;
  mix-blend-mode: screen;
  will-change: transform;
}
</style>
