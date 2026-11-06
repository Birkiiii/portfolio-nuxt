<template>
  <div>
    <!-- Animated Particles Background -->
    <div class="particles">
      <span v-for="n in 30" :key="n"></span>
    </div>

    <!-- Global Navigation Header -->
    <header>
      <div class="navdiv">
        <div class="logo">
          <NuxtLink to="/" class="nav-branding">KMV</NuxtLink>
        </div>

        <ul class="nav-links" :class="{ active: isMenuOpen }">
          <li class="nav-item">
            <NuxtLink to="/about" @click="closeMenu">About</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink to="/certification" @click="closeMenu">Certifications</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink to="/tech-stack" @click="closeMenu">Tech Stack</NuxtLink>
          </li>
        </ul>

        <div class="hamburger" :class="{ active: isMenuOpen }" @click="toggleMenu">
          <span class="bar"></span>
          <span class="bar"></span>
          <span class="bar"></span>
        </div>
      </div>
    </header>

    <!-- Page Content Viewport -->
    <main>
      <NuxtPage />
    </main>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<style>
/* Global navigation styles and keyframes go here */
</style>