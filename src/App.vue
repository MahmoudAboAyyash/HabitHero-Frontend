<script setup>
import { ref, onMounted } from 'vue'
import HabitList from './components/HabitList.vue'

const habits = ref([])
const loading = ref(true)
const error = ref('')

onMounted(async () => {
  try {
    const response = await fetch(
      'https://habithero-backend-gbkh.onrender.com/api/habits'
    )

    if (!response.ok) {
      throw new Error(`HTTP ${response.status}`)
    }

    habits.value = await response.json()
  } catch {
    error.value = 'Die Habits konnten nicht geladen werden.'
  } finally {
    loading.value = false
  }
})
</script>

<template>
  <main>
    <h1>HabitHero</h1>
    <p>Build better habits!</p>

    <p v-if="loading">Habits werden geladen …</p>
    <p v-else-if="error" role="alert">{{ error }}</p>
    <HabitList v-else :habits="habits" />
  </main>
</template>

<style scoped>
main {
  width: 100%;
  max-width: 900px;
  margin: 40px auto;
  padding: 20px;
  font-family: Arial, sans-serif;
  box-sizing: border-box;
}

h1 {
  color: #16a34a;
  text-align: center;
}

main > p {
  text-align: center;
}
</style>