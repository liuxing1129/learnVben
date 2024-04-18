<template>
  <div v-bind="$attrs" :class="preClass">
    <Flex>
      <div
        v-for="(item, index) in contentArray"
        :key="item"
        :style="{...ContentStyle, background: `${index % 2? '#1677ff': '#1666f0'}`}"
      >
        <div v-if="item%4===3">
          <ShowCard></ShowCard>
        </div>
        <div v-if="item%4===2">

        </div>
        <div v-if="item%4===1">

        </div>
        <div v-if="item%4===0">
          <ShowCalendar></ShowCalendar>
        </div>
      </div>
    </Flex>
  </div>
</template>

<script setup lang='ts'>
import type { CSSProperties } from "vue";
import {Flex} from "ant-design-vue"
import '@/styles/common.css'
import ShowCalendar from '@/views/lab/board/components/showCalendar.vue'
import ShowCard from '@/views/lab/board/components/showCard.vue'


const preClass = 'whiteBG'
let contentArray:any[] = [11,22,33,44]
const ContentStyle:CSSProperties = {
  width: '25%',
  padding: '1%',
  // height: '5rem',
  textAlign: 'center',
  justifyContent: 'center',
  margin: "1rem",
}
</script>

<style scoped>

</style>