<script setup lang="ts">
import type { Education } from '../types'

defineProps<{
  title: string;
  items: Education[];
}>()
</script>

<template>
  <section class="mb-6">
    <h2 class="text-xl font-semibold mb-2">{{ title }}</h2>

    <div v-for="(item, index) in items" :key="`education-${index}`" class="mb-4">
      <p>{{ item.degree }}</p>
      <p>{{ item.institution }} – {{ item.location }} • {{ item.period }}</p>
    </div>
  </section>
</template>
