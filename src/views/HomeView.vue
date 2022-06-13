<template>
  <div class="home">
    <b-carousel id="carousel-1" v-model="slide" :interval="4000" controls indicators background="#ababab"
      img-width="1024" img-height="480" style="text-shadow: 1px 1px 2px #333;" @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd">
      <!-- Slides with custom text -->
      <b-carousel-slide
        img-src="https://www.esdesignbarcelona.com/sites/default/files/inline-images/Que%CC%81%20es%20el%20estilo%20de%20ropa%20aesthetic%2C%20la%20moda%20de%20la%20que%20todos%20hablan%20%282%29.png"
        caption="¡Bienvenido a:">
        <h1>Hakoo Store!</h1>
        <b-button href="/Registro" pill variant="outline-danger">Registrar</b-button>
      </b-carousel-slide>
      <!-- Text slides with image -->
      <b-carousel-slide
        img-src="https://www.esdesignbarcelona.com/sites/default/files/2022-03/Que%CC%81%20es%20el%20estilo%20de%20ropa%20aesthetic%2C%20la%20moda%20de%20la%20que%20todos%20hablan%20%283%29_0.png">
        <h1>¡Aprovecha los beneficios!</h1>
        <b-button href="/Registro" pill variant="outline-danger">Registrar</b-button>
      </b-carousel-slide>
      <b-carousel-slide>
        <template #img>
          <img class="d-block img-fluid w-100" width="1024" height="480"
            src="https://www.esdesignbarcelona.com/sites/default/files/inline-images/Que%CC%81%20es%20el%20estilo%20de%20ropa%20aesthetic%2C%20la%20moda%20de%20la%20que%20todos%20hablan.png"
            alt="image slot">
        </template>
        <h1>Registrate y ponte a la moda</h1>
        <b-button href="/Registro" pill variant="outline-danger">Registrar</b-button>
      </b-carousel-slide>
      <b-carousel-slide>
        <template #img>
          <img class="d-block img-fluid w-100" width="1024" height="480"
            src="..\src\assets\Logos\white_logo_color_background_Horizontal.jpg" alt="image slot">
        </template>
        <h1>Registrate y ponte a la moda</h1>
        <b-button href="/Registro" pill variant="outline-danger">Registrar</b-button>
      </b-carousel-slide>
    </b-carousel>
    <!-- Footer -->
    <footer class="text-center text-lg-start bg-light text-muted">
      <!-- Section: Social media -->
      <section class="d-flex justify-content-center justify-content-lg-between p-4 border-bottom">
        <!-- Left -->
        <div class="me-5 d-none d-lg-block">
          <span>Conéctate con nosotros:</span>
        </div>
        <!-- Left -->

        <!-- Right -->
        <div>
          <a href="" class="me-4 text-reset">
            <i class="fab fa-facebook-f"></i>
          </a>
          <a href="" class="me-4 text-reset">
            <i class="fab fa-twitter"></i>
          </a>
          <a href="" class="me-4 text-reset">
            <i class="fab fa-google"></i>
          </a>
          <a href="" class="me-4 text-reset">
            <i class="fab fa-instagram"></i>
          </a>
          <a href="" class="me-4 text-reset">
            <i class="fab fa-linkedin"></i>
          </a>
          <a href="" class="me-4 text-reset">
            <i class="fab fa-github"></i>
          </a>
        </div>
        <!-- Right -->
      </section>
      <!-- Section: Social media -->

      <!-- Section: Links  -->
      <section class="">
        <div class="container text-center text-md-start mt-5">
          <!-- Grid row -->
          <div class="row mt-3">
            <!-- Grid column -->
            <div class="col-md-3 col-lg-4 col-xl-3 mx-auto mb-4">
              <!-- Content -->
              <img id="logohome" src="..\src\assets\Logos\Orden_vertical\dark_logo_transparent_background2.png"
                class="m-3" width="100px" height="100px">
              <p>
                Con 30 años de experiencia vendiendo lo más moderno en ropa y accesorios, te
                acompañamos en cada paso que das.
              </p>
            </div>
            <!-- Grid column -->
            <!-- Grid column -->
            <div class="col-md-3 col-lg-2 col-xl-2 mx-auto mb-4">
              <!-- Links -->
              <h6 class="text-uppercase fw-bold mb-4">
                Trabaja con Nosotros
              </h6>
              <p>
                <a href="#!" class="text-reset">Envía tu currículum</a>
              </p>
            </div>
            <!-- Grid column -->

            <!-- Grid column -->
            <div class="col-md-5 col-lg-3 col-xl-4 mx-auto mb-md-0 mb-5">
              <!-- Links -->
              <h6 class="text-uppercase fw-bold mb-4">
                Contacto:
              </h6>
              <p><i class="fas fa-home me-4"></i>San Miguel,El Salvador,59AVSur,Calle el Progreso</p>
              <p>
                <i class="fas fa-envelope me-3"></i>
                servicioalcliente@hakoostore.com
              </p>
              <p><i class="fas fa-phone me-3"></i> +503 2345-6789</p>
              <p><i class="fas fa-print me-3"></i> +503 2219-7860</p>
            </div>
            <!-- Grid column -->
          </div>
          <!-- Grid row -->
        </div>
      </section>
      <!-- Section: Links  -->
    </footer>
    <!-- Footer -->
    <HelloWorld msg="Hakoo" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  data() {
    return {
      slide: 0,
      sliding: null
    }
  },
  methods: {
    onSlideStart() {
      this.sliding = true
    },
    onSlideEnd() {
      this.sliding = false
    }
  }
}

</script>
