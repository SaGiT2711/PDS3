<template>
  <form @submit="validarFormulario">
    <p v-if="errors.length">
      <b>Por favor verificar</b>
    <ul>
      <li v-for="(error, index) in errors" :key="index" class="text-danger">{{ error }}</li>
    </ul>
    </p>
    <p>Nombre</p>
    <input type="text" class="form-control" id="name" v-model="name">
    <p>Email</p>
    <input type="email" class="form-control" id="email" v-model="email">
    <p>Asunto</p>
    <input type="text" class="form-control" id="asunto" v-model="asunto">
    <p>Mensaje</p>
    <textarea class="form-control" id="mensaje" v-model="mensaje" rows="5"></textarea>
    <br>
    <button type="submit" class="btn btn-primary">Enviar</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      errors: [],
      email: null,
      asunto: null,
      name: null,
      mensaje: null,
    }
  },
  methods: {
    validarFormulario: function (e) {
      if (this.name && this.email && this.asunto !== null && this.mensaje) {
        return true;
      }

      this.errors = [];

      if (!this.name) {
        this.errors.push('ingresa tu Nombre.');
      }
      if (!this.email) {
        this.errors.push('ingresa tu Email.');
      }
      if (!this.asunto) {
        this.errors.push('Asunto.');
      }
      if (!this.mensaje) {
        this.errors.push('Mensaje.');
      }

      e.preventDefault();
    },

  }
}
</script>