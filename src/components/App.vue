<template>
  <div id="container">
    <Calendar></Calendar>
    <Editor @submit.capture="console.log"></Editor>
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
        scheduleList: []
      }
    },
    methods: {
      addSchedule: function (event) {
        console.log(event)
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
