<template>
  <div id="container">
    <Calendar
    ></Calendar>
    <Editor
      :onAddSchedule="onAddSchedule"
      :onRemoveSchedule="onRemoveSchedule"
      :schedules="scheduleList[selectedDate]"
    ></Editor>
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
      },
      onRemoveSchedule: function (index) {
        this.$data.scheduleList[this.$data.selectedDate].splice(index, 1)
      }
    }
  }
</script>

<style>
#container {
  width: 100vw;
  display: flex;
  align-items: flex-start;
  justify-content: flex-start;
}
</style>
