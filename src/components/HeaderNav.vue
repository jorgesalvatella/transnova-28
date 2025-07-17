<template>
  <header class="header-nav">
    <nav class="navbar">
      <div class="nav-container">
        <!-- Logo -->
        <div class="nav-logo">
          <img
            src="https://imagenes.transnova28.com.mx/tranpo.png"
            alt="Transnova 28"
            class="logo-img"
          />
          <span class="logo-text">Transnova 28</span>
        </div>

        <!-- Desktop Navigation -->
        <ul class="nav-menu" :class="{ active: isMenuOpen }">
          <li class="nav-item">
            <a href="#inicio" class="nav-link" @click="closeMenu">Inicio</a>
          </li>
          <li class="nav-item">
            <a href="#servicios" class="nav-link" @click="closeMenu">Servicios</a>
          </li>
          <li class="nav-item">
            <a href="#nosotros" class="nav-link" @click="closeMenu">Nosotros</a>
          </li>
          <li class="nav-item">
            <a href="#contacto" class="nav-link" @click="closeMenu">Contacto</a>
          </li>
          <li class="nav-item">
            <a href="https://wa.me/5219842039535" class="btn-quote" target="_blank">Cotizar</a>
          </li>
        </ul>

        <!-- Mobile Menu Toggle -->
        <div class="nav-toggle" @click="toggleMenu" :class="{ active: isMenuOpen }">
          <span class="bar"></span>
          <span class="bar"></span>
          <span class="bar"></span>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'HeaderNav',
  data() {
    return {
      isMenuOpen: false,
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
    closeMenu() {
      this.isMenuOpen = false
    },
  },
  mounted() {
    // Close menu when clicking outside
    document.addEventListener('click', (e) => {
      if (!this.$el.contains(e.target)) {
        this.isMenuOpen = false
      }
    })
  },
}
</script>

<style scoped>
.header-nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background: #404b69;
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.navbar {
  padding: 1rem 0;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
  display: flex;
  justify-content: space-between;
}

.nav-logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-right: 2rem;
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
  color: white;
  letter-spacing: -0.5px;
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 2rem;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-link {
  color: whitesmoke;
  text-decoration: none;
  font-weight: 500;
  font-size: 0.95rem;
  transition: color 0.3s ease;
  position: relative;
  margin-left: 1rem;
}

.nav-link:hover {
  color: black;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: #404b69;
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
}

.btn-quote {
  background: white;
  color: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  border: none;
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  font-weight: 600;
  font-size: 0.9rem;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(64, 75, 105, 0.3);
  text-decoration: none;
}

.btn-quote:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(64, 75, 105, 0.4);
}

.nav-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  padding: 0.5rem;
}

.bar {
  width: 25px;
  height: 3px;
  background: #2a3550;
  margin: 3px 0;
  transition: 0.3s;
  border-radius: 2px;
}

.nav-toggle.active .bar:nth-child(1) {
  transform: rotate(-45deg) translate(-5px, 6px);
}

.nav-toggle.active .bar:nth-child(2) {
  opacity: 0;
}

.nav-toggle.active .bar:nth-child(3) {
  transform: rotate(45deg) translate(-5px, -6px);
}

/* Mobile Styles */
@media screen and (max-width: 768px) {
  .nav-menu {
    position: fixed;
    left: -100%;
    top: 70px;
    flex-direction: column;
    background: rgba(255, 255, 255, 0.98);
    backdrop-filter: blur(10px);
    width: 100%;
    text-align: center;
    transition: 0.3s;
    box-shadow: 0 10px 27px rgba(0, 0, 0, 0.05);
    padding: 2rem 0;
    gap: 1.5rem;
  }

  .nav-menu.active {
    left: 0;
  }

  .nav-toggle {
    display: flex;
  }

  .btn-quote {
    margin-top: 1rem;
  }
}

/* Scroll effect */
.header-nav.scrolled {
  background: rgba(255, 255, 255, 0.98);
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
}
</style>
