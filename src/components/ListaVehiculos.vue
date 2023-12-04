<template>
    <div>
      <h2>Vehículos Registrados:</h2>
      <ul>
        <li v-for="(vehiculo, index) in vehiculos" :key="index">
          <strong>Marca:</strong> {{ vehiculo.marca }}, <strong>Modelo:</strong> {{ vehiculo.modelo }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      vehiculos: {
        type: Array,
        default: () => []
      }
    }
  };
  </script>
  