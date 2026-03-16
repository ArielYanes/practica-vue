<script setup>
import { ref } from 'vue'

const productos = ref([
  { nombre: "Laptop", precio: 800, cantidad: 5 },
  { nombre: "Mouse", precio: 20, cantidad: 10 },
  { nombre: "Teclado", precio: 35, cantidad: 7 }
])

function aumentarCantidad(producto){
  producto.cantidad++
}
</script>

<template>
  <div>
    <h2>Lista de Productos</h2>

    <table border="1">
      <tr>
        <th>Producto</th>
        <th>Precio</th>
        <th>Cantidad</th>
        <th>Acción</th>
      </tr>

      <tr v-for="p in productos" :key="p.nombre">
        <td>{{ p.nombre }}</td>
        <td>{{ p.precio }}</td>
        <td>{{ p.cantidad }}</td>
        <td>
          <button @click="aumentarCantidad(p)">
            Agregar
          </button>
        </td>
      </tr>

    </table>
  </div>
</template>

<style>
table{
  margin-top:20px;
  border-collapse: collapse;
}

th, td{
  padding:8px;
  text-align:center;
}

button{
  padding:5px 10px;
}
</style>