<template>
  <div>

  </div>
</template>

<script>
import EventService from '@/service/EventService';

  export default {
    name: "Array",
    created () {
      EventService.getArrayList()
        .then(response => console.log('response: ', response.data))
        .catch(error => console.error("error api call: ", console.error();))
    },
  }
</script>

<style scoped>

</style>