<template>
  <div>
    <!-- Contact Section -->
    <section class="contact-section" id="contacto">
      <!-- Imagen decorativa fija -->
      <div class="contact-decorative-container">
        <img
          :src="IMAGE_URLS.URL_FOTO_TECNOLOGIA_RASTREO"
          alt="Tecnología de rastreo GPS"
          class="contact-decorative-image transport-image"
        />
      </div>
      <div class="contact-container">
        <div class="contact-content">
          <div class="contact-info">
            <h2 class="section-title">
              ¿Listo para optimizar tu
              <span class="gradient-text">logística</span>?
            </h2>
            <p class="section-description">
              Contacta con nuestros especialistas y descubre cómo podemos transformar tu cadena de
              suministro con soluciones personalizadas.
            </p>

            <div class="contact-methods">
              <div class="contact-method">
                <div class="method-icon">
                  <svg
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                  >
                    <path
                      d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"
                    ></path>
                  </svg>
                </div>
                <div class="method-info">
                  <h4>Contacto GDL</h4>
                  <p>33 34 64 6494 | 33 34 66 1506</p>
                  <span>Oficina GDL: 33 38 34 6744</span>
                </div>
              </div>

              <div class="contact-method">
                <div class="method-icon">
                  <svg
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                  >
                    <path
                      d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"
                    ></path>
                  </svg>
                </div>
                <div class="method-info">
                  <h4>Llamadas Cancún</h4>
                  <p>984 197 7121</p>
                  <span>WhatsApp: 984 203 9535</span>
                </div>
              </div>

              <div class="contact-method">
                <div class="method-icon">
                  <svg
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                  >
                    <path
                      d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
                    ></path>
                    <polyline points="22,6 12,13 2,6"></polyline>
                  </svg>
                </div>
                <div class="method-info">
                  <h4>Email</h4>
                  <p>admon@transnova28.com.mx</p>
                  <span>Respuesta en 24 horas</span>
                </div>
              </div>

              <div class="contact-method">
                <div class="method-icon">
                  <svg
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                  >
                    <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
                    <circle cx="12" cy="10" r="3"></circle>
                  </svg>
                </div>
                <div class="method-info">
                  <h4>Oficina Central</h4>
                  <p>GDL, Jalisco</p>
                </div>
              </div>
            </div>
          </div>

          <div class="contact-form-container">
            <form class="contact-form" @submit.prevent="submitForm">
              <div class="form-header">
                <h3>Contáctanos</h3>
                <p>Completa el formulario y te contactaremos en menos de 24 horas</p>
              </div>

              <div class="form-group">
                <input
                  type="text"
                  v-model="form.name"
                  placeholder="Nombre completo *"
                  class="form-input"
                  :class="{ error: errors.name }"
                  required
                />
                <span v-if="errors.name" class="error-message">{{ errors.name }}</span>
              </div>

              <div class="form-row">
                <div class="form-group">
                  <input
                    type="email"
                    v-model="form.email"
                    placeholder="Email *"
                    class="form-input"
                    :class="{ error: errors.email }"
                    required
                  />
                  <span v-if="errors.email" class="error-message">{{ errors.email }}</span>
                </div>

                <div class="form-group">
                  <input
                    type="tel"
                    v-model="form.phone"
                    placeholder="Teléfono *"
                    class="form-input"
                    :class="{ error: errors.phone }"
                    required
                  />
                  <span v-if="errors.phone" class="error-message">{{ errors.phone }}</span>
                </div>
              </div>

              <div class="form-group">
                <input
                  type="text"
                  v-model="form.company"
                  placeholder="Empresa"
                  class="form-input"
                />
              </div>

              <div class="form-group">
                <select
                  v-model="form.service"
                  class="form-select"
                  :class="{ error: errors.service }"
                  required
                >
                  <option value="">Tipo de servicio *</option>
                  <option value="transporte">Transporte Terrestre</option>
                  <option value="almacenamiento">Almacenamiento</option>
                  <option value="distribucion">Distribución</option>
                  <option value="logistica">Logística Integral</option>
                  <option value="especializado">Transporte Especializado</option>
                  <option value="tecnologia">Tecnología y Rastreo</option>
                </select>
                <span v-if="errors.service" class="error-message">{{ errors.service }}</span>
              </div>

              <div class="form-group">
                <textarea
                  v-model="form.message"
                  placeholder="Cuéntanos sobre tu proyecto o necesidades específicas..."
                  class="form-textarea"
                  rows="4"
                ></textarea>
              </div>

              <button
                type="submit"
                class="btn-submit"
                :disabled="isSubmitting"
                :class="{ loading: isSubmitting }"
              >
                <span v-if="!isSubmitting">Enviar Solicitud</span>
                <span v-else>Enviando...</span>
                <svg
                  v-if="!isSubmitting"
                  class="submit-arrow"
                  width="20"
                  height="20"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <line x1="22" y1="2" x2="11" y2="13"></line>
                  <polygon points="22,2 15,22 11,13 2,9 22,2"></polygon>
                </svg>
              </button>

              <p class="form-privacy">
                Al enviar este formulario, aceptas nuestra
                <a href="#" class="privacy-link">política de privacidad</a>
              </p>
            </form>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="footer-container">
        <div class="footer-content">
          <!-- Company Info -->
          <div class="footer-section">
            <div class="footer-logo">
              <img
                src="https://imagenes.transnova28.com.mx/tranpo.png"
                alt="Transnova 28"
                class="logo-img"
              />
              <span class="logo-text">Transnova 28</span>
            </div>
            <p class="footer-description">
              Líder en soluciones logísticas integrales, conectando México con el mundo a través de
              tecnología avanzada y servicios confiables.
            </p>
            <div class="social-links">
              <a href="#" class="social-link" aria-label="Facebook">
                <svg
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <path
                    d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"
                  ></path>
                </svg>
              </a>
              <a href="#" class="social-link" aria-label="Twitter">
                <svg
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <path d="M4 4l11.733 16h4.267l-11.733 -16z"></path>
                  <path d="M4 20l6.768 -6.768m2.46 -2.46l6.772 -6.772"></path>
                </svg>
              </a>
              <a href="#" class="social-link" aria-label="LinkedIn">
                <svg
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <path
                    d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"
                  ></path>
                  <rect x="2" y="9" width="4" height="12"></rect>
                  <circle cx="4" cy="4" r="2"></circle>
                </svg>
              </a>
              <a href="#" class="social-link" aria-label="Instagram">
                <svg
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
                  <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
                  <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
                </svg>
              </a>
            </div>
          </div>

          <!-- Quick Links -->
          <div class="footer-section">
            <h4 class="footer-title">Enlaces Rápidos</h4>
            <ul class="footer-links">
              <li><a href="#inicio">Inicio</a></li>
              <li><a href="#servicios">Servicios</a></li>
              <li><a href="#nosotros">Nosotros</a></li>
              <li><a href="#contacto">Contacto</a></li>
              <li><a href="#">Blog</a></li>
              <li><a href="#">Carreras</a></li>
            </ul>
          </div>

          <!-- Contact Info -->
          <div class="footer-section">
            <h4 class="footer-title">Contacto</h4>
            <div class="footer-contact">
              <div class="contact-item">
                <svg
                  width="16"
                  height="16"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
                  <circle cx="12" cy="10" r="3"></circle>
                </svg>
                <span>Quintana Roo <br />Jalisco<br />CDMX, México</span>
              </div>
              <div class="contact-item">
                <svg
                  width="16"
                  height="16"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <path
                    d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"
                  ></path>
                </svg>
                <span>GDL: 33 34 64 6494 | Cancún: 984 197 7121</span>
              </div>
              <div class="contact-item">
                <svg
                  width="16"
                  height="16"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <path
                    d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
                  ></path>
                  <polyline points="22,6 12,13 2,6"></polyline>
                </svg>
                <span>admon@transnova28.com.mx</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Footer Bottom -->
        <div class="footer-bottom">
          <div class="footer-bottom-content">
            <p>&copy; 2024 Transnova 28. Todos los derechos reservados.</p>
            <div class="footer-legal">
              <a href="#">Política de Privacidad</a>
              <a href="#">Términos de Servicio</a>
              <a href="#">Cookies</a>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import { IMAGE_URLS } from '@/constants/images'

