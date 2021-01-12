<template>
  <div>
    <p v-for="item in items" :key="item.id">
      {{ item }}
    </p>
    <!-- <p>{{ items.data }}</p> -->
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
        this.items = response
      })
      .catch(error => {
        console.log(error)
      })
  },
}
</script>

<style scoped>

</style>