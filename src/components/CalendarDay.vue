<script setup lang="ts">
import type { Dayjs } from "dayjs";
const props = defineProps<{ date: Dayjs }>();
</script>

<template>
  <div>
    {{ props.date.date() }}
    <!--
    andrew wtf did you do
    why is your code so shitty
   -->
  </div>
</template>
