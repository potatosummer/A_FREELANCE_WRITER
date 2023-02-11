<script setup lang="ts">
const headerList = [
  'Home',
  'Posts',
  'About',
]
</script>

<template>
  <div>
    <div flex justify-around>
      <h2 text-2rem>
        Summer
      </h2>
      <div flex align-base mt-2>
        <div
          v-for="name of headerList"
          :key="name"
          mr
        >
          <RouterLink hover-border-b-3 pb-2 :to="{ name }">
            {{ name }}
          </RouterLink>
        </div>
      </div>
    </div>
  </div>
</template>
