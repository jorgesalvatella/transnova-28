<template>
  <section class="hero-section" id="inicio">
    <div class="hero-container">
      <div class="hero-content">
        <div class="hero-text">
          <h1 class="hero-title">
            Soluciones de
            <span class="gradient-text">Logística</span>
            que impulsan tu negocio
          </h1>
          <p class="hero-description">
            Optimizamos tu cadena de suministro con tecnología avanzada y servicios de transporte
            confiables. Conectamos tu negocio con el mundo.
          </p>
          <div class="hero-buttons">
            <a href="https://wa.me/5219842039535" class="btn-primary" target="_blank">
              <span>Solicitar Información</span>
              <svg class="btn-arrow" width="20" height="20" viewBox="0 0 24 24" fill="none">
                <path
                  d="M7 17L17 7M17 7H7M17 7V17"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </a>
          </div>
        </div>

        <div class="hero-visual">
          <div class="visual-container">
            <!-- Imagen Principal de Camión Logístico -->
            <div class="hero-image-container">
              <img
                :src="IMAGE_URLS.URL_FOTO_CAMION_LOGISTICO"
                alt="Camión logístico moderno"
                class="hero-main-image futuristic-trailer"
              />
              <div class="image-overlay">
                <div class="tech-elements">
                  <div class="tech-dot"></div>
                  <div class="tech-dot"></div>
                  <div class="tech-dot"></div>
                </div>
              </div>
            </div>

            <!-- Camión animado -->
            <div class="truck-animation">
              <svg class="truck-svg" viewBox="0 0 200 100" fill="none">
                <rect x="20" y="40" width="80" height="30" rx="5" fill="#404b69" />
                <rect x="100" y="50" width="40" height="20" rx="3" fill="#2a3550" />
                <circle cx="40" cy="75" r="8" fill="#333" />
                <circle cx="120" cy="75" r="8" fill="#333" />
                <rect x="25" y="45" width="15" height="10" rx="2" fill="#fff" opacity="0.9" />
                <rect x="45" y="45" width="15" height="10" rx="2" fill="#fff" opacity="0.9" />
              </svg>
            </div>

            <!-- Líneas de trayectoria -->
            <div class="route-lines">
              <div class="route-line route-1"></div>
              <div class="route-line route-2"></div>
              <div class="route-line route-3"></div>
            </div>

            <!-- Indicadores de ubicación -->
            <div class="location-dots">
              <div class="location-dot dot-1">
                <div class="dot-pulse"></div>
              </div>
              <div class="location-dot dot-2">
                <div class="dot-pulse"></div>
              </div>
              <div class="location-dot dot-3">
                <div class="dot-pulse"></div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Stats section -->
      <div class="hero-stats">
        <div class="stat-item">
          <div class="stat-number">500+</div>
          <div class="stat-label">Clientes Satisfechos</div>
        </div>
        <div class="stat-item">
          <div class="stat-number">10k+</div>
          <div class="stat-label">Entregas Realizadas</div>
        </div>
        <div class="stat-item">
          <div class="stat-number">24/7</div>
          <div class="stat-label">Soporte Técnico</div>
        </div>
        <div class="stat-item">
          <div class="stat-number">98%</div>
          <div class="stat-label">Entregas a Tiempo</div>
        </div>
      </div>
    </div>

    <!-- Background elements -->
    <div class="hero-bg">
      <div class="bg-gradient"></div>
      <div class="bg-pattern"></div>
    </div>
  </section>
</template>

<script>
import { IMAGE_URLS } from '@/constants/images'

export default {
  name: 'HeroSection',
  data() {
    return {
      IMAGE_URLS,
    }
  },
}
</script>

<style scoped>
.hero-section {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding-top: 80px;
}

.hero-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url('https://imagenes.transnova28.com.mx/Transporte%20Logistico/Portada-Transnova28.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  z-index: -1;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  margin-bottom: 4rem;
}

.hero-text {
  animation: fadeInUp 1s ease-out;
  padding-left: 2rem;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 1.5rem;
  color: white;
  letter-spacing: -1px;
}

