<script setup>
import { ref } from 'vue'
const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])

// TODO: Add Code Here
function deleteitem(index){
    items.value.splice(index,1)
}
//initialise item 1st
const newitem=ref('')

function additem(){
    if (newitem.value.trim() !== '') {
        items.value.push(newitem.value)
        newitem.value = ''
}
}

</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
     <ul>
        <li v-for="(item, index) in items" :key="index">
            {{ item }}
            <button v-on:click="deleteitem(index)">Delete</button>
        </li>
     </ul>
     <input type="text" v-model="newitem">
     <button v-on:click="additem"> Add!</button>

   
</template>
