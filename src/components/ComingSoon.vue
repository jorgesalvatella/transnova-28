<template>
  <div class="d-flex flex-column justify-content-center align-items-center vh-100 w-100 p-5" style="background: linear-gradient(135deg, #404b69 0%, #2a3550 100%); color: white; position: relative; overflow: hidden;">
    <div class="text-center w-100">
      <!-- Logo con efecto de resplandor -->
      <div class="mb-5 position-relative">
        <img
          src="https://imagenes.transnova28.com.mx/tranpo.png"
          alt="Transnova 28 Logo"
          class="rounded-circle shadow-lg img-fluid animate__animated animate__fadeIn"
          :style="getLogoStyle()"
          @mouseover="hover = true; glow = true"
          @mouseleave="hover = false; glow = false"
        />
        <div class="position-absolute top-50 start-50 translate-middle" style="width: 28rem; height: 28rem; border-radius: 50%; background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0) 70%); z-index: -1;"></div>
      </div>
      <!-- Texto con animación de entrada -->
      <h1 class="display-1 fw-bolder mb-4 animate__animated animate__fadeInUp" style="text-shadow: 3px 3px 15px rgba(0, 0, 0, 0.6); letter-spacing: 2px;">
        Transnova 28
      </h1>
      <p class="display-3 mb-5 animate__animated animate__fadeInUp" style="animation-delay: 0.5s; text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.4);">
        Próximamente
      </p>
      
    </div>
  </div>
</template>

<script>
export default {
  name: 'ComingSoon',
  data() {
    return {
      hover: false,
      glow: false
    }
  },
  methods: {
    getLogoStyle() {
      return {
        width: '22rem',
        height: '22rem',
        transition: 'transform 0.3s, box-shadow 0.3s',
        cursor: 'pointer',
        'object-fit': 'cover',
        transform: this.hover ? 'scale(1.15)' : 'scale(1)',
        boxShadow: this.glow ? '0 0 20px rgba(255, 255, 255, 0.7)' : '0 10px 20px rgba(0, 0, 0, 0.3)'
      }
    }
  }
}
</script>

<style scoped>
.animate__fadeIn {
  animation-duration: 1.5s;
}
.animate__fadeInUp {
  animation-duration: 1.5s;
}
:deep(.vh-100) {
  height: 100vh !important;
}
</style>