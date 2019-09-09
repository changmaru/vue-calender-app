<template>
  <div class="form">
    <form class="add-form" @submit.prevent="addSchedule">
      <input class="schedule-name" type="text" placeholder="予定を入れてね" ref="name">
      <button class="add-button" type="submit">add</button>
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
        this.$refs.name.value = ''
        this.$props.onAddSchedule(name)
      }
    }
  }
</script>

<style>
.form {
  width: 100%;
  height: 10vh;
  margin-top: calc((100vh - 30vw) * 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}

.add-form {
  width: 70%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.schedule-name {
  width: 80%;
}

.add-button {
  width: 10%;
}

</style>
