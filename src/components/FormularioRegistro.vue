<template>
  <form @submit.prevent="registrarVehiculo">
    <label for="marca">Marca:</label>
    <input type="text" id="marca" v-model="marca" required><br><br>

    <label for="modelo">Modelo:</label>
    <input type="text" id="modelo" v-model="modelo" required><br><br>

    <button type="submit">Registrar Vehículo</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      marca: '',
      modelo: ''
    };
  },
  methods: {
    registrarVehiculo() {
      const nuevoVehiculo = {
        marca: this.marca,
        modelo: this.modelo
      };
      this.$emit('registro', nuevoVehiculo);
      this.marca = '';
      this.modelo = '';
    }
  }
};
</script>
