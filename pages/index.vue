<template>
  <div class="flex flex-col md:flex-row">
    <!-- Mobile Layout -->
    <div class="md:hidden w-full">
      <div class="flex bg-[#f0c36d]">
        <!-- Logo Section -->
        <div class="logo-mobile bg-black flex items-center justify-end px-4 py-3">
          <p class="text-4xl text-white font-bold">LOGO</p>
        </div>
        
        <!-- Right Side Controls -->
        <div class="flex-1 flex items-center justify-end gap-3 px-4">
          <!-- Language Button -->
          <button class="flex items-center justify-center bg-[#1a1a1a] rounded-full w-12 h-12">
            <span class="text-[#f0c36d] font-bold text-lg">Vn</span>
          </button>
          
          <!-- Hamburger Menu -->
          <button class="flex items-center justify-center bg-[#1a1a1a] rounded-full w-12 h-12">
            <div class="flex flex-col gap-1">
              <span class="w-5 h-0.5 bg-[#f0c36d]"></span>
              <span class="w-5 h-0.5 bg-[#f0c36d]"></span>
              <span class="w-5 h-0.5 bg-[#f0c36d]"></span>
            </div>
          </button>
        </div>
      </div>
      
      <!-- Bottom Nav Icons -->
      <div class="flex items-center justify-center gap-4 bg-[#f0c36d] py-3 px-4">
        <img src="/assets/football.svg" class="w-10 h-10" alt="Football" />
        <img src="/assets/volleyball.svg" class="w-10 h-10" alt="Basketball" />
        <img src="/assets/volleyball.svg" class="w-10 h-10" alt="Gaming" />
        
        <!-- Theme Toggle -->
        <button class="relative flex items-center bg-[#1a1a1a] border-2 border-[#f0c36d] rounded-full w-16 h-8 ml-2">
          <div class="absolute left-1 w-6 h-6 bg-[#f0c36d] rounded-full flex items-center justify-center">
            <svg class="w-4 h-4 text-black" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z" clip-rule="evenodd"/>
            </svg>
          </div>
        </button>
      </div>
    </div>
    
    <!-- Desktop Layout -->
    <div class="hidden md:flex w-full">
      <Logo/>
      <Header />
    </div>
  </div>
</template>

<script setup>
// The header is now a separate component
</script>

<style scoped>
.logo-mobile {
  border-top-right-radius: 40px;
  min-width: 180px;
}
</style>

