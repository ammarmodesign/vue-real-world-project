<script setup>
defineProps({
  event: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <RouterLink :to="{ name: 'event-details', params: { id: event.id } }" class="events" v-if="event">
    <div class="event-card">
      <h1>{{ event.title }}</h1>
      <p>@{{ event.time }} on {{ event.date }}</p>
    </div>
  </RouterLink>
</template>

<style scoped>
.event-card {
  border: 2px solid black;
  padding: 16px;
  margin: 24px;
}
</style>
