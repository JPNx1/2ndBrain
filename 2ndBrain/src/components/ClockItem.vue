<template>
  <div id="clock">
    <p class="date">It is {{ weekday }}, the {{ date }}</p>
    <p class="time">{{ time }}</p>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
export default defineComponent ({
  data() {
    return {
      date: 'Current Date',
      time: 'Current Time',
      weekday : 'Current Weekday'
    }
  },
  created() {
    this.date = this.getDate()
    this.time = this.updateTime()
    this.week = this.getWeekday()
  },
  mounted() {
    this.interval = setInterval(() => {
      this.time = this.updateTime()
    }, 1000)
  },
  methods: {
    getDate() {
      let date = new Date()
      let month = date.getMonth()

      if(month < 10)
        month = month.padStart(1)

      return date.getDate() + '.' + month + '.' + date.getFullYear()
    },
    updateTime() {
      let date = new Date()
      return date.getHours() + ':' + date.getMinutes() + ':' + date.getSeconds()
    },
    getWeekday()
    {
      let date = new Date()
      return date.getWeekday()
    }
  }
})
</script>
