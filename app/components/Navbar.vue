<template>
  <div class="navbar sticky top-0 z-50 bg-base-100/80 shadow-sm backdrop-blur-sm">
    <div class="navbar-start">
      <NuxtLink to="/" class="btn btn-ghost text-xl font-bold text-primary">KMV</NuxtLink>
    </div>

    <div class="navbar-center hidden lg:flex">
      <ul class="menu menu-horizontal px-1 gap-2">
        <li>
          <NuxtLink to="/about" class="rounded-full">About</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/certification" class="rounded-full">Certifications</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/tech-stack" class="rounded-full">Tech Stack</NuxtLink>
        </li>
      </ul>
    </div>

    <div class="navbar-end lg:hidden">
      <button class="btn btn-ghost btn-circle" @click="toggleMenu" aria-label="Toggle menu">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
      </button>
    </div>
  </div>

  <div v-if="isMenuOpen" class="lg:hidden px-4 pb-4">
    <ul class="menu menu-sm bg-base-200 rounded-box w-full gap-2">
      <li>
        <NuxtLink to="/about" @click="closeMenu">About</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/certification" @click="closeMenu">Certifications</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/tech-stack" @click="closeMenu">Tech Stack</NuxtLink>
      </li>
    </ul>
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
