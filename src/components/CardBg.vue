<script setup lang="ts">
const { title } = defineProps<{
  title: string;
}>();
</script>

<template>
  <header class="bg-white shadow mb-5">
    <div class="mx-auto max-w-7xl py-4 px-4 sm:px-6 lg:px-8">
      <h1 class="text-3xl font-bold leading-tight text-gray-900">
        {{ title }}
      </h1>
    </div>
  </header>
  <section class="bg-white shadow">
    <div class="mx-auto max-w-7xl py-6 px-4 sm:px-6 lg:px-8">
      <slot />
    </div>
  </section>
</template>