.gradient-text {
  background: linear-gradient(135deg, #fde047 0%, #f97316 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-description {
  font-size: 1.25rem;
  line-height: 1.6;
  color: whitesmoke;
  margin-bottom: 2rem;
  max-width: 500px;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn-primary {
  background: linear-gradient(135deg, #fde047 0%, #f97316 100%);
  color: white;
  border: none;
  padding: 1rem 2rem;
  border-radius: 50px;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  text-align: center;
  gap: 0.5rem;
  box-shadow: 0 8px 25px rgba(64, 75, 105, 0.3);
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 12px 35px rgba(64, 75, 105, 0.4);
}

.btn-secondary {
  background: transparent;
  color: #404b69;
  border: 2px solid #404b69;
  padding: 1rem 2rem;
  border-radius: 50px;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.btn-secondary:hover {
  background: #404b69;
  color: white;
  transform: translateY(-2px);
}

.btn-arrow {
  transition: transform 0.3s ease;
}

.btn-primary:hover .btn-arrow {
  transform: translateX(3px);
}

.hero-visual {
  animation: fadeInRight 1s ease-out 0.3s both;
}

.visual-container {
  position: relative;
  height: 400px;
  width: 100%;
}

/* Hero Image Container */
.hero-image-container {
  position: absolute;
  top: 10%;
  right: 10%;
  width: 350px;
  height: 240px;
  z-index: 3;
}

.hero-main-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 20px;
}

.image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, rgba(64, 75, 105, 0.1), transparent);
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.tech-elements {
  display: flex;
  gap: 12px;
  opacity: 0.7;
}

.tech-dot {
  width: 8px;
  height: 8px;
  background: rgba(64, 75, 105, 0.8);
  border-radius: 50%;
  animation: pulse 2s ease-in-out infinite;
}

.tech-dot:nth-child(2) {
  animation-delay: 0.5s;
}

.tech-dot:nth-child(3) {
  animation-delay: 1s;
}

.truck-animation {
  position: absolute;
  top: 50%;
  left: 0;
  transform: translateY(-50%);
  animation: truckMove 4s ease-in-out infinite;
}

.truck-svg {
  width: 120px;
  height: 60px;
  filter: drop-shadow(0 4px 15px rgba(64, 75, 105, 0.3));
}

.route-lines {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.route-line {
  position: absolute;
  height: 2px;
  background: linear-gradient(90deg, transparent 0%, #404b69 50%, transparent 100%);
  border-radius: 1px;
}

.route-1 {
  top: 30%;
  left: 10%;
  width: 60%;
  animation: routeFlow 3s ease-in-out infinite;
}

.route-2 {
  top: 50%;
  left: 20%;
  width: 50%;
  animation: routeFlow 3s ease-in-out infinite 1s;
}

.route-3 {
  top: 70%;
  left: 5%;
  width: 70%;
  animation: routeFlow 3s ease-in-out infinite 2s;
}

.location-dots {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.location-dot {
  position: absolute;
  width: 12px;
  height: 12px;
  background: #404b69;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.dot-1 {
  top: 25%;
  right: 20%;
}
.dot-2 {
  top: 45%;
  right: 40%;
}
.dot-3 {
  top: 65%;
  right: 10%;
}

.dot-pulse {
  width: 6px;
  height: 6px;
  background: white;
  border-radius: 50%;
  animation: pulse 2s ease-in-out infinite;
}

.hero-stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
  padding: 2rem;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
  animation: fadeInUp 1s ease-out 0.6s both;
}

.stat-item {
  text-align: center;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 800;
  color: #404b69;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 0.9rem;
  color: #666;
  font-weight: 500;
}

.hero-bg {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: -1;
}

.bg-gradient {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
}

.bg-pattern {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image:
    radial-gradient(circle at 25% 25%, rgba(64, 75, 105, 0.1) 0%, transparent 50%),
    radial-gradient(circle at 75% 75%, rgba(42, 53, 80, 0.1) 0%, transparent 50%);
}

/* Animations */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes truckMove {
  0%,
  100% {
    transform: translateY(-50%) translateX(0);
  }
  50% {
    transform: translateY(-50%) translateX(30px);
  }
}

@keyframes routeFlow {
  0% {
    opacity: 0.6;
    transform: scaleX(0);
  }
  50% {
    opacity: 1;
    transform: scaleX(1);
  }
  100% {
    opacity: 0.6;
    transform: scaleX(0);
  }
}

@keyframes pulse {
  0%,
  100% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.5;
    transform: scale(1.2);
  }
}

/* Mobile Styles */

@media screen and (max-width: 768px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }

  .hero-title {
    font-size: 2.5rem;
    padding-top: 8rem;
  }

  .hero-description {
    font-size: 1.1rem;
    margin-left: auto;
    margin-right: auto;
  }

  .hero-buttons {
    justify-content: center;
  }

  .visual-container {
    display: none;
  }

  .hero-image-container {
    display: none;
  }

  .truck-animation,
  .route-lines,
  .location-dots {
    display: none;
  }

  .hero-stats {
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
    padding: 1.5rem;
  }

  .stat-number {
    font-size: 2rem;
  }
}

@media (max-width: 767px) {
  .hero-text {
    padding-left: 0;
  }
}

@media screen and (max-width: 480px) {
  .hero-title {
    font-size: 2rem;
  }
  .hero-text {
    animation: fadeInUp 1s ease-out;
    padding: none;
  }

  .hero-buttons {
    flex-direction: column;
  }

  .hero-stats {
    grid-template-columns: 1fr;
  }
}

@media screen and (max-width: 768px) {
  .hero-text {
    animation: fadeInUp 1s ease-out;
    padding: none;
  }
}
</style>
