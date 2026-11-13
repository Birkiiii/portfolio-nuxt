<template>
  <div class="ts-div">
    <div class="techstack">
      <h1 class="Tech">TECH</h1>
      <h1 class="Stack">STACK</h1>
    </div>

    <h1 id="fe">FRONTEND</h1>
    <div class="tech-stack-container">
      <TechCard v-for="item in frontendStack" :key="item.name" :item="item" />
    </div>

    <h1 id="be">BACKEND</h1>
    <div class="tech-stack-container">
      <TechCard v-for="item in backendStack" :key="item.name" :item="item" />
    </div>

    <h1 id="tl">TOOLS</h1>
    <div class="tech-stack-container">
      <TechCard v-for="item in toolsStack" :key="item.name" :item="item" />
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
    title: 'HTML',
    image: '/images/html logo.png',
    description: 'HyperText Markup Language used to structure web pages and content.'
  },
  {
    name: 'CSS',
    title: 'CSS',
    id: 'csslogo',
    image: '/images/css logo.png',
    description: 'Cascading Style Sheets used to design and style websites beautifully.'
  },
  {
    name: 'Javascript',
    title: 'JavaScript',
    image: '/images/javascript-logo.png',
    description: 'A programming language that adds interactivity and dynamic behavior to websites.'
  }
])

// Backend Data
const backendStack = ref([
  {
    name: 'Java',
    title: 'JAVA',
    image: '/images/java logo.png',
    description: 'A powerful object-oriented programming language used for desktop, web, and mobile applications.'
  },
  {
    name: 'C',
    title: 'C Language',
    id: 'clogo',
    image: '/images/c logo.png',
    description: 'A foundational programming language known for speed, efficiency, and system-level programming.'
  },
  {
    name: 'PostgreSQL',
    title: 'PostgreSQL',
    image: '/images/pg logo.png',
    description: 'An advanced open-source database system used for storing and managing application data.'
  },
  {
    name: 'Python',
    title: 'Python',
    image: '/images/python logo.png',
    description: 'A versatile and beginner-friendly programming language used for web development, automation, and data science.'
  }
])

// Tools Data
const toolsStack = ref([
  {
    name: 'Github',
    title: 'Github',
    image: '/images/gh logo.webp',
    description: 'A cloud-based platform used to store, manage, and collaborate on coding projects.'
  },
  {
    name: 'Git',
    title: 'Git',
    image: '/images/git logo.png',
    description: 'A version control system used to track code changes and manage development history.'
  },
  {
    name: 'Android Studio',
    title: 'Android Studio',
    image: '/images/android studio logo.png',
    description: 'The official IDE for building and developing Android mobile applications.'
  },
  {
    name: 'VsCode',
    title: 'Visual Studio Code',
    image: '/images/vscode logo.png',
    description: 'A lightweight and powerful code editor used for programming and web development.'
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