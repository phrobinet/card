<template>
  <div>
    <div v-for="item in items" :key="item.id">
      {{ item.title }}
    </div>
  </div>
</template>

<script>
import EventService from '@/service/EventService';

export default {
  name: "Array",
  data() {
    return {
      items: null
    }
  },
  created() {
    EventService.getEvents()
      .then(response => {
        this.items = response.data
      })
      .catch(error => {
        console.log(error)
      })
  },
}
</script>

<style scoped>

</style>