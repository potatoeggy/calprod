<script setup lang="ts">
import dayjs from "dayjs";

interface Birthday {
  name: string;
  date: dayjs.Dayjs;
}

const birthdays: Birthday[] = [
  {
    name: "Eggy",
    date: dayjs("2021-09-01"),
  },
];
</script>

<template>
  <CardBg title="Upcoming">
    <p>list of upcoming birthdays and all birthdays</p>
    <ul>
      <li v-for="birthday in birthdays" :key="birthday.date.toISOString()">
        {{ birthday.name }} - {{ birthday.date.format("MMMM D") }}
      </li>
    </ul>
  </CardBg>
</template>
