<template>
  <div class="date-container">
    <div
      v-if="selected || hasSchedule"
      class="marker"
      :class="{ selected, 'has-schedule': hasSchedule }" />
    <div class="date" @click="selectDate"> {{ date }} </div>
  </div>
</template>

<script>
  export default {
    name: 'day',
    props: ['onSelectDate', 'date', 'selected', 'hasSchedule', 'selectedDate'],
    methods: {
      selectDate: function () {
        if (!this.$props.onSelectDate) return
        this.$props.onSelectDate(this.$props.date)
      }
    }
  }
</script>

<style>
.date-container {
  width: 6.25vw;
  height: 5vw;
  display: flex;
  align-items: center;
  justify-content: center;
}

.marker {
  position: absolute;
  width: 3vw;
  height: 3vw;
  border-radius: 50%;
  z-index: 0;
}

.has-schedule {
  background: pink;
}

.selected {
  background: orange;
}

.date {
  user-select: none;
  z-index: 1;
}
</style>
