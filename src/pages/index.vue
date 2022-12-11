<route lang="json">
{
  "meta": {
    "title": "Home"
  }
}
</route>

<script setup>
import Calendar from "../components/Calendar.vue";
useHead({
  title: "Home",
});
</script>

<template>
  <Calendar />
</template>
