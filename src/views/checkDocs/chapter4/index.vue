<template>
  <div v-bind="$attrs" class="MarkdownContainer">
    <MarkdownViewer :value="text" />
  </div>
</template>

<script setup lang="ts">
import '/@/views/checkDocs/styles/common.css'
import {ref} from 'vue';
// import md from ''
import { MarkdownViewer } from '@/components/Markdown';
const text = ref('## 二级标题')
</script>

<style scoped>

</style>
