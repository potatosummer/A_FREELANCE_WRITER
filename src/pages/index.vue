<script setup lang="ts" generic="T extends any, O extends any">
defineOptions({
  name: 'IndexPage',
})

// const router = useRouter()
// const go = () => {
//   if (name)
//     router.push(`/hi/${encodeURIComponent(name.value)}`)
// }
</script>

<template>
  <div>
    <section flex items-center justify-between>
      <img src="/home.jpg" alt="home" w="4/5">
      <p text-center>
        寫字的ライター
      </p>
    </section>
  </div>
</template>
