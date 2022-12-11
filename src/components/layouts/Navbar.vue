<script setup>
import Logo from "@/components/layouts/navbar/logo.vue";
import NavLinks from "@/components/layouts/navbar/NavLinks.vue";
import UserInfo from "@/components/layouts/navbar/UserInfo.vue";
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
