<script setup lang="ts">
import type { Experience } from '../types'

defineProps<Experience>()
</script>

<template>
  <div class="mb-4">
    <h3 class="font-bold">{{ role }} — {{ company }}</h3>
    <p class="text-sm text-gray-500">{{ period }} • {{ location }}</p>
    <ul class="list-disc ml-6 mt-2 space-y-1">
      <li v-for="(highlight, index) in highlights" :key="`${role}-${company}-highlight-${index}`" >{{ highlight }}</li>
    </ul>
  </div>
</template>
