<template>
  <li
    class="top-nav-item"
    @mouseenter="open"
    @mouseleave="close"
  >
    <div
      class="relative rounded-[20px] transition-colors duration-300 ease-in-out"
    :class="{ 'bg-white/10': isOpen }"
    >
      <button class="live-schedule-btn">
        {{ title }}
      </button>

      <div v-if="isOpen" class="absolute top-full left-0
         min-w-[140px]
         flex flex-col gap-1
         p-[6px]
         rounded-xl
         shadow-md
         z-[1001]
         w-max
         max-w-[200px]
        bg-black/40 
        backdrop-blur-md
        border border-white/20
        rounded-3xl
        shadow-2xl
">
        <a
          v-for="item in items"
          :key="item.label"
          href="#"
          class="dropdown-item"
        > 
            <img :src="item.icon" alt="" class="
            w-[18px] 
            h-[18px]
            object-contain
            flex-shrink-0

            md:w-5 md:h-5
            lg:w-6 lg:h-6
            " />
          <span class="truncate">{{ item.label }}</span>
        </a>
      </div>
    </div>
  </li>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  title: String,
  items: Array,

})

const isOpen = ref(false)

function open() {
  isOpen.value = true
}

function close() {
  isOpen.value = false
}
</script>

<style scoped>

.live-schedule-btn {
  padding: 6px 10px;
  transition: all 0.3s ease;
  font-size: 11px;
  font-weight: 600;
  border-radius: 16px;
  cursor: pointer;
  background-color: black;
  color: rgba(235, 218, 68, 0.712);
  text-align: center;
  border: none;
  width: 100%;
  height: 32px;
  white-space: nowrap;
}

/* Tablet */
@media (min-width: 768px) {
  .live-schedule-btn {
    padding: 7px 12px;
    font-size: 12px;
    height: 36px;
    border-radius: 18px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .live-schedule-btn {
    padding: 8px 14px;
    font-size: 14px;
    height: 40px;
    border-radius: 20px;
  }
}

.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  min-width: 140px;
  display: flex;
  flex-direction: column;
  gap: 4px;
  padding: 6px;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  z-index: 1001;
  width: max-content;
  max-width: 200px;
}

/* Tablet */
@media (min-width: 768px) {
  .dropdown-menu {
    left: 5px;
    min-width: 160px;
    gap: 5px;
    padding: 8px;
    border-radius: 14px;
    max-width: 240px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .dropdown-menu {
    min-width: 180px;
    padding-top: 5px;
    border-radius: 16px;
    max-width: none;
  }
}

.dropdown-item {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 6px 10px;
  color: #2a2a2a;
  text-decoration: none;
  transition: all 0.3s ease;
  font-size: 10px;
  font-weight: 600;
  border-radius: 12px;
  cursor: pointer;
  background: transparent;
}

/* Tablet */
@media (min-width: 768px) {
  .dropdown-item {
    gap: 10px;
    padding: 7px 11px;
    font-size: 11px;
    border-radius: 14px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .dropdown-item {
    gap: 12px;
    padding: 8px 12px;
    font-size: 12px;
    border-radius: 16px;
  }
}

.dropdown-item:hover {
  background: rgba(107, 106, 104, 0.25);
  transform: translateY(3px);
}

@media (min-width: 768px) {
  .dropdown-item:hover {
    transform: translateY(3px);
  }
}

@media (min-width: 1024px) {
  .dropdown-item:hover {
    transform: translateY(3px);
  }
}


</style>
