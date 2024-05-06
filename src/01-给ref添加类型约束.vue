<script setup lang="ts">
import { ref } from "vue";
// 1. 给简单类型添加类型约束
// 方式1：使用类型推导
const count = ref(100)
console.log(count.value);

// 方式2：手动指定类型，使用泛型
const msg=ref<string>('I am string')
console.log(msg.value);

// 2. 给复杂类型添加类型约束
const year = ref<number|string>(2024)
year.value='2025'
console.log(year.value);

// 3. 思考题
type Goods = {
  id: string,
  name: string,
  price: number
}

const list = ref<Goods[]>([])
list.value=[
    {
    id: '1001',
    name: '男士卫衣',
    price: 100,
  },
  {
    id: '1002',
    name: '男士裤子',
    price: 200,
  }
]



</script>

<template>
  <ul>
    <li  v-for="item in list" :key="item.id">
      {{ item.name }}---{{item.price}}
    </li>
  </ul>
</template>

<style scoped>

</style>
