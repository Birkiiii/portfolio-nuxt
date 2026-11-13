<template>
  <article class="tech-stack-card card bg-neutral text-neutral-content shadow-xl">
    <div class="card-body flex-row items-center justify-center gap-5 p-6">
      <h2 class="tech-stack-name">{{ item.name }}</h2>
      <img :id="item.id" :src="item.image" :alt="item.name" class="tech-stack-logo" />
    </div>
  </article>
</template>

<script setup>
defineProps({
  item: {
    type: Object,
    required: true
  }
})
</script>

<style scoped>
.tech-stack-card {
  position: relative;
  flex: 1 1 260px;
  width: 100%;
  max-width: 320px;
  min-width: 220px;
  height: 220px;
  overflow: visible;
  transition: transform 0.4s ease, box-shadow 0.4s ease;
}

.tech-stack-card:hover {
  z-index: 10;
  transform: scale(1.03) translateY(-5px);
  box-shadow: 0 15px 30px #00000088;
}

.tech-stack-name {
  margin: 0;
  font-family: "Roboto Mono", monospace;
  font-size: 22px;
  transition: transform 0.3s ease;
}

.tech-stack-card:hover .tech-stack-name {
  transform: translateY(-5px);
}

.tech-stack-logo {
  width: 70px;
  height: 70px;
  object-fit: contain;
  transition: transform 0.3s ease;
}

.tech-stack-card:hover .tech-stack-logo {
  transform: translateY(-10px);
}

@media (max-width: 768px) {
  .tech-stack-card {
    flex-basis: 260px;
  }
}
</style>
