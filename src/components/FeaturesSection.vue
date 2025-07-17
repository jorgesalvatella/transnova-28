<template>
  <section class="features-section">
    <div class="features-container">
      <!-- Benefits Section -->
      <div class="benefits-section">
        <div class="benefits-content">
          <div class="benefits-text">
            <h2 class="section-title">
              ¿Por qué elegir 
              <span class="gradient-text">Transnova 28</span>?
            </h2>
            <p class="section-description">
              Más que un servicio de logística, somos tu socio estratégico para el crecimiento. 
              Nuestra experiencia y tecnología garantizan resultados excepcionales.
            </p>
            
            <div class="benefits-list">
              <div 
                v-for="(benefit, index) in benefits" 
                :key="benefit.id"
                class="benefit-item"
                :class="{ active: activeBenefit === index }"
                @mouseenter="activeBenefit = index"
              >
                <div class="benefit-icon">
                  <component :is="benefit.icon" />
                </div>
                <div class="benefit-content">
                  <h3 class="benefit-title">{{ benefit.title }}</h3>
                  <p class="benefit-description">{{ benefit.description }}</p>
                </div>
              </div>
            </div>
          </div>
          
          <div class="benefits-visual">
            <div class="visual-chart">
              <!-- Animated chart representation -->
              <div class="chart-container">
                <div class="chart-bar" style="height: 85%;">
                  <span class="chart-label">Eficiencia</span>
                  <span class="chart-value">85%</span>
                </div>
                <div class="chart-bar" style="height: 92%;">
                  <span class="chart-label">Puntualidad</span>
                  <span class="chart-value">92%</span>
                </div>
                <div class="chart-bar" style="height: 78%;">
                  <span class="chart-label">Ahorro</span>
                  <span class="chart-value">78%</span>
                </div>
                <div class="chart-bar" style="height: 95%;">
                  <span class="chart-label">Satisfacción</span>
                  <span class="chart-value">95%</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Features Grid -->
      <div class="features-grid-section">
        <div class="grid-header">
          <h2 class="section-title">Características que nos destacan</h2>
          <p class="section-subtitle">
            Tecnología avanzada y procesos optimizados para brindarte la mejor experiencia
          </p>
        </div>
        
        <div class="features-grid">
          <div 
            v-for="feature in features" 
            :key="feature.id"
            class="feature-card"
            @mouseenter="hoveredFeature = feature.id"
            @mouseleave="hoveredFeature = null"
          >
            <div class="feature-icon">
              <component :is="feature.icon" />
            </div>
            <h3 class="feature-title">{{ feature.title }}</h3>
            <p class="feature-description">{{ feature.description }}</p>
            <div class="feature-metric">
              <span class="metric-value">{{ feature.metric }}</span>
              <span class="metric-label">{{ feature.metricLabel }}</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Process Timeline -->
      <div class="process-section">
        <h2 class="section-title">Nuestro Proceso</h2>
        <p class="section-subtitle">
          Un flujo de trabajo optimizado que garantiza resultados excepcionales
        </p>
        
        <div class="process-timeline">
          <div 
            v-for="(step, index) in processSteps" 
            :key="step.id"
            class="process-step"
            :class="{ active: activeStep === index }"
          >
            <div class="step-number">{{ index + 1 }}</div>
            <div class="step-content">
              <h3 class="step-title">{{ step.title }}</h3>
              <p class="step-description">{{ step.description }}</p>
            </div>
            <div class="step-connector" v-if="index < processSteps.length - 1"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FeaturesSection',
  data() {
    return {
      activeBenefit: 0,
      hoveredFeature: null,
      activeStep: 0,
      benefits: [
        {
          id: 1,
          title: 'Experiencia Comprobada',
          description: 'Más de 10 años optimizando cadenas de suministro para empresas de todos los tamaños.',
          icon: 'ExperienceIcon'
        },
        {
          id: 2,
          title: 'Tecnología Avanzada',
          description: 'Sistemas de última generación para seguimiento, optimización y gestión en tiempo real.',
          icon: 'TechIcon'
        },
        {
          id: 3,
          title: 'Cobertura Nacional',
          description: 'Red de distribución que abarca todo el territorio nacional con tiempos garantizados.',
          icon: 'CoverageIcon'
        },
        {
          id: 4,
          title: 'Soporte 24/7',
          description: 'Equipo de atención especializado disponible las 24 horas para resolver cualquier incidencia.',
          icon: 'SupportIcon'
        }
      ],
      features: [
        {
          id: 1,
          title: 'Seguimiento GPS',
          description: 'Monitoreo en tiempo real de todos tus envíos con precisión de ubicación.',
          metric: '99.9%',
          metricLabel: 'Precisión',
          icon: 'GPSIcon'
        },
        {
          id: 2,
          title: 'Automatización',
          description: 'Procesos automatizados que reducen errores y optimizan tiempos.',
          metric: '75%',
          metricLabel: 'Reducción de tiempo',
          icon: 'AutoIcon'
        },
        {
          id: 3,
          title: 'Analítica Avanzada',
          description: 'Reportes detallados y análisis predictivo para optimizar operaciones.',
          metric: '40%',
          metricLabel: 'Mejora en eficiencia',
          icon: 'AnalyticsIcon'
        },
        {
          id: 4,
          title: 'Integración API',
          description: 'Conecta nuestros servicios directamente con tus sistemas empresariales.',
          metric: '100+',
          metricLabel: 'Integraciones',
          icon: 'APIIcon'
        }
      ],
      processSteps: [
        {
          id: 1,
          title: 'Análisis de Necesidades',
          description: 'Evaluamos tus requerimientos específicos y diseñamos una solución personalizada.'
        },
        {
          id: 2,
          title: 'Planificación Estratégica',
          description: 'Desarrollamos un plan detallado con rutas optimizadas y recursos asignados.'
        },
        {
          id: 3,
          title: 'Ejecución y Monitoreo',
          description: 'Implementamos la solución con seguimiento continuo y ajustes en tiempo real.'
        },
        {
          id: 4,
          title: 'Análisis y Optimización',
          description: 'Evaluamos resultados y optimizamos procesos para mejora continua.'
        }
      ]
    }
  },
  mounted() {
    // Auto-rotate benefits
    setInterval(() => {
      this.activeBenefit = (this.activeBenefit + 1) % this.benefits.length
    }, 4000)
    
    // Auto-rotate process steps
    setInterval(() => {
      this.activeStep = (this.activeStep + 1) % this.processSteps.length
    }, 3000)
  },
  components: {
    ExperienceIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <polygon points="12,2 15.09,8.26 22,9 17,14.74 18.18,21.02 12,17.77 5.82,21.02 7,14.74 2,9 8.91,8.26"></polygon>
        </svg>
      `
    },
    TechIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <rect x="2" y="3" width="20" height="14" rx="2" ry="2"></rect>
          <line x1="8" y1="21" x2="16" y2="21"></line>
          <line x1="12" y1="17" x2="12" y2="21"></line>
        </svg>
      `
    },
    CoverageIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <circle cx="12" cy="12" r="10"></circle>
          <line x1="2" y1="12" x2="22" y2="12"></line>
          <path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"></path>
        </svg>
      `
    },
    SupportIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2z"></path>
          <path d="M12 6v6l4 2"></path>
        </svg>
      `
    },
    GPSIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <polygon points="3,11 22,2 13,21 11,13 3,11"></polygon>
        </svg>
      `
    },
    AutoIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <circle cx="12" cy="12" r="3"></circle>
          <path d="M12 1v6m0 6v6m11-7h-6m-6 0H1"></path>
        </svg>
      `
    },
    AnalyticsIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <polyline points="22,12 18,12 15,21 9,3 6,12 2,12"></polyline>
        </svg>
      `
    },
    APIIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path>
          <rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect>
        </svg>
      `
    }
  }
}
</script>

