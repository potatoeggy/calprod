<script setup lang="ts"></script>

<template>
  <Navbar />
  <main class="grow p-10">
    <router-view />
  </main>
</template>

<style>
body {
  display: flex;
  height: 100vh;
  width: 100vw;
}
</style>
