<template>
  <main class="wrapper">
    <div class="left-container">
      <img src="/images/id kirby 2.png" alt="Profile picture" id="dp" />

      <h1 id="name">{{ firstName }}</h1>
      <h1 id="Lname">{{ lastName }}</h1>

      <div class="line"></div>

      <p id="shortintro">{{ desc }}</p>

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

// Personal Info State
const firstName = ref('Kirby')
const lastName = ref('Villegas')
const desc = ref('Aspiring Web Developer')

const socials = ref({
  github: 'https://github.com/Birkiiii',
  linkedin: 'https://www.linkedin.com/in/your-linkedin'
})

const url = useRequestURL()

const title = 'Home | Kirby Villegas'
const description = 'Welcome to the personal website of Kirby Villegas, an aspiring web developer. Explore my portfolio, learn about my skills, and connect with me on GitHub and LinkedIn.'

useHead({
  title,
  link: [{ rel: 'canonical', href: url.href }],
})

useSeoMeta({
  description,
  ogTitle: title,
  ogDescription: description,
  ogType: 'website',
  ogUrl: url.href,
  ogImage: `${url.origin}/images/id kirby 2.png`, 
  ogImageAlt: 'Kirby Villegas portrait image',
})

</script>


<style scoped>
/* Page-specific styling for the profile section */
</style>