<style scoped>
.features-section {
  padding: 6rem 0;
  background: #ffffff;
}

.features-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

/* Benefits Section */
.benefits-section {
  margin-bottom: 6rem;
}

.benefits-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.section-title {
  font-size: 3rem;
  font-weight: 800;
  color: #2a3550;
  margin-bottom: 1.5rem;
  line-height: 1.1;
  letter-spacing: -1px;
}

.gradient-text {
  background: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-description {
  font-size: 1.2rem;
  color: #666;
  line-height: 1.6;
  margin-bottom: 2rem;
}

.benefits-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.benefit-item {
  display: flex;
  gap: 1rem;
  padding: 1.5rem;
  border-radius: 15px;
  transition: all 0.3s ease;
  cursor: pointer;
}

.benefit-item:hover,
.benefit-item.active {
  background: rgba(64, 75, 105, 0.05);
  transform: translateX(10px);
}

.benefit-icon {
  color: #404b69;
  flex-shrink: 0;
  display: flex;
  align-items: center;
}

.benefit-title {
  font-size: 1.25rem;
  font-weight: 700;
  color: #2a3550;
  margin-bottom: 0.5rem;
}

.benefit-description {
  color: #666;
  line-height: 1.5;
}

.benefits-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.visual-chart {
  background: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  border-radius: 20px;
  padding: 2rem;
  color: white;
  width: 100%;
  max-width: 400px;
}

.chart-container {
  display: flex;
  align-items: end;
  gap: 1rem;
  height: 200px;
}

.chart-bar {
  flex: 1;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 8px 8px 0 0;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 1rem 0.5rem 0.5rem;
  text-align: center;
  transition: height 0.5s ease;
  position: relative;
}

.chart-value {
  font-weight: 700;
  font-size: 1.1rem;
}

.chart-label {
  font-size: 0.8rem;
  opacity: 0.9;
  writing-mode: vertical-lr;
  text-orientation: mixed;
}

/* Features Grid */
.features-grid-section {
  margin-bottom: 6rem;
}

.grid-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-subtitle {
  font-size: 1.1rem;
  color: #666;
  max-width: 600px;
  margin: 0 auto;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.feature-card {
  background: white;
  border: 2px solid rgba(64, 75, 105, 0.1);
  border-radius: 15px;
  padding: 2rem;
  text-align: center;
  transition: all 0.3s ease;
}

.feature-card:hover {
  border-color: #404b69;
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(64, 75, 105, 0.15);
}

.feature-icon {
  color: #404b69;
  margin-bottom: 1rem;
  display: flex;
  justify-content: center;
}

.feature-title {
  font-size: 1.25rem;
  font-weight: 700;
  color: #2a3550;
  margin-bottom: 1rem;
}

.feature-description {
  color: #666;
  line-height: 1.5;
  margin-bottom: 1.5rem;
}

.feature-metric {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.25rem;
}

.metric-value {
  font-size: 2rem;
  font-weight: 800;
  color: #404b69;
}

.metric-label {
  font-size: 0.9rem;
  color: #666;
  font-weight: 500;
}

/* Process Timeline */
.process-section {
  text-align: center;
}

.process-timeline {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
  position: relative;
}

.process-step {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  position: relative;
  transition: all 0.3s ease;
}

.process-step.active .step-number {
  background: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  color: white;
  transform: scale(1.1);
}

.step-number {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background: rgba(64, 75, 105, 0.1);
  color: #404b69;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
  transition: all 0.3s ease;
}

.step-content {
  max-width: 200px;
}

.step-title {
  font-size: 1.1rem;
  font-weight: 700;
  color: #2a3550;
  margin-bottom: 0.5rem;
}

.step-description {
  color: #666;
  font-size: 0.9rem;
  line-height: 1.4;
}

/* Mobile Styles */
@media screen and (max-width: 768px) {
  .benefits-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .section-title {
    font-size: 2.5rem;
  }
  
  .features-grid {
    grid-template-columns: 1fr;
  }
  
  .process-timeline {
    grid-template-columns: 1fr;
  }
  
  .chart-container {
    height: 150px;
  }
}

@media screen and (max-width: 480px) {
  .section-title {
    font-size: 2rem;
  }
  
  .benefit-item {
    padding: 1rem;
  }
  
  .feature-card {
    padding: 1.5rem;
  }
}
</style>