<template>
  <main class="wrapper">
    <div class="left-container">
      <img src="/images/id kirby 2.png" alt="Profile picture" id="dp" />

      <h1 id="name">{{ firstName }}</h1>
      <h1 id="Lname">{{ lastName }}</h1>

      <div class="line"></div>

      <p id="shortintro">{{ title }}</p>

      <div class="social-icons">
        <a :href="socials.github" target="_blank" rel="noreferrer">
          <img src="/images/gh logo.webp" class="icon" alt="GitHub" />
        </a>
        <a :href="socials.linkedin" target="_blank" rel="noreferrer">
          <img src="/images/li logo.webp" class="icon" alt="LinkedIn" />
        </a>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'

// Set page title for Nuxt
useHead({
  title: 'Home | Kirby Villegas'
})

// Personal Info State
const firstName = ref('Kirby')
const lastName = ref('Villegas')
const title = ref('Aspiring Web Developer')

const socials = ref({
  github: 'https://github.com/Birkiiii',
  linkedin: 'https://www.linkedin.com/in/your-linkedin'
})
</script>

<style scoped>
/* Page-specific styling for the profile section */
</style>