export default {
  name: 'ContactFooter',
  data() {
    return {
      IMAGE_URLS,
      form: {
        name: '',
        email: '',
        phone: '',
        company: '',
        service: '',
        message: '',
      },
      errors: {},
      isSubmitting: false,
    }
  },
  methods: {
    validateForm() {
      this.errors = {}

      if (!this.form.name.trim()) {
        this.errors.name = 'El nombre es requerido'
      }

      if (!this.form.email.trim()) {
        this.errors.email = 'El email es requerido'
      } else if (!this.isValidEmail(this.form.email)) {
        this.errors.email = 'Email inválido'
      }

      if (!this.form.phone.trim()) {
        this.errors.phone = 'El teléfono es requerido'
      }

      if (!this.form.service) {
        this.errors.service = 'Selecciona un tipo de servicio'
      }

      return Object.keys(this.errors).length === 0
    },

    isValidEmail(email) {
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
      return emailRegex.test(email)
    },

    async submitForm() {
      if (!this.validateForm()) {
        return
      }

      this.isSubmitting = true

      try {
        // Simulate API call
        await new Promise((resolve) => setTimeout(resolve, 2000))

        // Reset form
        this.form = {
          name: '',
          email: '',
          phone: '',
          company: '',
          service: '',
          message: '',
        }

        alert('¡Solicitud enviada exitosamente! Te contactaremos pronto.')
      } catch (error) {
        alert('Error al enviar la solicitud. Inténtalo de nuevo.')
      } finally {
        this.isSubmitting = false
      }
    },
  },
}
</script>

