<template>
  <div class="ts-div">
    <div class="techstack">
      <h1 class="Tech">TECH</h1>
      <h1 class="Stack">STACK</h1>
    </div>

    <h1 id="fe">FRONTEND</h1>
    <div class="tech-stack-container">
      <TechCard
        v-for="item in frontendStack"
        :key="item.name"
        :item="item"
      />
    </div>

    <h1 id="be">BACKEND</h1>
    <div class="tech-stack-container">
      <TechCard
        v-for="item in backendStack"
        :key="item.name"
        :item="item"
      />
    </div>

    <h1 id="tl">TOOLS</h1>
    <div class="tech-stack-container">
      <TechCard
        v-for="item in toolsStack"
        :key="item.name"
        :item="item"
      />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

useHead({
  title: 'Tech Stack | Kirby Villegas'
})

// Frontend Data
const frontendStack = ref([
  {
    name: 'HTML',
    image: '/images/html logo.png'
  },
  {
    name: 'CSS',
    id: 'csslogo',
    image: '/images/css logo.png'
  },
  {
    name: 'Javascript',
    image: '/images/javascript-logo.png'
  }
])

// Backend Data
const backendStack = ref([
  {
    name: 'Java',
    image: '/images/java logo.png'
  },
  {
    name: 'C',
    id: 'clogo',
    image: '/images/c logo.png'
  },
  {
    name: 'PostgreSQL',
    image: '/images/pg logo.png'
  },
  {
    name: 'Python',
    image: '/images/python logo.png'
  }
])

// Tools Data
const toolsStack = ref([
  {
    name: 'Github',
    image: '/images/gh logo.webp'
  },
  {
    name: 'Git',
    image: '/images/git logo.png'
  },
  {
    name: 'Android Studio',
    image: '/images/android studio logo.png'
  },
  {
    name: 'VsCode',
    image: '/images/vscode logo.png'
  }
])

const url = useRequestURL()

const title = 'Tech Stack | Kirby Villegas'
const description = 'Explore the technologies and tools that Kirby Villegas uses to build web applications and solve real-world problems.'

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
})

</script>

<style scoped>
/* Component styles */
</style>