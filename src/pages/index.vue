<script setup lang="ts" generic="T extends any, O extends any">
defineOptions({
  name: 'IndexPage',
})
const subTitle = import.meta.env.VITE_APP_SUBTITLE
const mail = import.meta.env.VITE_APP_EMAIL
// const router = useRouter()
// const go = () => {
//   if (name)
//     router.push(`/hi/${encodeURIComponent(name.value)}`)
// }
</script>

<template>
  <div>
    <section flex items-center justify-between>
      <img src="/home.jpg" alt="home" w="3/4">
      <div text-right>
        <h3 text-2xl mb-3>
          Summer
        </h3>
        <p>
          {{ subTitle }}
        </p>
        <i text-sm>
          {{ mail }}
        </i>
      </div>
    </section>
  </div>
</template>
