<template>
  <div class="flex h-screen items-center justify-center bg-gray-100">
    <GoogleLogin :callback="callback" prompt auto-login />
  </div>
</template>

<script setup lang="ts">
import { GoogleLogin } from "vue3-google-login";
import { useAuthStore } from "@/store";
const authStore = useAuthStore();

const callback = async (googleResponse: any) => {
  await authStore.login(googleResponse.credential);
};
</script>
