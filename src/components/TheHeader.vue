<script setup lang="ts">
const headerList = [
  {
    name: 'Home',
    url: '/',
  },
  {
    name: 'Posts',
    url: '/Posts',
  },
]
</script>

<template>
  <div>
    <div flex justify-between>
      <h2 text-2rem>
        Summer
      </h2>
      <div flex m="t-3">
        <div
          v-for="{ name, url } of headerList"
          :key="name"
          mr
        >
          <RouterLink hover-border-b-3 hover-border-teal-600 pb-2 :to="url">
            {{ name }}
          </RouterLink>
        </div>
        <TheViews ml />
      </div>
    </div>
  </div>
</template>

<style scoped>
  .router-link-exact-active {
    --un-border-opacity: 1;
    border-bottom: 3px solid rgba(13, 148, 136, var(--un-border-opacity));
  }
</style>
