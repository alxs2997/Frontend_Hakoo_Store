<template>
  <div id="app">
    <b-navbar toggleable type="dark" variant="dark">
      <b-navbar-toggle target="navbar-toggle-collapse">
        <template #default="{ expanded }">
          <b-icon v-if="expanded" icon="chevron-bar-up"></b-icon>
          <b-icon v-else icon="chevron-bar-down"></b-icon>
        </template>
      </b-navbar-toggle>
      <b-navbar-brand href="#">
        <router-link to="/">
          <img id="logohome" src="../src/assets/Logos/white_logo_transparent_backgroundHorizontal.png" alt=""
            class="mr-sm-2" width="60px" height="40px" center>
        </router-link>
        |
        <button type="button" class="btn btn-outline-secondary position-relative" id="show-btn" @click="$bvModal.show('bv-modal-exe')">
          <i class="fa fa-cart-plus"></i>
          <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">
            7
            <span class="visually-hidden">Sus productos añadidos</span>
          </span>
        </button>
        <b-modal id="bv-modal-exe" hide-footer>
          <template #modal-title>
              <h2 text="center">Productos Añadidos</h2>
            </template>
            <div class="d-block text-center">
              +
            </div>
            <b-button pill variant="outline-secondary" class="mt-3" block @click="$bvModal.hide('bv-modal-exe')">
              Eliminar</b-button>
            <div class="modal-footer">
              <b-button pill variant="outline-success">Pagar</b-button>
            </div>
        </b-modal>
      </b-navbar-brand>


      <b-collapse id="navbar-toggle-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-button squared variant="outline-secondary" href="/">Home</b-button>
          <b-button squared variant="outline-secondary" href="#">Merch</b-button>
          <b-button squared variant="outline-secondary" id="show-btn" @click="$bvModal.show('bv-modal-example')">Iniciar
            Sesión</b-button>
          <!-- Modal accion formulario  -->
          <b-modal id="bv-modal-example" hide-footer>
            <template #modal-title>
              <h2 text="center">¡Hola de Nuevo!</h2>
            </template>
            <div class="d-block text-center">
              <h3>Ingrese sus credenciales</h3>
              <b-form-group role="form">
                <div class="form-group">
                  <label for="inputUser">Usuario:</label>
                  <b-input type="text" class="form-control" id="inputName" placeholder="Ingresa tu correo o usuario...">
                  </b-input>
                </div>
                <br>
                <div class="form-group">
                  <label for="inputpass">Contraseña:</label>
                  <b-input type="password" name="password" class="form-control" id="inputPass" placeholder="Password">
                  </b-input>
                </div>
              </b-form-group>
            </div>
            <b-button pill variant="outline-secondary" class="mt-3" block @click="$bvModal.hide('bv-modal-example')">
              Cancelar</b-button>
            <div class="modal-footer">
              <b-button pill variant="secondary" href="/Registro">Registrarse</b-button>
              <b-button pill variant="outline-info">Iniciar Sesión</b-button>
            </div>

          </b-modal>
          <!-- Modal Accion formulario  -->
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <router-view></router-view>
    <footer class="text-center text-lg-start bg-light text-muted">
      <!-- Copyright -->
      <div class="text-center p-4" style="background-color: rgba(0, 0, 0, 0.05);">
        © 2022 Copyright:
        <a class="text-reset fw-bold" href="https://github.com/galle997/Proyecto_Hakoo">Hakoo Store Project</a>
      </div>
      <!-- Copyright -->
    </footer>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
