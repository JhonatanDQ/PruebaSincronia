<script setup>
import {ref} from 'vue';

const users = ref([])

function loadData(){
    fetch('https://jsonplaceholder.typicode.com/users')
  .then(function(response){ 
    return response.json()})
  .then(function (data) { 
    console.log(data)
    users.value = data
})
  }
</script>



<template>
    <div 
        v-for="users in users" :key="users.id"
    class="bg-slate-300 mb-1"> 
    {{ users.name }}
</div> 
    <button @click="loadData">
        cargar info 
    </button>
</template>
