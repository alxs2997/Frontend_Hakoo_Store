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
      </b-navbar-brand>


      <b-collapse id="navbar-toggle-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item href="/">Home</b-nav-item>
          <b-nav-item href="#">Merch</b-nav-item>
          <b-button id="show-btn" @click="$bvModal.show('bv-modal-example')">Iniciar Sesión</b-button>
          <!-- Modal accion formulario  -->
          <b-modal id="bv-modal-example" hide-footer class="modal fade" role="dialog">
            <div class="modal-content">
              <template class="modal-header">
                  <h2 text="center">¡Hola de Nuevo!</h2>
                  <h4 text="center">Bienvenido/a</h4>
                  <img id="logohome" src="../src/assets/Logos/white_logo_transparent_backgroundHorizontal.png" alt=""
                  class="mr-sm-2" width="60px" height="40px" center>
              </template>
              <!-- Modal Body -->
              <div class="modal-body">
                <p class="statusMsg"></p>
                <b-form-group role="form">
                  <div class="form-group">
                    <label for="inputUser">Usuario:</label>
                    <b-input type="text" class="form-control" id="inputName" placeholder="Ingresa tu correo o usuario...">
                    </b-input>
                  </div>
                  <div class="form-group">
                    <label for="inputpass">Contraseña:</label>
                    <b-input type="password" name="password" class="form-control" id="inputEmail" placeholder="Enter your email">
                    </b-input>
                  </div>
                </b-form-group>
              </div>

              <!-- Modal Footer -->
              <div class="modal-footer">
                <b-link href="/">Cancelar</b-link>
                |
                <b-button pill variant="outline-secondary" href="/Registro">Registrarse</b-button>
                <b-button pill variant="outline-info">Iniciar Sesión</b-button>
              </div>
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
