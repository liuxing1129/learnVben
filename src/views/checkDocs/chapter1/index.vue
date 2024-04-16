<template>
  <div v-bind="$attrs" class="MarkdownContainer">
    <MarkdownViewer :value="text" />
  </div>
</template>

<script setup lang="ts">
import '/@/views/checkDocs/styles/common.css'
import {ref} from 'vue';
import md from "./工时系统服务.md?raw"
import { MarkdownViewer } from '@/components/Markdown';
const text = ref(md)
</script>

<style scoped></style>
