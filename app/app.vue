<template>
  <div>
    <!-- Animated Particles Background -->
    <div class="particles">
      <span v-for="n in 30" :key="n"></span>
    </div>

    <Navbar />

    <!-- Page Content Viewport -->
    <main>
      <NuxtPage />
    </main>
  </div>
</template>


<style>
/* Global navigation styles and keyframes go here */
</style>