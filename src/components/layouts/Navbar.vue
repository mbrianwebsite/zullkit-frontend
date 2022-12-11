<script setup>
import Logo from "./navbar/logo.vue";
import NavLinks from "./navbar/NavLinks.vue";
import UserInfo from "./navbar/UserInfo.vue";
</script>

<template>
  <nav class="bg-white border-gray-200 px-2 sm:px-4 py-2.5 rounded dark:bg-gray-800">
    <div class="container flex flex-wrap items-center justify-between mx-auto my-2">
      <Logo />
      <NavLinks />
      <UserInfo />
    </div>
  </nav>
</template>
