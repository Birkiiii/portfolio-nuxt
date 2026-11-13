<template>
  <div class="card h-full bg-base-200 shadow-xl transition-transform duration-300 hover:-translate-y-1 hover:shadow-2xl">
    <figure class="px-6 pt-6">
      <img :id="item.id" :src="item.image" :alt="item.name" class="h-24 w-24 object-contain" />
    </figure>

    <div class="card-body items-center text-center">
      <span class="badge badge-primary badge-outline">{{ item.name }}</span>
      <h2 class="card-title text-base-content">{{ item.title }}</h2>
      <p class="text-sm text-base-content/80">{{ item.description }}</p>
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
