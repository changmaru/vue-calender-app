<template>
  <div class="calendar">
    <div class="day-of-week">
      <div v-for="day in ['Su', 'Mo', 'Tu', 'We', 'Th', 'Fr', 'Sa']" :key="day">
          <Day :date="day" />
      </div>
    </div>

    <div class="dates">
      <div v-for="date in 30" :key="date">
        <Day
          :date="date"
          :selected="date === selectedDate"
          :hasSchedule="hasScheduleList[date - 1]"
          :selectedDate="selectedDate"
          :onSelectDate="onSelectDate"
        />
      </div>
    </div>
  </div>
</template>

<script>
  import Day from "./Day"
  export default {
    name: 'calendar',
    props: ['hasScheduleList', 'onSelectDate', 'selectedDate'],
    components: { Day }
  }
</script>

<style>
.calendar {
  width: 50vw;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.day-of-week {
  border-bottom: 1px solid black;
}

.day-of-week,
.dates {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
}
</style>
