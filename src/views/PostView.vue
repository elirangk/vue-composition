<template>
    <p>This is post {{ $route.params.id }}</p>
    <button @click="showPostId">Show Post Id</button>
<br>
<button @click="goHome" style="color:#00bd7e">Go Home In 2 Seconds</button>
</template>

<script setup>
import { useRouter, useRoute } from 'vue-router'
const router = useRouter()
const route = useRoute()

const showPostId = () =>{
    alert(`This Post Id is ${ route.params.id}`)
}

const goHome =() =>{
    setTimeout(() => {
        router.push('/')
    }, 2000);
}
</script>