<style scoped>
/* Contact Section */
.contact-section {
  padding: 6rem 0;
  background: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  color: white;
  position: relative;
  overflow: hidden;
}

/* Contact Decorative Image */
.contact-decorative-container {
  position: absolute;
  top: 10%;
  right: 5%;
  width: 300px;
  height: 200px;
  z-index: 1;
}

.contact-decorative-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 18px;
  border: 2px solid rgba(255, 255, 255, 0.3);
  box-shadow:
    0 10px 30px rgba(0, 0, 0, 0.3),
    0 5px 15px rgba(64, 75, 105, 0.2);
  transition: all 0.3s ease;
  left: 60px;
  top: 200px;
}

.contact-decorative-image:hover {
  transform: translateY(-5px) scale(1.02);
  border-color: rgba(255, 255, 255, 0.5);
  box-shadow:
    0 15px 40px rgba(0, 0, 0, 0.4),
    0 8px 20px rgba(64, 75, 105, 0.3);
}

.contact-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.section-title {
  font-size: 3rem;
  font-weight: 800;
  margin-bottom: 1.5rem;
  line-height: 1.1;
  letter-spacing: -1px;
}

.gradient-text {
  background: linear-gradient(135deg, #60a5fa 0%, #34d399 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-description {
  font-size: 1.1rem;
  opacity: 0.9;
  line-height: 1.6;
  margin-bottom: 3rem;
  position: relative;
  z-index: 2;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.contact-method {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
}

.method-icon {
  background: rgba(255, 255, 255, 0.1);
  padding: 1rem;
  border-radius: 12px;
  flex-shrink: 0;
}

.method-info h4 {
  font-size: 1.1rem;
  font-weight: 700;
  margin-bottom: 0.25rem;
}

.method-info p {
  font-size: 1rem;
  margin-bottom: 0.25rem;
}

.method-info span {
  font-size: 0.9rem;
  opacity: 0.8;
}

/* Contact Form */
.contact-form-container {
  background-image: url('https://imagenes.transnova28.com.mx/Transporte%20Logistico/WhatsApp%20Image%202025-07-16%20at%2017.59.44%20(4).jpeg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  border-radius: 20px;
  padding: 2.5rem;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.1);
  position: relative;
  overflow: hidden;
}

.contact-form-container::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(255, 255, 255, 0.92);
  border-radius: 20px;
  z-index: 1;
}

.contact-form {
  position: relative;
  z-index: 2;
}

.form-header {
  text-align: center;
  margin-bottom: 2rem;
}

.form-header h3 {
  font-size: 1.5rem;
  font-weight: 700;
  color: #2a3550;
  margin-bottom: 0.5rem;
}

.form-header p {
  color: #666;
  font-size: 0.9rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.form-input,
.form-select,
.form-textarea {
  width: 100%;
  padding: 1rem;
  border: 2px solid #e2e8f0;
  border-radius: 12px;
  font-size: 1rem;
  transition: all 0.3s ease;
  background: white;
  color: #2a3550;
}

.form-input:focus,
.form-select:focus,
.form-textarea:focus {
  outline: none;
  border-color: #404b69;
  box-shadow: 0 0 0 3px rgba(64, 75, 105, 0.1);
}

.form-input.error,
.form-select.error {
  border-color: #ef4444;
}

.form-textarea {
  resize: vertical;
  min-height: 100px;
}

.error-message {
  color: #ef4444;
  font-size: 0.85rem;
  margin-top: 0.25rem;
  display: block;
}

.btn-submit {
  width: 100%;
  background: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  color: white;
  border: none;
  padding: 1rem 2rem;
  border-radius: 12px;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.btn-submit:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(64, 75, 105, 0.3);
}

.btn-submit:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.btn-submit.loading {
  animation: pulse 2s infinite;
}

.submit-arrow {
  transition: transform 0.3s ease;
}

.btn-submit:hover .submit-arrow {
  transform: translateX(3px);
}

.form-privacy {
  text-align: center;
  font-size: 0.85rem;
  color: #666;
}

.privacy-link {
  color: #404b69;
  text-decoration: none;
}

.privacy-link:hover {
  text-decoration: underline;
}

/* Footer */
.footer {
  background: #1a202c;
  color: white;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 3rem;
  padding: 4rem 0 2rem;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.logo-img {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  object-fit: cover;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: 700;
}

.footer-description {
  opacity: 0.8;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.social-links {
  display: flex;
  gap: 0.75rem;
}

.social-link {
  color: white;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
}

.footer-title {
  font-size: 1.25rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.footer-links {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-links li {
  margin-bottom: 0.5rem;
}

.footer-links a {
  color: rgba(255, 255, 255, 0.8);
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: white;
}

.footer-contact {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.contact-item {
  display: flex;
  gap: 0.75rem;
  align-items: flex-start;
}

.contact-item svg {
  color: rgba(255, 255, 255, 0.7);
  flex-shrink: 0;
  margin-top: 0.25rem;
}

.contact-item span {
  opacity: 0.8;
  line-height: 1.5;
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding: 2rem 0;
}

.footer-bottom-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  opacity: 0.8;
}

.footer-legal {
  display: flex;
  gap: 2rem;
}

.footer-legal a {
  color: rgba(255, 255, 255, 0.8);
  text-decoration: none;
  font-size: 0.9rem;
  transition: color 0.3s ease;
}

.footer-legal a:hover {
  color: white;
}

/* Animations */
@keyframes pulse {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0.8;
  }
}

/* Mobile Styles */
@media screen and (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .contact-decorative-container {
    width: 250px;
    height: 160px;
    top: 8%;
    right: 3%;
  }

  .section-title {
    font-size: 2.5rem;
  }

  .contact-form-container {
    padding: 2rem;
  }

  .form-row {
    grid-template-columns: 1fr;
  }

  .footer-bottom-content {
    flex-direction: column;
    gap: 1rem;
    text-align: center;
  }

  .footer-legal {
    gap: 1rem;
  }
}

@media screen and (max-width: 480px) {
  .section-title {
    font-size: 2rem;
  }

  .contact-form-container {
    padding: 1.5rem;
  }

  .footer-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .contact-decorative-container {
    display: none;
  }
}
</style>
