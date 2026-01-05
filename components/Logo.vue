<template>
  <div class="logo-container">
    <a href="/" class="logo-link">
      <h1 class="logo-text">
        My<span class="logo-highlight">Brand</span>
      </h1>
    </a>
  </div>
</template>

<script setup>
// Logo component - responsive for mobile devices
</script>

<style scoped>
.logo-container {
  display: flex;
  align-items: center;
  padding: 0.5rem;
}

.logo-link {
  text-decoration: none;
  transition: transform 0.2s ease;
}

.logo-link:hover {
  transform: scale(1.05);
}

.logo-text {
  font-size: 1.5rem;
  font-weight: bold;
  color: #1a202c;
  margin: 0;
}

.logo-highlight {
  color: #3b82f6;
}

/* Mobile responsiveness */
@media (max-width: 640px) {
  .logo-container {
    padding: 0.25rem;
  }
  
  .logo-text {
    font-size: 1.25rem;
  }
}

@media (max-width: 375px) {
  .logo-text {
    font-size: 1.125rem;
  }
}
</style>
