<script setup lang="ts">
const { createdDate, title, tags, redirectUrl } = defineProps<{
  createdDate: string // 創建日期
  title: string // 文章標題
  tags: string[] // 標籤
  redirectUrl: string // 文章網址
}>()
defineOptions({
  name: 'TheArticle',
})
</script>

<template>
  <article>
    <a :href="redirectUrl" :alt="title" target="_blank">
      <h2 text-base hover-text-gray-400 transition duration-300 font-mPlus>
        {{ title }}
      </h2>
    </a>
    <div flex text-sm mt-1>
      <span text-gray-400>
        {{ createdDate }}
      </span>
      <span v-for="tag of tags" :key="tag" ml-3 tag font-mPlus>
        {{ tag }}
      </span>
    </div>
  </article>
</template>
