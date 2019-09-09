<template>
  <div class="form">
    <form class="add-form" @submit.prevent="addSchedule">
      <input type="text" placeholder="予定を入れてね" ref="name">
      <button type="submit">add</button>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'scheduleForm',
    props: ['onAddSchedule'],
    methods: {
      addSchedule: function (event) {
        const name = this.$refs.name.value
        this.$props.onAddSchedule(name)
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
