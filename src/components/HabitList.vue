
<script setup>
defineProps({
  habits: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <section>
    <h2>Meine Gewohnheiten</h2>

    <div
      v-for="habit in habits"
      :key="habit.id"
      class="habit-card"
    >
      <h3>{{ habit.name }}</h3>
      <p>{{ habit.description }}</p>
      <p>Ziel: {{ habit.targetPerWeek }}x pro Woche</p>
      <p>Status: {{ habit.active ? 'Aktiv' : 'Inaktiv' }}</p>
    </div>
  </section>
</template>

<style scoped>
section {
  width: 100%;
  max-width: 600px;
  margin: 30px auto;
}

h2 {
  text-align: center;
  margin-bottom: 25px;
}

.habit-card {
  background-color: #f0fdf4;
  color: #166534;
  padding: 20px;
  margin: 15px 0;
  border: 1px solid #bbf7d0;
  border-radius: 12px;
}
</style>
