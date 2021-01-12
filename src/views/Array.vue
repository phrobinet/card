<template>
  <CardDetail v-for="item in items" :key="item.id" :item="item"/>
  <!-- <div>
    <p v-for="item in items" :key="item.id" :card="item">
      {{ item.back.title }}
    </p>
  </div> -->
</template>

<script>
import EventService from '@/service/EventService';
import CardDetail from  '@/components/CardDetail';

export default {
  name: "Array",
  components: {
    CardDetail,
  },
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