<template>
  <div
    @click="selectDate"
    :class="{ selected: isSelected, 'outer-date': true, hasSchedule: hasSchedule }"
  >
    <div class="date"> {{ date }} </div>
  </div>
</template>

<script>
  export default {
    name: 'day',
    props: ['onSelectDate', 'date', 'isSelected', 'hasSchedule', 'selectedDate'],
    methods: {
      selectDate: function () {
        this.$props.onSelectDate(this.$props.date)
      }
    }
  }
</script>

<style>
.outer-date {
  width: 3vw;
  height: 3vw;
  margin: 1vw 1.625vw;
}

.hasSchedule {
  border-radius: 50%;
  background: pink;
}

.selected {
  border-radius: 50%;
  background: orange;
}

.date {
  height: 100%;
  transform: translateY(-50%);
}
</style>
