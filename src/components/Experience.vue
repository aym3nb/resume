<script setup lang="ts">
import type { Experience } from '../types'
import ExperienceItem from './ExperienceItem.vue';

defineProps<{
  items: Experience[];
}>()
</script>

<template>
  <section class="mb-6">
    <h2 class="text-xl font-semibold mb-2">Experience</h2>

    <ExperienceItem
      v-for="(item, index) in items"
      :key="`job-${index}`"
      :role="item.role"
      :company="item.company"
      :period="item.period"
      :location="item.location"
      :highlights="item.highlights"
    />
  </section>
</template>
