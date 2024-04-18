<template>
  <div
    :style="{...calendarContainerStyles}"  
  >
    <Calendar 
      v-modal:value="calendarValue"
      :fullscreen="false"
    />
  </div>
</template>

<script setup lang='ts'>
import { Calendar } from 'ant-design-vue';
import { Dayjs } from 'dayjs';
import {ref} from 'vue';
import type { CSSProperties } from 'vue';

let calendarContainerStyles:CSSProperties = {
  // padding: '1rem',
}

let calendarValue = ref<Dayjs>();

</script>

<style scoped>

</style>
