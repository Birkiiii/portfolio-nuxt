<template>
  <div class="min-h-screen bg-[#1c1c1c] text-white flex flex-col items-center justify-center px-4 text-center">
    <!-- Big 404 Display -->
    <div class="relative mb-6">
      <h1 class="text-8xl sm:text-9xl font-extrabold tracking-wider text-[#1e96fc] drop-shadow-[0_10px_20px_rgba(0,0,0,0.5)]">
        404
      </h1>
    </div>

    <!-- Error Title & Description -->
    <h2 class="text-2xl sm:text-4xl font-bold mb-4 tracking-wide uppercase">
      Page Not Found
    </h2>
    <p class="text-[#a0a0a0] max-w-md mb-8 text-base sm:text-lg">
      Oops! The page you're looking for doesn't exist, was moved, or never existed in this dimension.
    </p>

    <!-- Return Home Button -->
    <button 
      @click="handleError"
      class="bg-[#1e96fc] text-white px-6 py-3 rounded-lg text-lg font-medium transition duration-300 shadow-md hover:bg-[#187ad1] hover:scale-105 cursor-pointer"
    >
      Return to Safety
    </button>
  </div>
</template>

<script setup>
// Props passed automatically by Nuxt when an error occurs
const props = defineProps({
  error: Object
})

useHead({
  title: '404 - Page Not Found | Kirby Villegas'
})

// Nuxt helper to clear error state and redirect smoothly back to home
const handleError = () => {
  clearError({ redirect: '/' })
}
</script>

<style scoped>
/* Page transition and custom font bindings */
h1 {
  font-family: 'Alfa Slab One', cursive, sans-serif;
}
</style>