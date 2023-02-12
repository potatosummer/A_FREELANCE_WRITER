<script setup lang="ts">
defineOptions({
  name: 'Posts',
})
const router = useRouter()
</script>

<template>
  <div>
    <h3 text="xl">
      Not Found
    </h3>
    <button
      class="btn m-3 text-sm mt-8"
      @click="router.replace('/')"
    >
      Home
    </button>
  </div>
</template>
