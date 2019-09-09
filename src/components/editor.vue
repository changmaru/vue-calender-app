<template>
  <div class="editor">
    <ScheduleForm :onAddSchedule="onAddSchedule"></ScheduleForm>
    <Schedule name="hoge"></Schedule>
  </div>
</template>

<script>
  import Schedule from "./schedule"
  import ScheduleForm from "./ScheduleForm"
  export default {
    name: 'editor',
    components: {
      Schedule,
      ScheduleForm
    },
    props: ['onAddSchedule']
  }
</script>

<style>
.editor {
  width: 50vw;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}
</style>
