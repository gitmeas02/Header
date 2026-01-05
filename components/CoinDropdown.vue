<template>
  <div
    v-if="isOpen"
    ref="dropdownContainer"
    class="absolute top-14 left-0 right-0 bg-black/40 backdrop-blur-md border border-white/20 rounded-3xl shadow-2xl z-50 flex flex-col gap-2 pt-3 px-3 pb-4"
  >
    <div
      class="flex items-center gap-3 bg-black/30 rounded-full py-1.5 px-3 h-12 border border-white/5"
    >
      <div
        class="w-8 h-8 flex items-center justify-center grayscale brightness-150"
      >
        <img :src="coins" class="w-8 h-8 object-contain" />
      </div>
      <span class="text-lg font-bold text-white tracking-wide">20.000</span>
    </div>

    <div
      class="flex items-center gap-3 bg-black/30 rounded-full py-1.5 px-3 h-12 border border-white/5"
    >
      <div class="w-8 h-8 flex items-center justify-center">
        <Crown class="w-6 h-6 text-gray-300" />
      </div>
      <span class="text-lg font-bold text-white tracking-wide">20.000</span>
    </div>

    <div
      class="flex items-start justify-center gap-2 py-12 text-white/90 hover:text-white transition-colors h-[76px] pt-[50px] "
    >
      <div class="bg-[#f0c36d] rounded-full">
        <Plus class="w-6 h-6 text-black stroke-[4px]" />
      </div>
      <span class="text-lg font-medium">Nạp thêm</span>
    </div>
  </div>
</template>

<script setup>
import { ref, watch, onMounted, onUnmounted } from "vue";
import { X, Plus, Crown } from "lucide-vue-next";
import coins from "@/public/assets/coin.svg";

const props = defineProps({
  isOpen: Boolean,
});

const emit = defineEmits(["close"]);

const dropdownContainer = ref(null);

const handleClickOutside = (event) => {
  if (!props.isOpen || !dropdownContainer.value) return;

  // Get the parent container (the coin button area)
  const parentContainer = dropdownContainer.value.parentElement;

  // Close if click is outside both dropdown and parent
  if (
    !dropdownContainer.value.contains(event.target) &&
    !parentContainer?.contains(event.target)
  ) {
    emit("close");
  }
};

watch(
  () => props.isOpen,
  (newVal) => {
    if (newVal) {
      // Add listener when dropdown opens
      setTimeout(() => {
        document.addEventListener("click", handleClickOutside);
      }, 0);
    } else {
      // Remove listener when dropdown closes
      document.removeEventListener("click", handleClickOutside);
    }
  }
);

onUnmounted(() => {
  document.removeEventListener("click", handleClickOutside);
});
</script>
