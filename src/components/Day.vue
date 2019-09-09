<template>
  <div
    @click="selectDate"
    :class="{ selected: isSelected }"
  >
    {{ date }}
  </div>
</template>

<script>
  export default {
    name: 'day',
    props: ['onSelectDate', 'date', 'isSelected', 'selectedDate'],
    methods: {
      selectDate: function () {
        this.$props.onSelectDate(this.$props.date)
      }
    }
  }
</script>

<style>
</style>
