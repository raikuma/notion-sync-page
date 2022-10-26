<script setup>
import { NotionRenderer, getPageBlocks, useGetPageBlocks } from "vue3-notion"
import { ref, onMounted } from "vue"

const data = ref()

onMounted(async () => {
  data.value = await getPageBlocks("6321d90d4abc4731b48f77d147958d73")
})
</script>

<template>
  <NotionRenderer v-if="data" :blockMap="data" fullPage />
</template>

<style>
@import "vue3-notion/dist/style.css"; /* optional Notion-like styles */
@import "prismjs/themes/prism.css";
@import "katex/dist/katex.min.css";
</style>