<template>
    <div>
        <h6> Home </h6>
    </div>


    <div class="card">
        <h4> {{ productName }} </h4>
        
        <div class="footer">
            <button @click="changeQuantity(-1)"> - </button>
            <h4> {{ product.quantity }} </h4>
            <button @click="changeQuantity(1)"> + </button>
        </div>

        <div class="note">
            <input v-model="product.note" type="text" class="input">
            <p> {{ product.note }} </p>
        </div>

        <div class="total">
            <p>The Price is : {{ total }}</p>
        </div>

    </div>
</template>

<script setup>
import {reactive, computed, watch} from 'vue'

const productName = 'Apple Macbook',
    price = 4000

const product = reactive({
    quantity:0,
    note:''
})

const changeQuantity = (x) => {
    product.quantity += x;
}

const total = computed ( ()=>{
    return product.quantity * price * 1.20
})

watch ( ()=>{
    if (product.quantity > 4) alert ('You went over your head!')
})
</script>


<style>
.card{
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    border-radius: 5px;
    width:150px;
    padding: 15px;
}

.footer{
    display:grid;
    grid-template-columns: auto auto auto;
    text-align: center;

}
.input{
    width:120px;
}
</style>