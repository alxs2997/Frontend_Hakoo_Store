<template>
    <div>
        <b-card class="col-md-6 offset-md-3">
            <br>
            <form class="row g-3 needs-validation" novalidate>

                <h3>Formulario De Registro</h3>
                <p>Para seguir las tendencias en moda...</p>
                <div class="col-md-4">
                    <div class="form-outline">
                        <input type="text" class="form-control" id="validationCustom01" placeholder="Nombres"
                            required />
                        <div class="valid-feedback">Looks good!</div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="form-outline">
                        <input type="text" class="form-control" id="validationCustom02" placeholder="Apellidos"
                            required />
                        <div class="valid-feedback">Looks good!</div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="input-group form-outline">
                        <span class="input-group-text" id="inputGroupPrepend">@</span>
                        <input type="text" class="form-control" id="validationCustomUsername"
                            aria-describedby="inputGroupPrepend" placeholder="Username" required />
                        <div class="invalid-feedback">Please choose a username.</div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="form-outline">
                        <input type="text" class="form-control" id="validationCustom02" placeholder="correo@mail.com"
                            required />
                        <label for="validationCustom03" class="form-label"></label>
                        <div class="valid-feedback">Looks good!</div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="form-outline">
                        <input type="text" class="form-control" id="validationCustom02" placeholder="Teléfono"
                            required />
                        <label for="validationCustom03" class="form-label"></label>
                        <div class="valid-feedback">Looks good!</div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="form-outline">
                        <input type="text" class="form-control" id="validationCustom02" placeholder="Password"
                            required />
                        <label for="validationCustom03" class="form-label"></label>
                        <div class="valid-feedback">Looks good!</div>
                    </div>
                </div>
                <div class="col-12">
                    <b-button pill variant="outline-danger">Cancelar</b-button>
                    |
                    <b-button pill variant="outline-success">Registrarme</b-button>
                </div>
            </form>
        </b-card>
        <br>
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
.container .b-button {
    float: left
}
</style>
