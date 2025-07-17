<template>
  <div id="app">
    <HeaderNav />
    <main>
      <HeroSection />
      <ServicesSection />
      <FeaturesSection />
      <AboutSection />
      <ContactFooter />
    </main>
  </div>
</template>

<script>
import HeaderNav from './components/HeaderNav.vue'
import HeroSection from './components/HeroSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import FeaturesSection from './components/FeaturesSection.vue'
import AboutSection from './components/AboutSection.vue'
import ContactFooter from './components/ContactFooter.vue'

export default {
  name: 'App',
  components: {
    HeaderNav,
    HeroSection,
    ServicesSection,
    FeaturesSection,
    AboutSection,
    ContactFooter
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  line-height: 1.6;
  color: #333;
  overflow-x: hidden;
}

#app {
  min-height: 100vh;
}

/* Global utility classes */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 8px;
  font-weight: 600;
  text-decoration: none;
  cursor: pointer;
  transition: all 0.3s ease;
  gap: 0.5rem;
}

.btn-primary {
  background: linear-gradient(135deg, #404b69 0%, #2a3550 100%);
  color: white;
  box-shadow: 0 4px 15px rgba(64, 75, 105, 0.3);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(64, 75, 105, 0.4);
}

.btn-secondary {
  background: transparent;
  color: #404b69;
  border: 2px solid #404b69;
}

.btn-secondary:hover {
  background: #404b69;
  color: white;
}

/* Responsive text sizes */
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}

/* Smooth scrolling for anchor links */
html {
  scroll-padding-top: 80px;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background: #404b69;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: #2a3550;
}

/* Futuristic Transport Image Classes */
.transport-image {
  opacity: 0.85;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(8px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 12px;
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
}

.transport-image::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.6s ease;
}

.transport-image:hover {
  opacity: 1;
  transform: scale(1.02);
  box-shadow: 0 15px 35px rgba(64, 75, 105, 0.3);
  border-color: rgba(64, 75, 105, 0.4);
}

.transport-image:hover::before {
  left: 100%;
}

/* Futuristic Trailer/Truck Images */
.futuristic-trailer {
  background: linear-gradient(135deg, rgba(64, 75, 105, 0.1), rgba(42, 53, 80, 0.15));
  backdrop-filter: blur(15px);
  border: 2px solid rgba(64, 75, 105, 0.3);
  border-radius: 20px;
  opacity: 0.9;
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
}

.futuristic-trailer::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(circle at 50% 50%, rgba(64, 75, 105, 0.1), transparent 70%);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.futuristic-trailer:hover {
  opacity: 1;
  transform: translateY(-8px) scale(1.03);
  box-shadow: 
    0 25px 50px rgba(64, 75, 105, 0.25),
    0 0 30px rgba(64, 75, 105, 0.1);
  border-color: rgba(64, 75, 105, 0.5);
}

.futuristic-trailer:hover::after {
  opacity: 1;
}

/* Holographic Effect */
.holographic-transport {
  background: linear-gradient(45deg, rgba(64, 75, 105, 0.1), rgba(42, 53, 80, 0.1));
  backdrop-filter: blur(12px);
  border: 1px solid rgba(64, 75, 105, 0.2);
  border-radius: 16px;
  opacity: 0.8;
  position: relative;
  overflow: hidden;
  transition: all 0.4s ease;
}

.holographic-transport::before {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: linear-gradient(45deg, #404b69, #2a3550, #404b69);
  background-size: 200% 200%;
  border-radius: 16px;
  opacity: 0;
  z-index: -1;
  animation: borderGlow 3s ease-in-out infinite;
  transition: opacity 0.3s ease;
}

.holographic-transport:hover::before {
  opacity: 1;
}

.holographic-transport:hover {
  opacity: 1;
  transform: scale(1.05);
  box-shadow: 0 20px 40px rgba(64, 75, 105, 0.3);
}

@keyframes borderGlow {
  0%, 100% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
}

/* Glass Morphism for Images */
.glass-transport {
  background: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 24px;
  opacity: 0.85;
  transition: all 0.4s ease;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
}

.glass-transport:hover {
  opacity: 1;
  background: rgba(255, 255, 255, 0.25);
  border-color: rgba(64, 75, 105, 0.4);
  transform: translateY(-5px);
  box-shadow: 0 15px 45px rgba(64, 75, 105, 0.2);
}

/* Neon Glow Effect */
.neon-transport {
  opacity: 0.9;
  border-radius: 18px;
  position: relative;
  transition: all 0.4s ease;
  filter: drop-shadow(0 0 10px rgba(64, 75, 105, 0.3));
}

.neon-transport:hover {
  opacity: 1;
  transform: scale(1.02);
  filter: 
    drop-shadow(0 0 20px rgba(64, 75, 105, 0.5))
    drop-shadow(0 0 40px rgba(64, 75, 105, 0.3))
    drop-shadow(0 0 60px rgba(64, 75, 105, 0.1));
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .transport-image,
  .futuristic-trailer,
  .holographic-transport,
  .glass-transport {
    border-radius: 12px;
  }
  
  .transport-image:hover,
  .futuristic-trailer:hover,
  .holographic-transport:hover,
  .glass-transport:hover {
    transform: scale(1.01);
  }
}
</style>