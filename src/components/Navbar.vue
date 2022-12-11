<script setup lang="ts">
const route = useRoute();
const links = [
  {
    title: "Productivity",
    url: "/prod",
  },
  {
    title: "Social",
    url: "/social",
  },
  {
    title: "Birthdays",
    url: "/birthdays",
  },
  {
    title: "Settings",
    url: "/settings",
  },
];
</script>

<template>
  <nav class="flex flex-col w-1/4">
    <h1><router-link to="/">Calprod</router-link></h1>
    <hr class="pb-4" />
    <template v-for="(link, _) in links" :key="_">
      <div :class="['nav-item', { selected: route.path === link.url }]">
        <router-link :to="link.url" v-if="link.url">
          {{ link.title }}
        </router-link>
        <h2 v-else>{{ link.title }}</h2>
      </div>
    </template>
  </nav>
</template>

<style scoped>
nav {
  padding: 5%;
}

.nav-item {
  @apply text-2xl font-bold py-3 px-2;
  border-radius: 0.75rem;
}

.selected {
  background-color: #f0f0f0;
}
</style>
