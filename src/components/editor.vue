<template>
  <div class="editor">
    <ScheduleForm @add-schedule="handler"></ScheduleForm>
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
    methods: {
      handler: function (event) {
        this.$emit('add-schedule', event)
      }
    }
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
