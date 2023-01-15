<script setup>
import { onMounted, computed } from "vue";
import { useUserStore } from "@/stores/user";


import Logo from "@/components/layouts/navbar/Logo.vue";
import NavLinks from "@/components/layouts/navbar/NavLinks.vue";
import UserInfo from "@/components/layouts/navbar/UserInfo.vue";
import AuthButton from "@/components/layouts/navbar/AuthButton.vue";

const userStore = useUserStore()
const user = computed(() => userStore.getUser)
const isLoggedIn = computed(() => userStore.isLoggedIn)

onMounted(() => {
  userStore.fetchUser()
})


</script>

<template>
  <nav class="bg-white border-gray-200 px-2 sm:px-4 py-2.5 rounded dark:bg-gray-800">
    <div class="container flex flex-wrap items-center justify-between mx-auto my-2">
      <Logo />
      <NavLinks />
      <UserInfo v-if="isLoggedIn" :user="user.data" />
      <AuthButton v-else />
    </div>
  </nav>
</template>
