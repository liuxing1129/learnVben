<template>
  <div>
    <Card 
      :loading="loadingState" 
      :title="CardTitle" 
      :style="CardStyle"
      hoverable
    >
      <template #cover>
        <img :src="coverImgSrc" :alt="coverImgAlt">
      </template>
      <template #actions>
        <SettingOutlined key="setting"/>
        <EditOutlined key="edit"/>
        <EllipsisOutlined key="ellipsis"/>
      </template>
      <CardMeta :title="CardContentTitle" :description="CardContentDescription">
        <template #avatar>
          <Avatar :src="avatarImgSrc" />
        </template>
      </CardMeta>
    </Card>

    <Button @click="switchLoadingState">切换缓冲状态</Button>
  </div>
</template>

<script setup lang='ts'>
import {Card, Button, CardMeta, Avatar} from 'ant-design-vue';
import {ref} from 'vue';
import type { CSSProperties } from 'vue';
import { SettingOutlined, EditOutlined, EllipsisOutlined } from '@ant-design/icons-vue';
import {Axios as ax} from 'axios';
 
/**
 * 引用的静态资源
 */
import demoImg from '@/assets/images/demo.png';
import avatar from '@/assets/images/logo.png'


/**
 * 组件传值
 */
let CardTitle = 'Card Title'; //父组件调用时传参
let coverImgSrc = demoImg;
let avatarImgSrc = avatar;
let coverImgAlt = '示例图片';
let CardContentTitle = '内容标题';
let CardContentDescription = '内容描述';


/**
 * 加载状态
 */
let loadingState = ref<boolean>(true);


/**
 * 定义卡片样式
 */
const CardStyle:CSSProperties = {
  boxSizing: 'border-box',
  width: '100%',
  height: '100%',
}

/**
 * 切换卡片内容加载状态
 */
const switchLoadingState = ()=>{
  console.log(loadingState.value)
  loadingState.value = !loadingState.value;
}

/**
 * 卡片内容数据获取
 */

const getCardContentAxios = new ax({
  method: 'get',
  url: 'http://localhost:80',
})

const getCardContent = async (item)=>{
  return await getCardContentAxios
}
</script>

<style scoped>

</style>