<script setup lang="ts">
import { articles } from '~/sources/articles'
defineOptions({
  name: 'Posts',
})
const reverse = ref(false)
const keywords = ref('')
const toggleList = () => reverse.value = !reverse.value
const sortList = computed(() => {
  return articles.sort((a, b) => {
    const aT = new Date(a.createdDate).getTime()
    const bT = new Date(b.createdDate).getTime()
    return reverse.value ? aT - bT : bT - aT
  }).filter(item => !keywords.value || item.tags.includes(keywords.value))
})
const filterArticle = (name: string) => {
  if (name !== keywords.value)
    keywords.value = name
  else
    keywords.value = ''
}
const filterTags = computed(() => {
  const tags = articles.map(item => item.tags[0])
  return tags.filter((item, index) => tags.indexOf(item) === index)
})
</script>

<template>
  <div text-left>
    <h3 text-xl border="l-4 teal-600" pl-3 mb-6>
      Articles
    </h3>
    <div mb-4 flex items-center>
      <div>
        <button icon-btn block disabled:text-teal-600 disabled:cursor-default :disabled="reverse" @click="toggleList()">
          <div i-carbon-caret-up />
        </button>
        <button icon-btn block disabled:text-teal-600 disabled:cursor-default :disabled="!reverse" @click="toggleList()">
          <div i-carbon-caret-down />
        </button>
      </div>
      <button
        v-for="item of filterTags" :key="item"
        :class="item === keywords && 'text-gray-300'"
        ml-2 text-gray-400 hover:text-gray-300 font-mPlus
        @click="filterArticle(item)"
      >
        {{ item }}
      </button>
    </div>
    <div v-for="({ title, createdDate, tags, redirectUrl }, index) of sortList" :key="index" mb-3>
      <TheArticle
        :title="title"
        :created-date="createdDate"
        :tags="tags"
        :redirect-url="redirectUrl"
      />
    </div>
  </div>
</template>
