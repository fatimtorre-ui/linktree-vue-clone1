<script setup>
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue'
const profile = ref({
  name: 'Fatima Torres',
  slogan: 'STC IT Student',
  avatar: '8b97e421-39d2-4295-854f-d194e06a99fc.jpg'
  })
</script>

<template>
  <main class="flex min-h-screen flex-col items-center justify-center px-4 py-8">
    <!-- Profile Header-->
     <div class="mb-8 flex flex-col items-center text-center">
      <div class="h-24 w-24 overflow-hidden rounded-full border-green-400 shadow-lg shadow-green-500/20 sm:h-32 sm:w-32">
      <img 
      :src="profile.avatar" 
      :alt="profile.name"
      class="h-fill w-full object-cover"
      />
      </div>
        <h1 class="font-sans mb-2 text-2xl font-bold text-white sm:text-3xl">{{  profile.name }}</h1>
        <p class="max-w-xs text-gray-300 sm:text-lg">{{  profile.slogan }}</p>
     </div>
    
  </main>
</template>
