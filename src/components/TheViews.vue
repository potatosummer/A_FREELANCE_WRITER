<script setup lang="ts" generic="T extends any, O extends any">
defineOptions({
  name: 'TheViews',
})
const url = import.meta.env.VITE_APP_INSTAGRAM
</script>

<template>
  <nav text-xl flex items-start>
    <button icon-btn mr-2 @click="toggleDark()">
      <div dark:i-carbon-moon i-carbon-sun />
    </button>
    <a :href="url" target="_blank">
      <div i-carbon-logo-instagram block mr-auto hover-text-teal-600 />
    </a>
  </nav>
</template>
