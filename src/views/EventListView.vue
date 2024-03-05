<script setup>
import EventCard from '@/components/EventCard.vue'
import { onMounted, ref } from 'vue'
import EventsSevice from '@/services/EventsSevice'

const events = ref(null)
const error = ref(null)
onMounted(() => {
  EventsSevice.getEvents()
    .then((res) => {
      events.value = res.data
    })
    .catch((err) => {
      error.value = err.message
    })
})
</script>

<template>
  <main>
    <EventCard v-for="(event, index) in events" :event="event" :key="index" />
  </main>
</template>
