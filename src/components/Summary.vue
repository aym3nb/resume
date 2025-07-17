<script setup lang="ts">
defineProps<{
  summary: string;
}>()
</script>

<template>
  <section class="mb-6">
    <h2 class="text-xl font-semibold mb-2">Summary</h2>
    <p>
      {{ summary }}
    </p>
  </section>
</template>
