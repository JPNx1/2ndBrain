<script setup lang="ts">
  import ClockItem from '../components/ClockItem.vue'
  defineProps<{
    usr: string
  }>()

</script>

<template>
  <div>
    <h1>Good {{ partOfDay }} {{ usr }}</h1>
  </div>
  <div>
    <ClockItem />
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      partOfDay: 'Morning'
    }
  },
  created() {
    this.partOfDay = this.getTimeOfDay()

    let interval = setInterval(() => {
      this.partOfDay = this.getTimeOfDay()
    }, 3600000) 
  },
  methods:
  {
    getTimeOfDay()
    {
      let date = new Date()
      let currentHour = date.getHours()
         if (currentHour >= 5 && currentHour < 12) {
           return 'morning'
         } else if (currentHour >= 12 && currentHour < 17) {
           return 'day'
         } else if (currentHour >= 17 && currentHour < 21) {
           return 'afternoon'
         } else if (currentHour >= 21 && currentHour <= 23) {
           return 'evening'
         } else {
           return 'night'
         }
    }
  }
}
</script>

<style></style>
