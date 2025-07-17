<template>
  <section class="services-section" id="servicios">
    <div class="services-container">
      <!-- Header -->
      <div class="services-header">
        <h2 class="section-title">Nuestros Servicios</h2>
        <p class="section-subtitle">
          Soluciones integrales de logística y transporte diseñadas para impulsar tu negocio
        </p>
      </div>

      <!-- Services Grid -->
      <div class="services-grid">
        <!-- Imagen decorativa de almacén -->
        <div class="services-image-container">
          <img
            :src="IMAGE_URLS.URL_FOTO_ALMACEN_DISTRIBUCION"
            alt="Almacén moderno de distribución"
            class="services-image glass-transport"
          />
        </div>
        <div
          v-for="(service, index) in services"
          :key="service.id"
          class="service-card"
          :class="{ featured: service.featured }"
          @mouseenter="hoveredCard = index"
          @mouseleave="hoveredCard = null"
        >
          <div class="service-icon">
            <component :is="service.icon" />
          </div>
          <h3 class="service-title">{{ service.title }}</h3>
          <p class="service-description">{{ service.description }}</p>
          <ul class="service-features">
            <li v-for="feature in service.features" :key="feature">
              <svg class="check-icon" width="16" height="16" viewBox="0 0 24 24" fill="none">
                <path
                  d="M20 6L9 17L4 12"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
              {{ feature }}
            </li>
          </ul>
          <div class="service-action">
            <button class="btn-service">
              Más Información
              <svg class="arrow-icon" width="16" height="16" viewBox="0 0 24 24" fill="none">
                <path
                  d="M7 17L17 7M17 7H7M17 7V17"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </button>
          </div>
        </div>
      </div>

      <!-- CTA Section -->
      <div class="services-cta">
        <div class="cta-content">
          <h3>¿Necesitas una solución personalizada?</h3>
          <p>
            Contáctanos para diseñar un plan logístico que se adapte perfectamente a las necesidades
            de tu empresa
          </p>
          <a href="https://wa.me/5219842039535" class="btn-cta" target="_blank"
            >Solicitar Cotización</a
          >
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { IMAGE_URLS } from '@/constants/images'

export default {
  name: 'ServicesSection',
  data() {
    return {
      IMAGE_URLS,
      hoveredCard: null,
      services: [
        {
          id: 1,
          title: 'Transporte Terrestre',
          description:
            'Servicio de transporte confiable y eficiente para mercancías de cualquier tamaño.',
          features: [
            'Flota moderna y equipada',
            'Seguimiento en tiempo real',
            'Entregas programadas',
            'Seguro de mercancías',
          ],
          icon: 'TruckIcon',
          featured: false,
        },

        {
          id: 4,
          title: 'Logística Integral',
          description: 'Gestión completa de tu cadena de suministro desde origen hasta destino.',
          features: [
            'Consultoría especializada',
            'Análisis de procesos',
            'Optimización de costos',
            'Reportes detallados',
          ],
          icon: 'LogisticsIcon',
          featured: false,
        },

        {
          id: 6,
          title: 'Tecnología y Rastreo',
          description: 'Plataforma tecnológica avanzada para el control total de tus envíos.',
          features: [
            'App móvil',
            'Dashboard en tiempo real',
            'Alertas automáticas',
            'Integración API',
          ],
          icon: 'TechIcon',
          featured: false,
        },
      ],
    }
  },
  components: {
    TruckIcon: {
      template: `
        <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <rect x="1" y="3" width="15" height="13"></rect>
          <polygon points="16,8 20,8 23,11 23,16 16,16"></polygon>
          <circle cx="5.5" cy="18.5" r="2.5"></circle>
          <circle cx="18.5" cy="18.5" r="2.5"></circle>
        </svg>
      `,
    },
    WarehouseIcon: {
      template: `
        <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M2 20h20"></path>
          <path d="M4 20V9l8-4 8 4v11"></path>
          <path d="M9 20v-6h6v6"></path>
        </svg>
      `,
    },
    DeliveryIcon: {
      template: `
        <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <rect x="1" y="5" width="22" height="14" rx="2" ry="2"></rect>
          <path d="M8 19H5a2 2 0 01-2-2V7a2 2 0 012-2h14a2 2 0 012 2v10a2 2 0 01-2 2h-3"></path>
          <circle cx="12" cy="19" r="2"></circle>
          <path d="M8 19l4 0 4 0"></path>
        </svg>
      `,
    },
    LogisticsIcon: {
      template: `
        <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <polyline points="22,12 18,12 15,21 9,3 6,12 2,12"></polyline>
        </svg>
      `,
    },
    SpecialIcon: {
      template: `
        <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M12 2L2 7l10 5 10-5-10-5z"></path>
          <path d="M2 17l10 5 10-5"></path>
          <path d="M2 12l10 5 10-5"></path>
        </svg>
      `,
    },
    TechIcon: {
      template: `
        <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <rect x="2" y="3" width="20" height="14" rx="2" ry="2"></rect>
          <line x1="8" y1="21" x2="16" y2="21"></line>
          <line x1="12" y1="17" x2="12" y2="21"></line>
        </svg>
      `,
    },
  },
}
</script>

