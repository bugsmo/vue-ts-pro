<script setup lang="ts">
import { onMounted, ref } from 'vue';


// 目标：为模板引用添加类型约束
// 需要联合 null 类型，防止页面未渲染之前不存在input标签而报错
const inputRef=ref<HTMLInputElement|null>(null)

onMounted(()=>{
  // 自动添加了 ? ，是防止报错
  inputRef.value?.focus()
})

// 练习题
const aRef=ref<HTMLAnchorElement|null>(null)
onMounted(()=>{
  console.log(aRef.value?.href);
  
})

</script>

<template>
<input type="text" ref="inputRef">
<a href="https://www.baidu.com" ref="aRef">百度</a>
</template>

<style scoped>

</style>
