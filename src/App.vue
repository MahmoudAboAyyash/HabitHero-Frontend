
<script setup>
import HabitList from './components/HabitList.vue'

const habits = [
  {
    id: 1,
    name: 'Sport machen',
    description: '3-mal pro Woche trainieren',
    targetPerWeek: 3,
    active: true
  },
  {
    id: 2,
    name: 'Englisch lernen',
    description: 'Jeden Tag 30 Minuten lernen',
    targetPerWeek: 7,
    active: true
  },
  {
    id: 3,
    name: 'Lesen',
    description: '20 Seiten pro Tag lesen',
    targetPerWeek: 7,
    active: true
  }
]
</script>

<template>
  <main>
    <h1>HabitHero</h1>
    <p>Build better habits!</p>

    <HabitList :habits="habits" />
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

