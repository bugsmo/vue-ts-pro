<script setup lang="ts">
import { reactive } from "vue";
// 1. 给 reactive 添加类型约束
// 方式1：使用类型推导
const form = reactive({
  username: 'test',
  password:'123123',
})

console.log(form);


// 方式2：手动指定类型
type LoginForm = {
  username: string,
  password: string,
  isGreed?: boolean,
}

const login: LoginForm=reactive({
  username:'test1',
  password:"123321",
})

login.isGreed=true

console.log(login);

// 思考题
type address = {
    username: string,
    address:string,
    phone:string,
    gender?:'男'|'女'
}

const myAddress: address=reactive(
  {
    username: 'you',
    address: 'cn',
    phone: '1234566778',
  }
)

myAddress.gender='男'

console.log(myAddress);



</script>

<template>
</template>

<style scoped>

</style>
