<script setup lang="ts">
import { ref,computed } from "vue";
// 目标：computed 的类型约束

// 方式：computed会自动推导，无需配置，也不应该配置
const count=ref(10)

const doubleCount=computed(()=>{
  return count.value*2
})

console.log(doubleCount.value);

// 练习题
type Goods = {
  id:string,
  name:string,
  price:number,
}

const goodsList=ref<Goods[]>([])
goodsList.value=[
  {id:'1001',name:'男鞋',price:550},
  {id:'1002',name:'女鞋',price:850},
  {id:'1003',name:'衬衫',price:450},
]

const newList=computed(()=>{
  return goodsList.value.filter(item=>{
    return item.price>500
    }
  )
})
</script>

<template>
  <ul>
    <li v-for="item in newList" :key="item.id">
    {{ item.name }}---{{ item.price }}
    </li>
  </ul>
</template>

<style scoped>

</style>
