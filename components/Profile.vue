<template>
  <div class="flex flex-col items-center bg-transparent">
    <p>Xin chào, NguyenVanDen</p>
    <div
      class="profile inline-flex items-center bg-[#1a1a1a] rounded-full border-2 border-[#333] shadow-lg gap-4"
    >
      <div
        class="flex items-center gap-3 bg-white rounded-full py-1 px-2 pr-1 shadow-inner h-12 min-w-[200px] relative"
      >
        <div class="relative">
          <img
            :src="coins"
            alt="coins"
            class="w-10 h-10 object-contain drop-shadow-sm"
          />
        </div>
        <p class="text-2xl font-black text-[#1a1a1a] grow px-2">1000</p>

        <button
        @click="addCoin"
          class="bg-[#f0c36d] hover:bg-[#e0b35d] rounded-full w-10 h-10 flex items-center justify-center transition-colors shadow-sm"
        >
          <Plus v-if="!showCoinDropdown" class="w-6 h-6 text-[#1a1a1a] stroke-[3px]" />
          <X v-else class="w-5 h-5 text-[#1a1a1a] stroke-[3px]" />
        </button>
        
        <CoinDropdown 
          :is-open="showCoinDropdown" 
          @close="showCoinDropdown = false" 
        />
      </div>  
          <div class="flex items-center gap-5 ml-2">
        <div class="relative cursor-pointer group">
          <BellRing
            class="w-8 h-8 text-[#f0c36d] group-hover:brightness-110 transition"
          />
          <span
            class="absolute -top-1 -right-2 bg-[#ff4d4d] text-white text-[12px] font-bold rounded-full h-5 w-5 flex items-center justify-center border border-[#1a1a1a]"
          >
            10
          </span>
        </div>

        <div class="relative cursor-pointer group">
          <Mail
            class="w-8 h-8 text-[#f0c36d] group-hover:brightness-110 transition"
          />
          <span
            class="absolute -top-1 -right-2 bg-[#ff4d4d] text-white text-[12px] font-bold rounded-full h-5 w-5 flex items-center justify-center border border-[#1a1a1a]"
          >
            2
          </span>
        </div>

        <div class="relative cursor-pointer group">
          <Calendar
            class="w-8 h-8 text-[#f0c36d] group-hover:brightness-110 transition"
          />
          <span
            class="absolute -bottom-1 -right-1 bg-[#ff4d4d] rounded-full p-0.5 border border-[#1a1a1a]"
          >
            <Check class="w-3 h-3 text-white stroke-[4px]" />
          </span>
        </div>
       <div @click="toggleDropdown" class="relative cursor-pointer ml-2 group">
          <div class="relative w-16 h-16 flex items-center justify-center">
            <div class="absolute inset-0 border-[3px] border-[#f0c36d] rounded-full shadow-[0_0_10px_rgba(240,195,109,0.5)]"></div>
            
            <img
              src="https://i.pravatar.cc/300"
              alt="Profile Avatar"
              class="w-[85%] h-[85%] rounded-full object-cover border-2 border-[#1a1a1a]"
            />

            <div class="absolute -bottom-1 -right-1 bg-gradient-to-b from-[#444] to-black border-2 border-[#f0c36d] rounded-full w-7 h-7 flex items-center justify-center shadow-lg">
              <span class="text-[#f0c36d] text-[10px] font-black italic">{{ numberMessage }}</span>
            </div>
            
          </div>

          <ProfileDropdown ref="dropdownRef" :items="profileItems" />
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref } from "vue";
import coins from "@/public/assets/coin.svg";
import football from "@/public/assets/football.svg";
import { BellRing, Calendar, Mail, Plus, Check, X } from "lucide-vue-next";
import ProfileDropdown from "./ProfileDropdown.vue";
import CoinDropdown from "./CoinDropdown.vue";

const numberMessage = 5;
const dropdownRef = ref(null);
const showCoinDropdown = ref(false);

const profileItems = [
  { icon: football, label: "Hồ sơ của tôi" },
  { icon: football, label: "Cài đặt" },
  { icon: football, label: "Lịch sử" },
  { icon: football, label: "Đăng xuất" },
];

function toggleDropdown() {
  dropdownRef.value?.toggle();
}

function addCoin() {
  showCoinDropdown.value = !showCoinDropdown.value;
}
</script>
