<template>
  <div class="about">
    <h6>About</h6>
    <div class="user" :class="{ platinum : user.clubMember}">
    Hello, {{ user.firstName }} {{ user.lastName }}
    </div>
    <h4 v-if="!user.phone">No Phone</h4>
    <h4 v-else>Your Phone Number is: {{ user.phone }}</h4>
  </div>

  <div v-for="item in user.lastPurchases" :key="item.id" @click="doSomething(item.id)">{{ item.product }}</div>
</template>

<script setup>
import {reactive} from 'vue'

const user = reactive({
  firstName:'Sam',
  lastName: 'Said',
  phone:'',
  clubMember:true,
  lastPurchases:[{id:1,product:'Audi'},{id:2,product:'BMW'},{id:3,product:'Tesla'}]
})

const doSomething = (id) => console.log(id)
</script>

<style>
.platinum{
  background-color: #868581;
}
</style>