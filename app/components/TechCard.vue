<template>
  <article
    class="tech-stack-card card bg-neutral text-neutral-content shadow-xl"
    :class="{ 'is-expanded': expanded }"
    :aria-expanded="expanded"
    role="button"
    tabindex="0"
    @click="$emit('toggle')"
    @keydown.enter.prevent="$emit('toggle')"
    @keydown.space.prevent="$emit('toggle')"
  >
    <div class="card-body flex-row items-center justify-center gap-5 p-6">
      <h2 class="tech-stack-name">{{ item.name }}</h2>
      <img :id="item.id" :src="item.image" :alt="item.name" class="tech-stack-logo" />
    </div>

    <div class="tech-stack-details card bg-neutral text-neutral-content shadow-xl">
      <div class="card-body p-5 text-center">
        <span class="badge badge-primary badge-outline mx-auto">{{ item.title }}</span>
        <p>{{ item.description }}</p>
      </div>
    </div>
  </article>
</template>

<script setup>
defineProps({
  item: {
    type: Object,
    required: true
  },
  expanded: {
    type: Boolean,
    default: false
  }
})

defineEmits(['toggle'])
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
  cursor: pointer;
  transition: transform 0.4s ease, box-shadow 0.4s ease, margin-bottom 0.4s ease;
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

.tech-stack-details {
  position: absolute;
  z-index: 1;
  top: calc(100% + 10px);
  left: 0;
  width: 100%;
  opacity: 0;
  visibility: hidden;
  pointer-events: none;
  transform: translateY(-8px);
  transition: opacity 0.3s ease, transform 0.3s ease, visibility 0.3s ease;
}

.tech-stack-details p {
  margin: 0;
  color: #d6d6d6;
  font-size: 14px;
  line-height: 1.5;
  font-family: Arial, sans-serif;
}

.is-expanded {
  z-index: 20;
  margin-bottom: 140px;
}

.is-expanded .tech-stack-logo {
  transform: translateY(-20px);
}

.is-expanded .tech-stack-details {
  opacity: 1;
  visibility: visible;
  pointer-events: auto;
  transform: translateY(0);
}

@media (max-width: 768px) {
  .tech-stack-card {
    flex-basis: 260px;
  }
}
</style>
