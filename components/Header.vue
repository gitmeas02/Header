<template>
  <header class="header">
    <nav class="nav-container">
      <!-- Mobile menu button -->
      <button 
        @click="toggleMenu" 
        class="mobile-menu-btn"
        aria-label="Toggle menu"
      >
        <svg 
          v-if="!isMenuOpen" 
          xmlns="http://www.w3.org/2000/svg" 
          class="menu-icon" 
          fill="none" 
          viewBox="0 0 24 24" 
          stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg 
          v-else 
          xmlns="http://www.w3.org/2000/svg" 
          class="menu-icon" 
          fill="none" 
          viewBox="0 0 24 24" 
          stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>

      <!-- Desktop navigation -->
      <ul class="nav-list desktop-nav">
        <li v-for="item in navItems" :key="item.name" class="nav-item">
          <a :href="item.href" class="nav-link">{{ item.name }}</a>
        </li>
      </ul>

      <!-- Mobile navigation -->
      <transition name="slide">
        <ul v-if="isMenuOpen" class="nav-list mobile-nav">
          <li v-for="item in navItems" :key="item.name" class="nav-item">
            <a :href="item.href" class="nav-link" @click="closeMenu">{{ item.name }}</a>
          </li>
        </ul>
      </transition>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const navItems = [
  { name: 'Home', href: '/' },
  { name: 'About', href: '/about' },
  { name: 'Services', href: '/services' },
  { name: 'Contact', href: '/contact' }
]

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<style scoped>
.header {
  width: 100%;
}

.nav-container {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  position: relative;
}

.mobile-menu-btn {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  color: #1a202c;
}

.menu-icon {
  width: 1.5rem;
  height: 1.5rem;
}

.nav-list {
  list-style: none;
  display: flex;
  gap: 2rem;
  padding: 0;
  margin: 0;
  align-items: center;
  justify-content: flex-end;
}

.desktop-nav {
  padding: 1rem 0;
}

.mobile-nav {
  display: none;
}

.nav-item {
  margin: 0;
}

.nav-link {
  text-decoration: none;
  color: #4a5568;
  font-weight: 500;
  padding: 0.5rem 1rem;
  border-radius: 0.375rem;
  transition: all 0.2s ease;
  display: block;
}

.nav-link:hover {
  color: #3b82f6;
  background-color: #f7fafc;
}

/* Mobile responsiveness */
@media (max-width: 768px) {
  .mobile-menu-btn {
    display: block;
  }

  .desktop-nav {
    display: none;
  }

  .mobile-nav {
    display: flex;
    flex-direction: column;
    gap: 0;
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background-color: white;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    padding: 0.5rem 0;
  }

  .nav-item {
    width: 100%;
  }

  .nav-link {
    padding: 1rem 1.5rem;
    border-radius: 0;
  }

  .nav-link:hover {
    background-color: #f7fafc;
  }
}

/* Slide transition for mobile menu */
.slide-enter-active,
.slide-leave-active {
  transition: all 0.3s ease;
}

.slide-enter-from {
  opacity: 0;
  transform: translateY(-10px);
}

.slide-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
