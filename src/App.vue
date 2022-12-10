<script setup>
import { RouterView } from "vue-router";
import Navbar from "./components/layouts/Navbar.vue";
</script>

<template>
  <!-- <header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
    </nav>
  </header> -->
  <Navbar />
  <RouterView />
</template>

<style>
@import "@/assets/css/styles.css";
</style>
