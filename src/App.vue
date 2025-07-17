<script setup lang="ts">
import { ref, onMounted } from 'vue'
import Header from './components/Header.vue'
import Summary from './components/Summary.vue'
import Experience from './components/Experience.vue'
import Education from './components/Education.vue'
import AdditionalInformation from './components/AdditionalInformation.vue'
import ResumeActions from './components/ResumeActions.vue'
import resume from './data/resume.json'

const isDark = ref(false)

onMounted(() => {
  const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches

  if (!localStorage.theme && prefersDark) {
    isDark.value = true
    localStorage.theme = 'dark'
    document.documentElement.classList.add('dark')
  } else if (localStorage.theme === 'dark') {
    isDark.value = true
    document.documentElement.classList.add('dark')
  } else {
    isDark.value = false
    document.documentElement.classList.remove('dark')
  }
})

const toggleDarkMode = () => {
  isDark.value = !isDark.value
  localStorage.theme = isDark.value ? 'dark' : 'light'
  document.documentElement.classList.toggle('dark')
}
</script>

<template>
  <main :class="{ dark: isDark }" class="min-h-screen bg-white text-gray-900 dark:bg-gray-900 dark:text-gray-100 px-4 lg:px-0">
    <ResumeActions :isDark="isDark" @toggleTheme="toggleDarkMode" />

    <div class="max-w-3xl mx-auto">
      <Header :name="resume.name" :location="resume.location" :contact="resume.contact" />

      <Summary :summary="resume.summary" />

      <Experience :items="resume.experience" />

      <Education :title="'Education'" :items="resume.education" />

      <Education :title="'Certifications'" :items="resume.certifications" />

      <AdditionalInformation :items="resume.additionalInformation" />
    </div>
  </main>
</template>
