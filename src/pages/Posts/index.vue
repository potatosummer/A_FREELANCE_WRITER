<script setup lang="ts">
defineOptions({
  name: 'Posts',
})
// const router = useRouter()
// const route = useRoute()
</script>

<template>
  <div text-left>
    <h3 text-xl border="right teal-600 2">
      Articles
    </h3>
    <div v-for="v of 10" :key="v">
      {{ v }}
    </div>
  </div>
</template>
