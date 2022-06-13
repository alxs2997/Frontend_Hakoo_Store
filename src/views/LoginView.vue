<template>

  <div clas="container">
    <br>
    <b-card class="col-md-6 offset-md-3">
      <h3>Login</h3>
      <b-form @submit="onSubmit" @reset="onReset" v-if="show">
          <br>
        <b-form-group id="input-group-1" label="Correo:" label-for="input-1">
          <div class="col-md-6 offset-md-3">
            <b-form-input size="sm" id="input-1" v-model="form.email" type="email" placeholder="Enter email" required>
          </b-form-input>
          </div>
        </b-form-group>
        <br>
        <b-form-group id="input-group-2" label="Ingresa contraseña:" label-for="input-2" description="¿Olvidó su contraseña?">
          <div class="col-md-6 offset-md-3">
            <b-form-input size="sm" class="mr-sm-2" id="input-2" v-model="form.passwordos" type="password" placeholder="Ingrese contraseña" required></b-form-input>
          </div>
        </b-form-group>
        <br>
      <div>  
          <b-button pill variant="danger">Cancelar</b-button>
          |
          <b-button pill variant="primary">Ingresar</b-button>
        </div>
        <br>
        <a href="/Login" @click="form.type=2" v-if="form.type!=2" >Recuper contraseña</a>
        |
        <a href="/Registro" @click="form.type=1" v-if="form.type!=1" >Registrarme</a>
      </b-form>
    </b-card>
    <br>
  </div>

</template>
<script>
import Login from "@/components/Login.vue";

export default {
  components: {
    Login
  },
  data() {
    return {
      form: {
        email: '',
        name: '',
        food: null,
        checked: []
      },
      foods: [{ text: 'Select One', value: null }, 'Carrots', 'Beans', 'Tomatoes', 'Corn'],
      show: true
    }
  },
  methods: {
    onSubmit(event) {
      event.preventDefault()
      alert(JSON.stringify(this.form))
    },
    onReset(event) {
      event.preventDefault()
      // Reset our form values
      this.form.email = ''
      this.form.name = ''
      this.form.food = null
      this.form.checked = []
      // Trick to reset/clear native browser form validation state
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    }
  }

}
</script>

<style scoped>
</style>
