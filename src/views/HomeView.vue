<template>
    <div>
        <h1> Home </h1>
    </div>

    <div class="product">
        <h3> Product A</h3>
        <h3> {{ productTitle }}</h3>
        <button @click="decreaseCounter">-</button>
        <h3> {{ product.counter }} </h3>
        <button @click="increaseCounter">+</button>
        <input v-model="product.note" type="text" placeholder="add note">
        <p>{{ product.note }}</p>
    </div>
</template>

<script setup>
import {reactive} from 'vue'

const productTitle = 'My Product'

const product = reactive({
    counter:0,
    note:'your request'
})
const increaseCounter = () => product.counter++
const decreaseCounter = () => product.counter--
</script>


<style>
.product{
    border: 1px solid lightblue;
    margin-top: 20px;
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    padding: 2px 16px;
    width:25%;
    text-align: center;
}
</style>