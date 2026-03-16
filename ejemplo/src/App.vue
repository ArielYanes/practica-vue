<script setup>
import { ref } from 'vue'
import MiComponente from './components/mi.vue'
import Usuarios from './components/Usuarios.vue'
import prooductos from './components/prooductos.vue'

const contador = ref(0)

function aumentar(){
  contador.value++
}
</script>

<template>
  <div class="contenedor">
    <h1>Mi primera app en Vue</h1>

    <p>Contador: {{ contador }}</p>

    <button @click="aumentar">
      Aumentar
    </button>

    <hr>

    <h2>Componente</h2>
    <MiComponente />
  </div>

  <hr>
    <div>
      <h1>Sistemas de Usuario</h1>

      <Usuarios />

    </div>

    <div>
      <h1>Sistemas de producto</h1>

      <prooductos />

    </div>

</template>

<style>
.contenedor{
  text-align:center;
  margin-top:100px;
  font-family: Arial;
}

button{
  padding:10px 20px;
  font-size:16px;
  cursor:pointer;
}
</style>