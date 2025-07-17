<script setup lang="ts">
import type { Contact } from '../types'

defineProps<{
  name: string;
  location: string;
  contact: Contact;
}>()
</script>

<template>
  <header class="my-8 text-center">
    <h1 class="text-4xl font-bold">{{ name }}</h1>
    <div class="mt-4 flex flex-wrap gap-4 justify-center text-sm text-gray-600 dark:text-gray-400">
      <span class="flex items-center">
        <img class="mr-2 inline size-4" src="../assets/map-pin.svg" alt="" /> {{ location }}
      </span>
      <span class="flex items-center">
        <img class="mr-2 inline size-4" src="../assets/mobile.svg" alt="" />
        <a :href="`tel:${ contact.mobile }`">{{ contact.mobile }}</a>
      </span>
      <span class="flex items-center">
        <img class="mr-2 inline size-4" src="../assets/envelope.svg" alt="" />
        <a :href="`mailto:${ contact.email }`">{{ contact.email }}</a>
      </span>
      <span class="flex items-center">
        <img class="mr-2 inline size-4" src="../assets/github.svg" alt="" />
        <a :href="`https://github.com/${ contact.github }`" target="blank">{{ contact.github }}</a>
      </span>
    </div>
  </header>
</template>
