<script setup>
import "../src/assets/main.css";
import NavBar from "./components/NavBar.vue";
</script>

<template>
  <template v-if="$route.name == 'admin'">
    <router-view></router-view>
  </template>
  <template v-else>
    <header>
      <NavBar />
    </header>
    <router-view></router-view>
  </template>
</template>

<style>
html {
  background-color: #c4c4c4;
}
</style>
