<script setup lang="ts">
import { ref, onMounted } from 'vue'
import ParticleCanvas from './components/effects/ParticleCanvas.vue'
import MouseGlow from './components/effects/MouseGlow.vue'
import Hero from './components/sections/Hero.vue'
import About from './components/sections/About.vue'
import Focus from './components/sections/Focus.vue'
import Garden from './components/sections/Garden.vue'
import Principles from './components/sections/Principles.vue'
import Philosophy from './components/sections/Philosophy.vue'
import Contact from './components/sections/Contact.vue'
import Footer from './components/sections/Footer.vue'

const isDarkMode = ref(false)

onMounted(() => {
  const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches
  const savedTheme = localStorage.getItem('theme')
  isDarkMode.value = savedTheme ? savedTheme === 'dark' : prefersDark
  document.documentElement.setAttribute('data-theme', isDarkMode.value ? 'dark' : 'light')
})

const toggleTheme = () => {
  isDarkMode.value = !isDarkMode.value
  document.documentElement.setAttribute('data-theme', isDarkMode.value ? 'dark' : 'light')
  localStorage.setItem('theme', isDarkMode.value ? 'dark' : 'light')
}
</script>

<template>
  <div>
    <!-- 背景效果 -->
    <ParticleCanvas />
    <MouseGlow />

    <!-- 背景光晕 -->
    <div class="bg-blur">
      <div class="blur blur1"></div>
      <div class="blur blur2"></div>
      <div class="blur blur3"></div>
    </div>

    <!-- 主题切换 -->
    <button @click="toggleTheme" class="theme-toggle" aria-label="切换主题">
      <svg v-if="isDarkMode" width="20" height="20" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z" />
      </svg>
      <svg v-else width="20" height="20" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z" />
      </svg>
    </button>

    <!-- 页面内容 -->
    <Hero />
    <About />
    <Focus />
    <Garden />
    <Principles />
    <Philosophy />
    <Contact />
    <Footer />
  </div>
</template>

<style>
/* 背景光晕 */
.bg-blur {
  position: fixed;
  inset: 0;
  z-index: -2;
  overflow: hidden;
}

.blur {
  position: absolute;
  border-radius: 50%;
  filter: blur(140px);
  opacity: 0.25;
}

.blur1 {
  width: 500px;
  height: 500px;
  background: #4f8cff;
  top: -120px;
  left: -100px;
}

.blur2 {
  width: 600px;
  height: 600px;
  background: #22c55e;
  right: -150px;
  top: 300px;
}

.blur3 {
  width: 400px;
  height: 400px;
  background: #9b8cff;
  bottom: -100px;
  left: 40%;
}

/* 主题切换 */
.theme-toggle {
  position: fixed;
  top: 24px;
  right: 24px;
  z-index: 50;
  width: 44px;
  height: 44px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--card);
  backdrop-filter: blur(30px);
  border: 1px solid var(--border);
  cursor: pointer;
  color: var(--secondary);
  transition: all 0.2s ease;
}

.theme-toggle:hover {
  transform: scale(1.05);
}
</style>
