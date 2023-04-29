<template>
  <div class="navbar bg-base-100">
    <div class="navbar-start">
      <a class="btn btn-ghost normal-case text-2xl">Databack</a>
    </div>
    <div class="navbar-center font-bold">
      <ul class="menu menu-horizontal px-1">
        <li><a href="https://docs.databack.dev" target="_blank">Documentation (writing)</a></li>
        <li><a>Pricing</a></li>
        <li><a href="mailto:long2ice@gmail.com">Contact</a></li>
      </ul>
    </div>
    <div class="navbar-end">
      <button class="btn-ghost btn">
        <label class="swap-rotate swap">
          <input type="checkbox" data-toggle-theme="light,dark" v-model="mode" />
          <MdOutlinedWbSunny class="swap-off text-2xl" />
          <CoMoon class="swap-on text-2xl" />
        </label>
      </button>
      <a
        href="https://github.com/long2ice/databack.git"
        target="_blank"
        class="btn btn-ghost text-2xl"
      >
        <AkGithubFill />
      </a>
    </div>
  </div>
</template>

<style scoped></style>
<script setup lang="ts">
import { onMounted, ref, watch } from 'vue'
import { themeChange } from 'theme-change'
const mode = ref(false)
const props = defineProps({
  onThemeChange: {
    type: Function,
    required: true
  }
})
onMounted(() => {
  themeChange(mode.value)
  props.onThemeChange(mode.value)
})
watch(mode, (value) => {
  props.onThemeChange(value)
})
</script>
