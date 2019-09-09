<template>
  <div id="container">
    <Calendar></Calendar>
    <Editor :onAddSchedule="onAddSchedule"></Editor>
  </div>
</template>

<script>
  import Calendar from "./Calendar"
  import Editor from "./editor"
  export default {
    name: 'app',
    components: {
      Calendar,
      Editor
    },
    data: function () {
      return {
        scheduleList: new Array(30).fill(0).map(v => []),
        selectedDate: 8
      }
    },
    methods: {
      onAddSchedule: function (schedule) {
        this.$data.scheduleList[this.$data.selectedDate].push(schedule)
        console.log(this.$data.scheduleList[this.$data.selectedDate])
      }
    }
  }
</script>

<style>
#container {
  width: 100vw;
  display: flex;

}
</style>
