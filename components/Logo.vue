<template>
   <div class="bg-[#f0c36d] ">
     <div class="flex w-[200px] lg:w-[488px] Border">
        <p class="text-[48px] lg:text-[96px] text-2xl">Logo</p>
    </div>
   </div>
</template>
<script setup></script>
<style scoped>
    .Border {
        border-top-right-radius: 40px;
        background-color: rgb(0, 0, 0);
        text-align: right;
        display: flex;
        justify-content: flex-end; 
        color: white;
        margin: 0;
        padding: 0;
    }
    
    @media (min-width: 1024px) {
        .Border {
            border-top-right-radius: 60px;
        }
    }
</style>