<template>
  <h1>Ejercicio 03: To Do list + Cont</h1>
  <h2>Tareas {{ counter }}</h2>
  <input v-model="msg">
  <button @click="add">Añadir</button>

  <h2 class="mt-3">Mis Tareas</h2>
  <ul class="list-group mt-2">
    <li class="list-group-item" v-for="(item, index) in tareas" :key="index">
      {{ item }}
      <button @click="delet(index)">Eliminar </button>
    </li>
  </ul>
</template>

  <script setup>
    import { ref } from "vue";

  const tareas = ref([]);
  const counter = ref(0);
  var msg ="";
  const add = () => {
      tareas.value.push(msg);
      counter.value++;
      msg ="";

  };

  const delet = (index) => {
  var removed = tareas.value.splice(index, 1);
  for (var i = 0; i < counter.value; i++) {
    tareas[i]= removed[i];
  }
  counter.value--;
   
  };

  </script>

  <style>
    #app {
      font-family: Avenir, Helvetica, Arial, sans-serif;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      text-align: center;
      color: #2c3e50;
      margin-top: 60px;
    }
  </style>
