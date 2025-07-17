<script setup lang="ts">
defineProps<{
  items: string[];
}>()
</script>

<template>
  <section class="mb-6">
    <h2 class="text-xl font-semibold mb-2">Additional Information</h2>

    <div v-for="(item, index) in items" :key="`additional-info-${index}`" class="mb-4">
      <p>{{ item }}</p>
    </div>
  </section>
</template>
