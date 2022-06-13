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
          <b-nav-item href="/Login">Iniciar Sesión</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <router-view></router-view>
    <footer>
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
