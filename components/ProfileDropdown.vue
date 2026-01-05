<template>
  <div ref="dropdownContainer" class="relative">
    <div
      v-if="isOpen"
      class="absolute right-0 top-2 mt-2 w-48 bg-white rounded-lg shadow-lg py-2 z-50"
    >
      <a
        v-for="item in items"
        :key="item.label"
        href="#"
        class="flex items-center gap-2 px-4 py-2 hover:bg-gray-100 transition"
        @click.prevent="handleItemClick"
      >
        <img :src="item.icon" class="w-5 h-5" />
        <span class="text-sm">{{ item.label }}</span>
      </a>
    </div>
  </div>
</template>

<script setup>
import { ref, defineProps, defineExpose, onMounted, onUnmounted } from 'vue'

const props = defineProps({
  items: {
    type: Array,
    default: () => []
  }
})

const isOpen = ref(false)
const dropdownContainer = ref(null)

const toggle = () => {
  isOpen.value = !isOpen.value
}

const close = () => {
  isOpen.value = false 
}

const handleItemClick = () => {
  console.log('Item clicked')
  close()
}

const handleClickOutside = (event) => {
  if (!dropdownContainer.value || !isOpen.value) return
  
  // Get the parent profile avatar container
  const profileContainer = dropdownContainer.value.parentElement
  
  // Check if click is outside both the dropdown and the profile avatar
  if (!dropdownContainer.value.contains(event.target) && 
      !profileContainer?.contains(event.target)) {
    close()
  }
}

onMounted(() => {
  document.addEventListener('click', handleClickOutside)
})

onUnmounted(() => {
  document.removeEventListener('click', handleClickOutside)
})

defineExpose({ toggle, close })
</script>