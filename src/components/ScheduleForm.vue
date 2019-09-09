<template>
  <div class="form">
    <form class="add-form" @submit.prevent="addSchedule">
      <input type="text" placeholder="予定を入れてね">
      <button type="submit">add</button>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'scheduleForm',
    props: ['name'],
    methods: {
      addSchedule: function (event) {
        this.$emit('add-schedule', event)
      }
    }
  }
</script>

<style>
.form {
  width: 60%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
