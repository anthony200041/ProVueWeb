<template>
  <div id="app">
    <header>
      <h1>Sistema de Registro de Vehículos</h1>
    </header>
    <main>
      <FormularioRegistro @registro="agregarVehiculo" />
      <ListaVehiculos :vehiculos="vehiculos" />
    </main>
  </div>
</template>

<script>
import FormularioRegistro from './components/FormularioRegistro.vue';
import ListaVehiculos from './components/ListaVehiculos.vue';

export default {
  components: {
    FormularioRegistro,
    ListaVehiculos
  },
  data() {
    return {
      vehiculos: JSON.parse(localStorage.getItem('vehiculos')) || []
    };
  },
  methods: {
    agregarVehiculo(nuevoVehiculo) {
      this.vehiculos.push(nuevoVehiculo);
      this.guardarVehiculos();
    },
    guardarVehiculos() {
      localStorage.setItem('vehiculos', JSON.stringify(this.vehiculos));
    }
  }
};
</script>

<style>
/* Estilos */
/* ... */
</style>
