<template>
  <div class="schedule">
    <div>{{ name }}</div>
    <button @click="removeSchedule">X</button>
  </div>
</template>

<script>
  export default {
    name: 'schedule',
    props: ['onRemoveSchedule', 'name', 'index'],
    methods: {
      removeSchedule: function () {
        this.$props.onRemoveSchedule(this.$props.index)
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
