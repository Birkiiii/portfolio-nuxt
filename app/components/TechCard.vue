<template>
  <div class="tech-card">
    <h3>{{ item.name }}</h3>
    <img :id="item.id" :src="item.image" :alt="item.name" />
    <div class="tech-info">
      <h2>{{ item.title }}</h2>
      <p class="deft">{{ item.description }}</p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  item: {
    type: Object,
    required: true
  }
})
</script>
