<template>
  <div id="container">
    <Calendar
      :hasScheduleList="hasScheduleList"
      :selectedDate="selectedDate"
      :onSelectDate="onSelectDate"
    />
    <Editor
      :onAddSchedule="onAddSchedule"
      :onRemoveSchedule="onRemoveSchedule"
      :schedules="scheduleList[selectedDate - 1]"
    />
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
        selectedDate: new Date().getDate()
      }
    },
    methods: {
      onSelectDate: function (date) {
        this.$data.selectedDate = parseInt(date, 10)
      },
      onAddSchedule: function (schedule) {
        if (schedule.match(/^\s*$/)) return
        this.$data.scheduleList[this.$data.selectedDate - 1].push(schedule.trim())
      },
      onRemoveSchedule: function (index) {
        this.$data.scheduleList[this.$data.selectedDate - 1].splice(index, 1)
      }
    },
    computed: {
      hasScheduleList: function() {
        return this.scheduleList.map(schedules => schedules.length > 0)
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
