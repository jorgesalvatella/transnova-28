<template>
  <div v-if="isOpen" class="modal-overlay" @click="closeModal">
    <div class="modal-content" @click.stop>
      <div class="modal-header">
        <h3>Contáctanos</h3>
        <button class="close-btn" @click="closeModal">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <line x1="18" y1="6" x2="6" y2="18"></line>
            <line x1="6" y1="6" x2="18" y2="18"></line>
          </svg>
        </button>
      </div>
      
      <div class="contact-options">
        <a :href="`tel:+52${phoneNumbers.gdl1}`" class="contact-option call-option">
          <div class="option-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path>
            </svg>
          </div>
          <div class="option-info">
            <h4>Llamar GDL</h4>
            <p>33 34 64 6494</p>
          </div>
        </a>

        <a :href="`tel:+52${phoneNumbers.cancun}`" class="contact-option call-option">
          <div class="option-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path>
            </svg>
          </div>
          <div class="option-info">
            <h4>Llamar Cancún</h4>
            <p>984 197 7121</p>
          </div>
        </a>

        <a :href="`tel:+52${phoneNumbers.gdl2}`" class="contact-option call-option">
          <div class="option-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path>
            </svg>
          </div>
          <div class="option-info">
            <h4>Oficina GDL</h4>
            <p>33 38 34 6744</p>
          </div>
        </a>

        <a :href="`mailto:${email}`" class="contact-option email-option">
          <div class="option-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
              <polyline points="22,6 12,13 2,6"></polyline>
            </svg>
          </div>
          <div class="option-info">
            <h4>Email</h4>
            <p>admon@transnova28.com.mx</p>
          </div>
        </a>

        <a :href="`https://wa.me/52${phoneNumbers.whatsapp}`" target="_blank" class="contact-option whatsapp-option">
          <div class="option-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
              <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.893 3.488"/>
            </svg>
          </div>
          <div class="option-info">
            <h4>WhatsApp</h4>
            <p>984 203 9535</p>
          </div>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactModal',
  props: {
    isOpen: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      phoneNumbers: {
        gdl1: '3334646494',
        gdl2: '3338346744',
        cancun: '9841977121',
        whatsapp: '9842039535'
      },
      email: 'admon@transnova28.com.mx'
    }
  },
  methods: {
    closeModal() {
      this.$emit('close')
    }
  },
  mounted() {
    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape' && this.isOpen) {
        this.closeModal()
      }
    })
  }
}
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: flex-start;
  justify-content: center;
  z-index: 99999;
  backdrop-filter: blur(5px);
  padding-top: 8rem;
}

.modal-content {
  background: white;
  border-radius: 20px;
  padding: 2rem;
  max-width: 450px;
  width: 90%;
  max-height: 85vh;
  overflow-y: auto;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3);
  position: relative;
  animation: modalSlideIn 0.3s ease-out;
  margin: 2rem;
}

@keyframes modalSlideIn {
  from {
    opacity: 0;
    transform: translateY(-30px) scale(0.95);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.modal-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 2px solid #f1f1f1;
}

.modal-header h3 {
  font-size: 1.5rem;
  font-weight: 700;
  color: #2a3550;
  margin: 0;
}

.close-btn {
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  border-radius: 50%;
  color: #666;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}

.close-btn:hover {
  background: #f1f1f1;
  color: #2a3550;
}

.contact-options {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.contact-option {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  border: 2px solid #e2e8f0;
  border-radius: 12px;
  text-decoration: none;
  color: #2a3550;
  transition: all 0.3s ease;
  background: #f9f9f9;
}

.contact-option:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
  border-color: #404b69;
}

.call-option:hover {
  background: linear-gradient(135deg, #3b82f6, #1d4ed8);
  color: white;
  border-color: #1d4ed8;
}

.email-option:hover {
  background: linear-gradient(135deg, #f59e0b, #d97706);
  color: white;
  border-color: #d97706;
}

.whatsapp-option:hover {
  background: linear-gradient(135deg, #25D366, #128C7E);
  color: white;
  border-color: #128C7E;
}

.option-icon {
  background: rgba(64, 75, 105, 0.1);
  padding: 0.75rem;
  border-radius: 10px;
  flex-shrink: 0;
  transition: all 0.3s ease;
}

.contact-option:hover .option-icon {
  background: rgba(255, 255, 255, 0.2);
}

.option-info h4 {
  font-size: 1rem;
  font-weight: 600;
  margin: 0 0 0.25rem 0;
}

.option-info p {
  font-size: 0.9rem;
  margin: 0;
  opacity: 0.8;
}

.contact-option:hover .option-info p {
  opacity: 1;
}

@media (max-width: 768px) {
  .modal-content {
    max-width: 95%;
    margin: 1rem;
    max-height: 90vh;
  }
}

@media (max-width: 480px) {
  .modal-content {
    padding: 1.5rem;
    margin: 0.5rem;
    max-height: 95vh;
  }
  
  .contact-option {
    padding: 0.75rem;
  }
  
  .option-icon {
    padding: 0.5rem;
  }
  
  .modal-header h3 {
    font-size: 1.25rem;
  }
}
</style>