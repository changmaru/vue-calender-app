<template>
  <div class="schedule">
    <div>{{ name }}</div>
    <button @click="removeSchedule">X</button>
  </div>
</template>

<script>
  export default {
    name: 'schedule',
    props: ['name'],
    methods: {
      removeSchedule: function (event) {
        this.$emit('remove-schedule', event)
      }
    }
  }
</script>

<style>
.schedule {
  width: 60%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
