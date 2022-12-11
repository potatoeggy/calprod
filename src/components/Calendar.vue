<script setup lang="ts">
import dayjs from "dayjs";
import IconLeftArrow from "../assets/icon-left.svg?component";
import IconRightArrow from "../assets/icon-right.svg?component";

const firstDayOfMonth = dayjs("2022-09-01");

// this is just a list comprehension that makes
// a list of dayjs objects for each day
const datesInMonth = Array.from(
  { length: firstDayOfMonth.daysInMonth() },
  (_, i) => firstDayOfMonth.add(i, "day")
);

const weekdays = [
  "Sunday",
  "Monday",
  "Tuesday",
  "Wednesday",
  "Thursday",
  "Friday",
  "Saturday",
];

const truncatedWeekdays = weekdays.map((s) => s.substring(0, 3));
</script>

<template>
  <div class="rounded-xl container h-full">
    <!-- i'm sorry for the div soup -->
    <div
      class="flex flex-col align-center h-full bg-white rounded-xl px-12 pb-12"
    >
      <div class="flex pt-8 justify-center items-center">
        <button
          type="button"
          class="rounded-full w-12 h-12 flex items-center justify-center month-select-button disabled"
        >
          <IconLeftArrow />
        </button>
        <h1 class="text-3xl font-bold px-8">September 2022</h1>
        <button
          type="button"
          class="rounded-full w-12 h-12 flex items-center justify-center month-select-button"
        >
          <IconRightArrow />
        </button>
      </div>
      <div class="grid grid-rows-5 grid-cols-7 gap-x-10 gap-y-5 pb-20 grow">
        <div
          class="flex flex-col-reverse"
          v-for="(day, _) in truncatedWeekdays"
          :key="_"
        >
          <h2 class="text-lg font-semibold text-center">
            {{ day }}
          </h2>
        </div>
        <CalendarDay v-for="(day, _) in datesInMonth" :key="_" :date="day" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  background: linear-gradient(to right, #75c5ff, #1c69ff);
  padding: 0.1rem;
}

.month-select-button {
  background: #e9effd;
}

.month-select-button.disabled {
  background: #f5f3ff;
}
</style>
