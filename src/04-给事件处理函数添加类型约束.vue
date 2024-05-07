<script setup lang="ts">

// 目标：为事件处理函数添加类型约束

// 给事件形参标注为 Event 类型，获得 input 标签的智能提示
const inputChange=(e:Event)=>{
  // 使用 as 断言获得更进一步的提示
  console.log((e.target as HTMLInputElement).value);
}

// 练习题
const buttonClick=(e:Event)=>{
  console.log((e.target as HTMLButtonElement));
}

</script>

<template>
<input type="text" @change="inputChange">
<button @click="buttonClick">按钮</button>
</template>

<style scoped>

</style>
