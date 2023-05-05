<template>
  <Navbar :on-theme-change="onThemeChange" />
  <div class="flex-1 flex justify-center items-center gap-20">
    <div class="w-[40%] flex flex-col gap-10">
      <div class="text-6xl font-bold text-blue-500">
        Backup your data and restore it in one place
      </div>
      <div class="text-xl text-gray-400">
        Support backup MySQL/PostgreSQL/Redis/MongoDB to any S3 compatible storages
      </div>
      <div class="flex gap-2">
        <a
          href="https://github.com/long2ice/databack.git"
          target="_blank"
          class="flex border p-3 items-center gap-2 rounded-md hover:bg-gray-100"
        >
          <AkGithubFill />
          View on Github
        </a>
        <a
          href="https://demo.databack.dev"
          target="_blank"
          class="flex border p-3 items-center gap-2 rounded-md hover:bg-gray-100"
        >
          <AnFilledHeart class="text-pink-500" />
          Try the demo
        </a>
        <a
          href="https://pro.databack.dev/login"
          target="_blank"
          class="flex border p-3 items-center gap-2 rounded-md hover:bg-gray-100"
        >
          <McVip1Fill class="text-orange-500" />
          Try the pro version
        </a>
      </div>
    </div>
    <div class="w-[60%]">
      <img :src="screenshot" class="rounded-md shadow-md" alt="home" />
    </div>
  </div>
</template>
<script setup lang="ts">
import Navbar from '@/components/Navbar.vue'
import { ref } from 'vue'
const onThemeChange = (mode: boolean) => {
  if (!mode) {
    screenshot.value = '/screenshot-light.png'
  } else {
    screenshot.value = '/screenshot-dark.png'
  }
}
const screenshot = ref()
</script>
<style scoped></style>
