<template>
  <header class="sticky top-0 z-[1000] flex flex-col bg-yellow-400 w-full">
    <!-- TOP NAV -->
    <nav class="flex flex-1 w-full items-center gap-3 bg-[#f0c36d] ">
      <ul class="flex items-center gap-1 list-none m-0 p-0 hidden lg:flex">
        <TopNavDropdown
          title="LỊCH TRỰC TIẾP"
          :items="liveItems"
        />

        <TopNavDropdown
          title="LỊCH TRỰC TIẾP"
          :items="liveItems"
        />
         <TopNavDropdown
          title="LỊCH TRỰC TIẾP"
          :items="liveItems"
        />
         <TopNavDropdown
          title="LỊCH TRỰC TIẾP"
          :items="liveItems"
        />
         <TopNavDropdown
          title="LỊCH TRỰC TIẾP"
          :items="liveItems"
        />
         <TopNavDropdown
          title="LỊCH TRỰC TIẾP"
          :items="liveItems"
        />
      </ul>
      
      <!-- Mobile Top Controls -->
      <div class="flex lg:hidden items-center gap-3 ml-auto px-4">
        <button class="flex items-center justify-center bg-[#1a1a1a] rounded-full w-10 h-10">
          <span class="text-[#f0c36d] font-bold text-sm">Vn</span>
        </button>
        <button class="flex items-center justify-center bg-[#1a1a1a] rounded-full w-10 h-10">
          <div class="flex flex-col gap-0.5">
            <span class="w-4 h-0.5 bg-[#f0c36d]"></span>
            <span class="w-4 h-0.5 bg-[#f0c36d]"></span>
            <span class="w-4 h-0.5 bg-[#f0c36d]"></span>
          </div>
        </button>
      </div>
      
      <div class="hidden lg:block">
        <Profile/>
      </div>
    </nav>
     
    <!-- BOTTOM NAV -->
    <nav class="flex flex-wrap bg-black gap-2 lg:gap-4">
      <ul class="flex items-center justify-center gap-2 p-4 lg:p-11 flex-wrap">
        <li
          v-for="(item, index) in bottomNav"
          :key="index"
          class="flex flex-row items-center gap-2 lg:gap-4"
        >
          <img :src="item.icon" class="w-8 h-8 lg:w-10 lg:h-10" />
          <a :href="item.link" class="text-[12px] lg:text-[16px] text-white hidden sm:block">{{ item.label }}</a>
        </li>
      </ul>
      <div class="flex items-center gap-2 lg:gap-4 ml-auto px-2 lg:px-0">
        <button class="hidden sm:flex items-center gap-2 bg-white/90 border rounded-full px-2 lg:px-3 w-fit h-8 m-2 lg:m-6">
          <img :src="football" alt="Vietnam Flag" class="w-[24px] lg:w-[32px] h-[24px] lg:h-[32px] object-contain p-2 lg:p-4">
          <span class="text-xs lg:text-sm font-semibold text-gray-800 uppercase tracking-wide">Tiếng Việt</span>
        </button>

        <button 
          @click="isDark = !isDark"
          class="relative w-14 lg:w-16 h-7 lg:h-8 rounded-full bg-[#1a1a1a] border-2 border-[#f0c36d] shadow-sm transition-all overflow-hidden m-2"
          :aria-label="`Switch to ${isDark ? 'light' : 'dark'} mode`"
        >
          <!-- Toggle Circle -->
          <div 
            class="absolute top-0.5 left-0.5 w-5 lg:w-6 h-5 lg:h-6 bg-[#f0c36d] rounded-full shadow-md transition-transform duration-300 flex items-center justify-center"
            :class="{ 'translate-x-6 lg:translate-x-8': isDark }"
          >
            <Sun v-if="!isDark" class="w-3 lg:w-4 h-3 lg:h-4 text-black" />
            <Moon v-else class="w-3 lg:w-4 h-3 lg:h-4 text-black" />
          </div>
        </button>
      </div>
    </nav>
 
  </header>
</template>

<script setup>
import TopNavDropdown from '@/components/TopNavDropdown.vue'
import football from '@/public/assets/football.svg'
import volleyball from '@/public/assets/volleyball.svg'


import message from '@/public/assets/seconds/message.svg'
import book from '@/public/assets/seconds/book.svg'
import hightlight from '@/public/assets/seconds/hightlight.svg'
import reels from '@/public/assets/seconds/reels.svg'
import star from '@/public/assets/seconds/star.svg'
import video from '@/public/assets/seconds/video.svg'

import vietName from '@/public/assets/vietname.svg'
import { Moon, Sun } from 'lucide-vue-next'
import { ref } from 'vue'

const isDark = ref(false)

const liveItems = [
  { icon: football, label: 'BÓNG ĐÁ' },
  { icon: volleyball, label: 'ĐUA BI' },
  { icon: volleyball, label: 'BÓNG RỔ' },
  { icon: volleyball, label: 'E-SPORTShhhhhhhhhhhhhhhhhhhhhhhhh' },
  { icon: volleyball, label: 'CASINO' }
]

const bottomNav = [
  { icon: message, label: 'LỊCH THI ĐẤU' , link: '/test'},
  { icon: reels, label: 'BÁNG TIN' },
    { icon: hightlight, label: 'REELS' },
  { icon: video, label: 'HIGHLIGHT' },
    { icon: star, label: 'TIP KÈO' },
  { icon: book, label: 'PHIM ẢNH' },
]

const numberMessage = 5
</script>


<style scoped>
</style>