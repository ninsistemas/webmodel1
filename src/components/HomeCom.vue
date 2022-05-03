<template>
  <div>
    <!-- ======= Header ======= -->
    <header id="header" class="fixed-top d-flex align-items-center">
      <div class="container">
        <div class="header-container d-flex align-items-center justify-content-between">
          <div class="logo">
            <h1 class="text-light"><a href="index.html"><span>{{ datosEmpresa.nombre }}</span></a></h1>
          </div>

          <nav id="navbar" class="navbar">
            <ul>
              <li><a class="nav-link scrollto active" href="#hero">Inicio</a></li>
              <li><a class="nav-link scrollto" href="#about">Nosotros</a></li>
              <li><a class="nav-link scrollto" href="#services">Servicios</a></li>
              <li><a class="nav-link scrollto " href="#portfolio">Portfolio</a></li>
              <li><a class="nav-link scrollto" href="#team">Equipo</a></li>
              <li><a class="getstarted scrollto" href="#contact">Contacto</a></li>
            </ul>
            <i class="bi bi-list mobile-nav-toggle"></i>
          </nav><!-- .navbar -->

        </div><!-- End Header Container -->
      </div>
    </header><!-- End Header -->

    <!-- ======= Hero Section ======= -->
    <section id="hero" class="d-flex align-items-center">
      <div class="container text-center position-relative" data-aos="fade-in" data-aos-delay="200">
        <h1>{{ datosEmpresa.tituloWeb }}</h1>
        <h2>{{ datosEmpresa.subTutiloWeb }}</h2>
        <a href="#about" class="btn-get-started scrollto">iniciemos</a>
      </div>
    </section><!-- End Hero -->

    <main id="main">
      <!-- ======= About Section ======= -->
      <section id="about" class="about">
        <div class="container mt-4">

          <div class="row content">
            <div class="col-lg-6" data-aos="fade-right" data-aos-delay="100">
              <h2>{{ datosEmpresa.tituloResumen }}</h2>
              <h3>{{ datosEmpresa.subTituloResumen }}</h3>
            </div>
            <div class="col-lg-6 pt-4 pt-lg-0" data-aos="fade-left" data-aos-delay="200">
              <p>{{ datosEmpresa.resumenEmppresa }}</p>
            </div>
          </div>

        </div>
      </section><!-- End About Section -->

      <!-- ======= Cta Section ======= -->
      <section id="cta" class="cta">
        <div class="container">

          <div class="text-center" data-aos="zoom-in">
            <h3>Toma acciones</h3>
            <p> Llena nuestra plantilla de test para poder pertenecer a nuestro equipo</p>
            <a class="cta-btn" href="#">Plantilla</a>
          </div>

        </div>
      </section><!-- End Cta Section -->

      <!-- ======= Services Section ======= -->
      <section id="services" class="services section-bg">
        <div class="container mt-4">

          <div class="row">
            <div class="col-lg-4">
              <div class="section-title" data-aos="fade-right">
                <h2>Servicios</h2>
              </div>
            </div>
            <div class="col-lg-8">
              <div class="row">
                <div v-for="servicio in servicios" :key="servicio.id" class="col-md-6 d-flex align-items-stretch">
                  <div class="icon-box" data-aos="zoom-in" data-aos-delay="100">
                    <div class="icon"><i :class="servicio.icono"></i></div>
                    <h4><a href="">{{ servicio.titulo }}</a></h4>
                    <p>{{ servicio.descripcion }}</p>
                  </div>
                </div>
              </div>
            </div>
          </div>

        </div>
      </section><!-- End Services Section -->

      <!-- ======= Portfolio Section ======= -->
      <section id="portfolio" class="portfolio">
        <div class="container mt-4">

          <div class="section-title" data-aos="fade-left">
            <h2>Portfolio</h2>
            <p>{{ portafolio.resumen }}</p>
          </div>

          <div class="row portfolio-container" data-aos="fade-up" data-aos-delay="200">

            <div v-for = "item in portafolio.items" :key="item.id" class="col-lg-4 col-md-6 portfolio-item filter-app">
              <div class="portfolio-wrap">
                <img :src="urlimg+item.imagen" class="img-fluid" alt="">
                <div class="portfolio-info">
                  <h4>{{ item.titulo }}</h4>
                  <div class="portfolio-links">
                    <a :href="item.enlase" title="More Details"><i class="bx bx-link"></i></a>
                  </div>
                </div>
              </div>
            </div>

          </div>

        </div>
      </section><!-- End Portfolio Section -->

      <!-- ======= Testimonials Section ======= -->
      <section id="testimonials" class="testimonials section-bg">
        <div class="container">

          <div class="row">
            <div class="col-lg-4">
              <div class="section-title" data-aos="fade-right">
                <h2>Testimonios</h2>
                <p>{{ testimonio.resumenpersona }}</p>
              </div>
            </div>
            <div class="col-lg-8" data-aos="fade-up" data-aos-delay="100">

              <div class="testimonials-slider swiper" data-aos="fade-up" data-aos-delay="100">
                <div class="swiper-wrapper">

                  <div class="swiper-slide">
                    <div class="testimonial-item">
                      <p>
                        <i class="bx bxs-quote-alt-left quote-icon-left"></i>{{ testimonio.testimonio }}<i class="bx bxs-quote-alt-right quote-icon-right"></i>
                      </p>
                      <img :src="urlimg+testimonio.imagen" class="testimonial-img" alt="">
                      <h3>{{ testimonio.nombre }}</h3>
                      <h4>{{ testimonio.cargo }}</h4>
                    </div>
                  </div><!-- End testimonial item -->

                </div>
                <div class="swiper-pagination"></div>
              </div>
            </div>
          </div>

        </div>
      </section><!-- End Testimonials Section -->

      <!-- ======= Team Section ======= -->
      <section id="team" class="team">
        <div class="container mt-4">

          <div class="row">
            <div class="col-lg-4">
              <div class="section-title" data-aos="fade-right">
                <h2>Equipo</h2>
                <p>{{ equipo.resumen }}</p>
              </div>
            </div>
            <div class="col-lg-8">
              <div class="row">

                <div v-for = "itemeq in equipo.items" :key="itemeq.id" class="col-lg-6">
                  <div class="member" data-aos="zoom-in" data-aos-delay="100">
                    <div class="pic"><img :src="urlimg+itemeq.imagen" class="img-fluid" alt=""></div>
                    <div class="member-info">
                      <h4>{{ itemeq.nombre }}</h4>
                      <span>{{ itemeq.cargo }}</span>
                      <p>{{ itemeq.resumen }}</p>
                      <div class="social">
                        <a :href="itemeq.twiter"><i class="ri-twitter-fill"></i></a>
                        <a :href="itemeq.instagran"><i class="ri-instagram-fill"></i></a>
                        <a :href="itemeq.linkedin"> <i class="ri-linkedin-box-fill"></i> </a>
                      </div>
                    </div>
                  </div>
                </div>

              </div>

            </div>
          </div>

        </div>
      </section><!-- End Team Section -->

      <!-- ======= Contact Section ======= -->
      <section id="contact" class="contact">
        <div class="container mt-4">
          <div class="row">
            <div class="col-lg-4" data-aos="fade-right">
              <div class="section-title">
                <h2>Contacto</h2>
                <p>{{ datosEmpresa.resumencontacto }}</p>
              </div>
            </div>

            <div class="col-lg-8" data-aos="fade-up" data-aos-delay="100">
              <div class="info mt-4">
                <i class="bi bi-geo-alt"></i>
                <h4>Direccion:</h4>
                <p>{{ datosEmpresa.direccion }}</p>
              </div>
              <div class="row">
                <div class="col-lg-6 mt-4">
                  <div class="info">
                    <i class="bi bi-envelope"></i>
                    <h4>Email:</h4>
                    <p>{{ datosEmpresa.correo }}</p>
                  </div>
                </div>
                <div class="col-lg-6">
                  <div class="info w-100 mt-4">
                    <i class="bi bi-phone"></i>
                    <h4>Telefono:</h4>
                    <p>{{ datosEmpresa.telefono }}</p>
                  </div>
                </div>
              </div>

              <form action="forms/contact.php" method="post" role="form" class="php-email-form mt-4">
                <div class="row">
                  <div class="col-md-6 form-group">
                    <input type="text" name="name" class="form-control" id="name" placeholder="Tu nombre" required>
                  </div>
                  <div class="col-md-6 form-group mt-3 mt-md-0">
                    <input type="email" class="form-control" name="email" id="email" placeholder="Tu email" required>
                  </div>
                </div>
                <div class="form-group mt-3">
                  <input type="text" class="form-control" name="subject" id="subject" placeholder="Asunto" required>
                </div>
                <div class="form-group mt-3">
                  <textarea class="form-control" name="message" rows="5" placeholder="Mensaje" required></textarea>
                </div>
                <div class="my-3">
                  <div class="loading">Loading</div>
                  <div class="error-message"></div>
                  <div class="sent-message">Your message has been sent. Thank you!</div>
                </div>
                <div class="text-center"><button type="submit">Send Message</button></div>
              </form>
            </div>
          </div>

        </div>
      </section><!-- End Contact Section -->

    </main><!-- End #main -->

    <!-- ======= Footer ======= -->
    <footer id="footer">
      <div class="container d-md-flex py-4">

        <div class="me-md-auto text-center text-md-start">
          <div class="copyright">
            &copy; Copyright <strong><span>ninsistemas</span></strong>.
          </div>
          <div class="credits">
            Desarrollado con <a href="https://bootstrapmade.com/">BootstrapMade</a> y <a href="https://vuejs.org/">VueJS</a>
          </div>
        </div>
        <div class="social-links text-center text-md-right pt-3 pt-md-0">
          <a href="#" class="twitter"><i class="bx bxl-twitter"></i></a>
          <a href="#" class="facebook"><i class="bx bxl-facebook"></i></a>
          <a href="#" class="instagram"><i class="bx bxl-instagram"></i></a>
          <a href="#" class="google-plus"><i class="bx bxl-skype"></i></a>
          <a href="#" class="linkedin"><i class="bx bxl-linkedin"></i></a>
        </div>
      </div>
    </footer><!-- End Footer -->

    <a href="#" class="back-to-top d-flex align-items-center justify-content-center"><i class="bi bi-arrow-up-short"></i></a>
  </div>
</template>

<script>
import {Global} from '../shared/Global'
export default {
  name: 'HomeCom',
  data() {
    return{
      urlimg : Global.image_url,
      datosEmpresa : Global.datosEmpresa,
      servicios : Global.servicios,
      portafolio : Global.portafolio,
      testimonio : Global.testimonio,
      equipo : Global.equipo,
    }
  }
}
</script>
