<script setup>
import { ref } from 'vue';
const products = ref(null);
fetch(' https://jsonplaceholder.typicode.com/posts')
    .then(response => response.json())
    .then(data => products.value = data);
</script>

<template>
    <div class="card m-3" style="background-color: hotpink;">
        <h1 class="card-header text-center">Vue 3 Datos obtenidos de la API</h1>
        <div class="card-body">
            <div v-if="products">
                <h2>Productos</h2>
                <ul class="mb-0">
                </ul>
                <table>
                 <tr>
    <th>userId</th>
    <th>id</th>
    <th>title</th>
    <th>body</th>
  </tr>
  <tr v-for="product in products" :key="product.id">
    <td>{{product.userId}}</td>
    <td>{{product.id}}</td>
    <td>{{product.title}}</td>
    <td>{{product.body}}</td>
  </tr>
 
                </table>
            </div>
            <div v-if="!products" class="text-center">
                <div class="spinner-border spinner-border-sm"></div>
            </div>
        </div>
    </div>
</template>