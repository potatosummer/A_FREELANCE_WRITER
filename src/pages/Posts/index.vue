<script setup lang="ts">
import { articles } from '~/sources/articles'
defineOptions({
  name: 'Posts',
})
const list = articles
// const router = useRouter()
// const route = useRoute()
</script>

<template>
  <div text-left>
    <h3 text-xl border="l-4 teal-600" pl-3 mb-6>
      Articles
    </h3>
    <div v-for="({ title, createdDate, tags, redirectUrl }, index) of list" :key="index" mb-4>
      <TheArticle
        :title="title"
        :created-date="createdDate"
        :tags="tags"
        :redirect-url="redirectUrl"
      />
    </div>
  </div>
</template>