<style scoped>
.services-section {
  padding: 6rem 0;
  background: linear-gradient(135deg, #f8fafc 0%, #ffffff 100%);
}

.services-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.services-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 3rem;
  font-weight: 800;
  color: #2a3550;
  margin-bottom: 1rem;
  letter-spacing: -1px;
}

.section-subtitle {
  font-size: 1.2rem;
  color: #666;
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
  position: relative;
}

/* Services Image Container */
.services-image-container {
  position: absolute;
  top: -80px;
  right: -100px;
  width: 300px;
  height: 200px;
  z-index: 1;
  opacity: 0.6;
}

.services-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 24px;
}

.service-card {
  background: white;
  border-radius: 20px;
  padding: 2.5rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.service-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.service-card:hover::before {
  transform: scaleX(1);
}

.service-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.15);
}

.service-card.featured {
  background: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  color: white;
  transform: scale(1.05);
}

.service-card.featured::before {
  display: none;
}

.service-card.featured:hover {
  transform: scale(1.05) translateY(-10px);
}

.service-icon {
  color: #404b69;
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  justify-content: flex-start;
}

.service-card.featured .service-icon {
  color: white;
}

.service-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: #2a3550;
  margin-bottom: 1rem;
}

.service-card.featured .service-title {
  color: white;
}

.service-description {
  color: #666;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.service-card.featured .service-description {
  color: rgba(255, 255, 255, 0.9);
}

.service-features {
  list-style: none;
  padding: 0;
  margin: 0 0 2rem 0;
}

.service-features li {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 0.75rem;
  font-size: 0.9rem;
  color: #555;
}

.service-card.featured .service-features li {
  color: rgba(255, 255, 255, 0.9);
}

.check-icon {
  color: #10b981;
  flex-shrink: 0;
}

.service-card.featured .check-icon {
  color: #34d399;
}

.service-action {
  margin-top: auto;
}

.btn-service {
  background: transparent;
  color: #404b69;
  border: 2px solid #404b69;
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  font-weight: 600;
  font-size: 0.9rem;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  width: fit-content;
}

.btn-service:hover {
  background: #404b69;
  color: white;
  transform: translateX(5px);
}

.service-card.featured .btn-service {
  background: white;
  color: #404b69;
  border-color: white;
}

.service-card.featured .btn-service:hover {
  background: rgba(255, 255, 255, 0.9);
  transform: translateX(5px);
}

.arrow-icon {
  transition: transform 0.3s ease;
}

.btn-service:hover .arrow-icon {
  transform: translateX(3px);
}

.services-cta {
  background: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  border-radius: 20px;
  padding: 3rem;
  text-align: center;
  color: white;
}

.cta-content h3 {
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.cta-content p {
  font-size: 1.1rem;
  margin-bottom: 2rem;
  opacity: 0.9;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.btn-cta {
  background: white;
  color: #404b69;
  border: none;
  padding: 1rem 2rem;
  border-radius: 25px;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(255, 255, 255, 0.2);
}

.btn-cta:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(255, 255, 255, 0.3);
}

/* Mobile Styles */
@media screen and (max-width: 768px) {
  .section-title {
    font-size: 2.5rem;
  }

  .services-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .services-image-container {
    display: none;
  }

  .service-card {
    padding: 2rem;
  }

  .services-cta {
    padding: 2rem;
  }

  .cta-content h3 {
    font-size: 1.5rem;
  }
}

@media screen and (max-width: 480px) {
  .section-title {
    font-size: 2rem;
  }

  .service-card {
    padding: 1.5rem;
  }

  .services-cta {
    padding: 1.5rem;
  }
}
</style>
