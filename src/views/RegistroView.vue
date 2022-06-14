<template>
    <div>
        <b-card class="col-md-6 offset-md-3">
            <br>
            <form v-on:submit.prevent="onSubmit" class="row g-3 needs-validation" novalidate>

                <h3>Formulario De Registro</h3>
                <p>Para seguir las tendencias en moda...</p>
                <div class="col-md-4">
                    <div class="form-outline">
                        <input type="text" class="form-control" v-model="nombre" id="validationCustom01" placeholder="Nombres"
                            required />
                        <div class="valid-feedback">Looks good!</div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="form-outline">
                        <input type="text" class="form-control" v-model="apellido" id="validationCustom02" placeholder="Apellidos"
                            required />
                        <div class="valid-feedback">Looks good!</div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="input-group form-outline">
                        <span class="input-group-text" id="inputGroupPrepend">@</span>
                        <input type="text" class="form-control" v-model="nombre_usuario" id="validationCustomUsername"
                            aria-describedby="inputGroupPrepend" placeholder="Username" required />
                        <div class="invalid-feedback">Please choose a username.</div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="form-outline">
                        <input type="text" class="form-control" v-model="correo" id="validationCustom02" placeholder="correo@mail.com"
                            required />
                        <label for="validationCustom03" class="form-label"></label>
                        <div class="valid-feedback">Looks good!</div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="form-outline">
                        <input type="text" class="form-control" v-model="telefono" id="validationCustom02" placeholder="Teléfono"
                            required />
                        <label for="validationCustom03" class="form-label"></label>
                        <div class="valid-feedback">Looks good!</div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="form-outline">
                        <input type="text" class="form-control" v-model="password" id="validationCustom02" placeholder="Password"
                            required />
                        <label for="validationCustom03" class="form-label"></label>
                        <div class="valid-feedback">Looks good!</div>
                    </div>
                </div>
                <div class="col-12">
                    <b-button pill variant="outline-danger" href="/">Cancelar</b-button>
                    |
                    <b-button type="submit" pill variant="outline-success">Registrarme</b-button>
                </div>
            </form>
        </b-card>
        <br>
        <img src="https://cdn-images.livecareer.es/pages/curriculum_vitae_de_dependienta_lces_1.jpg">
    </div>

</template>
<script>
import Registro from "@/components/Registro.vue";

export default {
    components: {
        Registro
    },
    data() {
        return {
            nombre:"",
            apellido:"",
            nombre_usuario:"",
            correo:"",
            telefono:null,
            password:""
        }
    },
    methods: {
        onSubmit(event) {
            event.preventDefault()
            this.axios.post('http://localhost:3000/api/cliente/add', {
                nombre: this.nombre,
                apellido: this.apellido,
                nombre_usuario: this.nombre_usuario,
                correo: this.correo,
                telefono: this.telefono,
                password: this.password
            }).then((response) => {
                console.log(response);
                this.$router.push('/')
            }).catch(function (error) {
                console.log(error)
            })
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
.container .b-button {
    float: left
}
</style>
