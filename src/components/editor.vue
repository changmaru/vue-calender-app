<template>
  <div class="editor">
    <ScheduleForm
      :onAddSchedule="onAddSchedule"
    ></ScheduleForm>
    <div v-for="(schedule, index) in schedules">
      <Schedule
        :name="schedule"
        :index="index"
        :onRemoveSchedule="onRemoveSchedule"
      ></Schedule>
    </div>
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
    props: ['onAddSchedule', 'onRemoveSchedule', 'schedules']
  }
</script>

<style>
.editor {
  width: 50vw;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}
</style>
