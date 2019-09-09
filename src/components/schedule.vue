<template>
  <div class="schedule">
    <div class="name">{{ name }}</div>
    <button class="delete-button" @click="removeSchedule">X</button>
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
  width: 100%;
  height: 36px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.name {

}

</style>
