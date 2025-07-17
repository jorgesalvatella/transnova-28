<template>
  <section class="about-section" id="nosotros">
    <div class="about-container">
      <!-- Company Story -->
      <div class="company-story">
        <div class="story-content">
          <div class="story-text">
            <!-- Imagen del equipo/oficina -->
            <div class="about-image-container">
              <img
                :src="IMAGE_URLS.URL_FOTO_EQUIPO_OFICINA"
                alt="Equipo profesional de Transnova 28"
                class="about-image holographic-transport"
              />
            </div>
            <div class="section-badge">Nuestra Historia</div>
            <h2 class="section-title">
              Conectando México con
              <span class="gradient-text">soluciones inteligentes</span>
            </h2>
            <p class="story-description">
              Desde 2010, hemos revolucionado la logística en México. Lo que comenzó como una
              pequeña empresa familiar se ha convertido en líder nacional en soluciones de
              transporte y distribución, sirviendo a más de 500 empresas en todo el país.
            </p>

            <div class="story-highlights">
              <div class="highlight-item">
                <div class="highlight-icon">
                  <svg
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                  >
                    <path d="M9 11H1v12h8V11z"></path>
                    <path d="M23 11h-8v12h8V11z"></path>
                    <path d="M15 7h-6v4h6V7z"></path>
                    <path d="M9 7V1h6v6"></path>
                  </svg>
                </div>
                <div>
                  <h4>Misión</h4>
                  <p>Optimizar cadenas de suministro con tecnología e innovación</p>
                </div>
              </div>

              <div class="highlight-item">
                <div class="highlight-icon">
                  <svg
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                  >
                    <circle cx="12" cy="12" r="10"></circle>
                    <polygon points="10,8 16,12 10,16 10,8"></polygon>
                  </svg>
                </div>
                <div>
                  <h4>Visión</h4>
                  <p>Ser la red logística más confiable y eficiente de América Latina</p>
                </div>
              </div>
            </div>
          </div>

          <div class="story-visual">
            <div class="timeline-container">
              <div class="timeline-line"></div>
              <div
                v-for="(milestone, index) in milestones"
                :key="milestone.id"
                class="timeline-item"
                :class="{ active: activeMilestone === index }"
                @mouseenter="activeMilestone = index"
              >
                <div class="timeline-dot"></div>
                <div class="timeline-content">
                  <div class="timeline-year">{{ milestone.year }}</div>
                  <div class="timeline-title">{{ milestone.title }}</div>
                  <div class="timeline-description">{{ milestone.description }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Values Section -->
      <div class="values-section">
        <h2 class="section-title">Nuestros Valores</h2>
        <div class="values-grid">
          <div v-for="value in companyValues" :key="value.id" class="value-card">
            <div class="value-icon">
              <component :is="value.icon" />
            </div>
            <h3 class="value-title">{{ value.title }}</h3>
            <p class="value-description">{{ value.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { IMAGE_URLS } from '@/constants/images'

export default {
  name: 'AboutSection',
  data() {
    return {
      IMAGE_URLS,
      activeMilestone: 0,
      hoveredMember: null,
      milestones: [
        {
          id: 1,
          year: '2010',
          title: 'Fundación',
          description: 'Inicio de operaciones con 3 camiones y un gran sueño',
        },
        {
          id: 2,
          year: '2015',
          title: 'Expansión Regional',
          description: 'Apertura  de distribución en 3 estados',
        },
        {
          id: 3,
          year: '2018',
          title: 'Transformación Digital',
          description: 'Implementación de tecnología GPS y plataforma web',
        },

        {
          id: 5,
          year: '2023',
          title: 'Líder Nacional',
          description: 'Reconocidos como empresa líder en logística mexicana',
        },
      ],
      teamMembers: [
        {
          id: 1,
          name: 'Carlos Mendoza',
          role: 'Director General',
          description:
            'Más de 15 años liderando proyectos de logística y transformación empresarial.',
          image:
            'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=300&h=300&fit=crop&crop=face',
        },
        {
          id: 2,
          name: 'Ana García',
          role: 'Directora de Operaciones',
          description:
            'Especialista en optimización de procesos y gestión de cadenas de suministro.',
          image:
            'https://images.unsplash.com/photo-1494790108755-2616b612b5bc?w=300&h=300&fit=crop&crop=face',
        },
        {
          id: 3,
          name: 'Miguel Torres',
          role: 'Director de Tecnología',
          description: 'Experto en soluciones tecnológicas aplicadas a la industria logística.',
          image:
            'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=300&h=300&fit=crop&crop=face',
        },
        {
          id: 4,
          name: 'Laura Jiménez',
          role: 'Directora Comercial',
          description:
            'Especialista en desarrollo de negocios y relaciones estratégicas con clientes.',
          image:
            'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=300&h=300&fit=crop&crop=face',
        },
      ],
      companyValues: [
        {
          id: 1,
          title: 'Confiabilidad',
          description: 'Cumplimos nuestras promesas y entregamos resultados consistentes.',
          icon: 'ReliabilityIcon',
        },
        {
          id: 2,
          title: 'Innovación',
          description: 'Adoptamos tecnologías emergentes para mejorar continuamente.',
          icon: 'InnovationIcon',
        },
        {
          id: 3,
          title: 'Excelencia',
          description: 'Buscamos la perfección en cada proceso y servicio que ofrecemos.',
          icon: 'ExcellenceIcon',
        },
        {
          id: 4,
          title: 'Sustentabilidad',
          description: 'Comprometidos con prácticas responsables con el medio ambiente.',
          icon: 'SustainabilityIcon',
        },
      ],
      certifications: [
        {
          id: 1,
          name: 'ISO 9001:2015',
          description: 'Sistemas de Gestión de Calidad',
          logo: 'https://via.placeholder.com/80x80/404b69/ffffff?text=ISO',
        },
        {
          id: 2,
          name: 'C-TPAT',
          description: 'Customs-Trade Partnership Against Terrorism',
          logo: 'https://via.placeholder.com/80x80/404b69/ffffff?text=CTPAT',
        },
        {
          id: 3,
          name: 'OEA México',
          description: 'Operador Económico Autorizado',
          logo: 'https://via.placeholder.com/80x80/404b69/ffffff?text=OEA',
        },
        {
          id: 4,
          name: 'FAST',
          description: 'Free and Secure Trade Program',
          logo: 'https://via.placeholder.com/80x80/404b69/ffffff?text=FAST',
        },
      ],
    }
  },
  mounted() {
    // Auto-rotate milestones
    setInterval(() => {
      this.activeMilestone = (this.activeMilestone + 1) % this.milestones.length
    }, 3000)
  },
  components: {
    ReliabilityIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path>
          <path d="M9 12l2 2 4-4"></path>
        </svg>
      `,
    },
    InnovationIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
          <path d="M12 7v5l3 3"></path>
        </svg>
      `,
    },
    ExcellenceIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <polygon points="12,2 15.09,8.26 22,9 17,14.74 18.18,21.02 12,17.77 5.82,21.02 7,14.74 2,9 8.91,8.26"></polygon>
        </svg>
      `,
    },
    SustainabilityIcon: {
      template: `
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M17 8c0 7-5 13-5 13s-5-6-5-13a5 5 0 0 1 10 0z"></path>
          <circle cx="12" cy="8" r="3"></circle>
        </svg>
      `,
    },
  },
}
</script>

<style scoped>
.about-section {
  padding: 6rem 0;
  background: linear-gradient(135deg, #f8fafc 0%, #ffffff 100%);
}

.about-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

/* Company Story */
.company-story {
  margin-bottom: 6rem;
}

.story-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  position: relative;
}

/* About Image Container */
.about-image-container {
  position: absolute;
  top: -50px;
  left: -80px;
  width: 220px;
  height: 160px;
  z-index: 1;
  opacity: 0.7;
}

.about-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 16px;
}

.section-badge {
  display: inline-block;
  background: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 600;
  margin-bottom: 1rem;
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

.story-description {
  font-size: 1.1rem;
  color: #666;
  line-height: 1.7;
  margin-bottom: 2rem;
}

.story-highlights {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.highlight-item {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
}

.highlight-icon {
  color: #404b69;
  flex-shrink: 0;
}

.highlight-item h4 {
  font-size: 1.1rem;
  font-weight: 700;
  color: #2a3550;
  margin-bottom: 0.25rem;
}

.highlight-item p {
  color: #666;
  font-size: 0.95rem;
  line-height: 1.5;
}

.timeline-container {
  position: relative;
  padding: 2rem 0;
}

.timeline-line {
  position: absolute;
  left: 20px;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(180deg, #404b69 0%, #2a3550 100%);
}

.timeline-item {
  position: relative;
  padding-left: 3rem;
  margin-bottom: 2rem;
  cursor: pointer;
  transition: all 0.3s ease;
}

.timeline-item:hover,
.timeline-item.active {
  transform: translateX(10px);
}

.timeline-dot {
  position: absolute;
  left: -2rem;
  top: 0.5rem;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #404b69;
  border: 3px solid white;
  box-shadow: 0 0 0 3px rgba(64, 75, 105, 0.2);
}

.timeline-item.active .timeline-dot {
  background: #2a3550;
  transform: scale(1.2);
}

.timeline-year {
  font-size: 1.25rem;
  font-weight: 800;
  color: #404b69;
  margin-bottom: 0.25rem;
}

.timeline-title {
  font-size: 1rem;
  font-weight: 700;
  color: #2a3550;
  margin-bottom: 0.25rem;
}

.timeline-description {
  font-size: 0.9rem;
  color: #666;
  line-height: 1.4;
}

/* Team Section */
.team-section {
  margin-bottom: 6rem;
}

.team-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-subtitle {
  font-size: 1.1rem;
  color: #666;
  margin-top: 1rem;
}

.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.team-card {
  background: white;
  border-radius: 20px;
  padding: 2rem;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.team-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.15);
}

.member-avatar {
  position: relative;
  width: 120px;
  height: 120px;
  margin: 0 auto 1.5rem;
  border-radius: 50%;
  overflow: hidden;
}

.member-avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.avatar-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(64, 75, 105, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.team-card:hover .avatar-overlay {
  opacity: 1;
}

.social-links {
  display: flex;
  gap: 0.5rem;
}

.social-link {
  color: white;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: scale(1.1);
}

.member-name {
  font-size: 1.25rem;
  font-weight: 700;
  color: #2a3550;
  margin-bottom: 0.5rem;
}

.member-role {
  color: #404b69;
  font-weight: 600;
  margin-bottom: 1rem;
}

.member-description {
  color: #666;
  font-size: 0.9rem;
  line-height: 1.5;
}

/* Values Section */
.values-section {
  margin-bottom: 6rem;
  text-align: center;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.value-card {
  padding: 2rem;
  text-align: center;
  transition: all 0.3s ease;
}

.value-card:hover {
  transform: translateY(-5px);
}

.value-icon {
  color: #404b69;
  margin-bottom: 1rem;
  display: flex;
  justify-content: center;
}

.value-title {
  font-size: 1.25rem;
  font-weight: 700;
  color: #2a3550;
  margin-bottom: 1rem;
}

.value-description {
  color: #666;
  line-height: 1.5;
}

/* Certifications */
.certifications-section {
  text-align: center;
}

.certifications-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.certification-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.5rem;
  background: white;
  border-radius: 15px;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
}

.certification-item:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.cert-logo img {
  width: 60px;
  height: 60px;
  object-fit: contain;
  border-radius: 8px;
}

.cert-name {
  font-size: 1rem;
  font-weight: 700;
  color: #2a3550;
  margin-bottom: 0.25rem;
}

.cert-description {
  font-size: 0.85rem;
  color: #666;
  line-height: 1.4;
}

/* Mobile Styles */
@media screen and (max-width: 768px) {
  .story-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .about-image-container {
    display: none;
  }

  .section-title {
    font-size: 2.5rem;
  }

  .team-grid {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  }

  .values-grid {
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  }

  .certifications-grid {
    grid-template-columns: 1fr;
  }
}

@media screen and (max-width: 480px) {
  .section-title {
    font-size: 2rem;
  }

  .team-card {
    padding: 1.5rem;
  }

  .value-card {
    padding: 1.5rem;
  }
}
</style>
