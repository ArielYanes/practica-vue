<script setup>
import { ref, computed } from 'vue'

const usuarios = ref([
  {
    nombre: "Juan",
    apellido: "Pérez",
    usuario: "jperez",
    rol: "Administrador",
    estado: "activo"
  },
  {
    nombre: "Ana",
    apellido: "Martínez",
    usuario: "amartinez",
    rol: "Usuario",
    estado: "activo"
  },
  {
    nombre: "Carlos",
    apellido: "Gómez",
    usuario: "cgomez",
    rol: "Editor",
    estado: "activo"
  }
])

function cambiarEstado(user){
  if(user.estado === "activo"){
    user.estado = "inactivo"
  }else{
    user.estado = "activo"
  }
}

const usuariosActivos = computed(()=>{
  return usuarios.value.filter(u => u.estado === "activo")
})
</script>

<template>
  <div>
    <h2>Lista de Usuarios</h2>

    <table border="1">
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Apellido</th>
          <th>Usuario</th>
          <th>Rol</th>
          <th>Estado</th>
          <th>Acción</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="user in usuariosActivos" :key="user.usuario">
          <td>{{ user.nombre }}</td>
          <td>{{ user.apellido }}</td>
          <td>{{ user.usuario }}</td>
          <td>{{ user.rol }}</td>
          <td>{{ user.estado }}</td>
          <td>
            <button @click="cambiarEstado(user)">
              Cambiar estado
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style>
table{
  border-collapse: collapse;
  width: 100%;
}

th, td{
  padding: 8px;
  text-align: center;
}

th{
  background-color: #eee;
}

button{
  padding: 5px 10px;
  cursor: pointer;
}
</style>