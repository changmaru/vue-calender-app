<template>
  <div @click="selectDate"> {{ date }} </div>
</template>

<script>
  export default {
    name: 'day',
    props: ['onSelectDate', 'date'],
    methods: {
      selectDate: function () {
        this.$props.onSelectDate(this.$props.date)
      }
    }
  }
</script>

<style>
</style>
