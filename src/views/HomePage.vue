<script setup>
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue'
import { routerKey } from 'vue-router';
//import { x } from 'vue-router/dist/router-CWoNjPRp.mjs';
const profile = ref({
  name: 'Fatima Torres',
  slogan: 'STC IT Student',
  avatar: '8b97e421-39d2-4295-854f-d194e06a99fc.jpg',
 links: [
  {
    id: 1,
    title: 'GitHub',
    url: 'https://github.com/fatimtorre-ui',
    icon: 'code',
    description: 'Check out my project',
  },
  {
    id: 2,
    title: 'LinkedIn',
    url: 'https://www.linkedin.com/in/fatima-torres-10547a2a7/',
    icon: 'briefcase',
    description: 'Connect with me professionally',
  },
{
      id: 3,
    title: 'Expense Tracker',
    url: 'https://expense-splitter-vue.fatim-torre.workers.dev',
    icon: 'expense',
    description: 'My Project',
}
 ],
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
        <h1 class="font-sans mb-2 text-2xl font-bold text-black sm:text-3xl">{{  profile.name }}</h1>
        <p class="max-w-xs text-black-300 sm:text-lg">{{  profile.slogan }}</p>
     </div>
    
     <!---Link list-->
     <div class="flex w-full max-w-md flex-col gap-4">
      <LinkCard v-for="link in profile.links"
      :key="link.id"
      :title="link.title"
      :url="link.url"
      :description= "link.description"
      :icon="link.icon"
      />
     </div>

     <!-- Navigate To Info-->
      <RouterLink
      to="/Info"
      class="mt-8 text-sm text-gray-400 underline-offset-4 transition-colors duration-200 hover:underline hover-text-green-400"
      >About me -></RouterLink>
  </main>
</template>
