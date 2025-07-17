<script setup lang="ts">
defineProps<{
  isDark: boolean;
}>()

const emit = defineEmits(['toggleTheme'])

const handleToggle = () => {
  emit('toggleTheme')
}
</script>

<template>
  <div class="w-full flex justify-end p-4">
    <button @click="handleToggle" class="text-xl hover:opacity-75 transition cursor-pointer" aria-label="Toggle Dark Mode">
      <img v-if="isDark" class="inline size-6" src="../assets/sun.svg" alt="Light" />
      <img v-else class="inline size-6" src="../assets/moon.svg" alt="Dark" />
    </button>

    <a
      href="/AYMEN_BARECHE_Resume.pdf"
      download
      class="text-xl hover:opacity-75 transition cursor-pointer ml-4"
      title="Download Resume"
    >
      <img class="inline size-6" src="../assets/download.svg" alt="" />
    </a>
  </div>
</template>
