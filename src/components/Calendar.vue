<template>
  <div class="grid">
    <div class="day-of-week">
      <div>Su</div>
      <div>Mo</div>
      <div>Tu</div>
      <div>We</div>
      <div>Th</div>
      <div>Fr</div>
      <div>Sa</div>
    </div>

    <div class="date-grid">
      <div v-for="date in 30">
        <Day :date="date"></Day>
      </div>
    </div>

  </div>
</template>

<script>
  import Day from "./Day"
  export default {
    name: 'calender',
    components: { Day }
  }
</script>

<style>
/* The grid */
.grid {
  width: 50vw;
}

.day-of-week,
.date-grid {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
}
</style>
