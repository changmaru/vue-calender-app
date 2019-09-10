<template>
  <div class="editor">
    <ScheduleForm
      :onAddSchedule="onAddSchedule"
    ></ScheduleForm>
    <div v-for="(schedule, index) in schedules" :key="index" class="schedules">
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
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border-left: 1px solid black;
}

.schedules {
  width: 60%;
  margin-bottom: 24px;
}
</style>
