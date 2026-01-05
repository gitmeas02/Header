<template>
  <div class="page-container">
    <div class="header-wrapper">
      <Logo/>
      <Header />
    </div>
    <main class="main-content">
      <section class="hero-section">
        <h2 class="hero-title">Welcome to Our Website</h2>
        <p class="hero-description">
          This is a responsive layout optimized for mobile devices
        </p>
      </section>
    </main>
  </div>
</template>

<script setup>
// The header is now a separate component
</script>

<style scoped>
.page-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.header-wrapper {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: white;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 0.5rem 1rem;
  position: sticky;
  top: 0;
  z-index: 100;
}

.main-content {
  flex: 1;
  padding: 2rem 1rem;
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
}

.hero-section {
  text-align: center;
  padding: 3rem 1rem;
}

.hero-title {
  font-size: 2.5rem;
  font-weight: bold;
  color: #1a202c;
  margin-bottom: 1rem;
}

.hero-description {
  font-size: 1.25rem;
  color: #4a5568;
  max-width: 600px;
  margin: 0 auto;
}

/* Mobile responsiveness */
@media (max-width: 768px) {
  .header-wrapper {
    padding: 0.5rem;
  }

  .hero-section {
    padding: 2rem 0.5rem;
  }

  .hero-title {
    font-size: 1.875rem;
  }

  .hero-description {
    font-size: 1rem;
  }
}

@media (max-width: 640px) {
  .header-wrapper {
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .main-content {
    padding: 1rem 0.5rem;
  }

  .hero-title {
    font-size: 1.5rem;
  }

  .hero-description {
    font-size: 0.875rem;
  }
}

@media (max-width: 375px) {
  .hero-title {
    font-size: 1.25rem;
  }
}
</style>
