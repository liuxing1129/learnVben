<template>
  <div> 第一章 </div>
  <v-md-preview :text="text" />
</template>

<script setup lang="ts">
  import { ref } from 'vue';

  const text = ref('');
</script>

<style scoped></style>
