<template>
  <div class="outer-date">
    <div
      @click="selectDate"
      :class="{ selected, 'inner-date': true, 'has-schedule': hasSchedule }"
    >
      <div class="date"> {{ date }} </div>
    </div>
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
.outer-date {
  width: 6.25vw;
  height: 5vw;
  line-height: 6.25vw;
  text-align: center;
  user-select: none;
}

.inner-date {
  width: 3vw;
  height: 3vw;
  margin: 1vw 1.625vw;
}

.has-schedule {
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
