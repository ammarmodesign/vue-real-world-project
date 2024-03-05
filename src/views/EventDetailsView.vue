<script setup>
import { onMounted, ref } from 'vue'
import EventsSevice from '@/services/EventsSevice'
const event = ref(null)

const props = defineProps({
  id: {
    required: true
  }
})

onMounted(() => {
  EventsSevice.getEvent(props.id).then((res) => {
    event.value = res.data
  })
})
</script>

<template>
  <main>
    <div v-if="event">
      <h1>{{ event.title }}</h1>
      <p>@{{ event.time }} on {{ event.date }}</p>
    </div>
  </main>
</template>
