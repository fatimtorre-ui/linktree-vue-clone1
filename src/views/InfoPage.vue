

<script setup>
import { ref } from 'vue'

const bio = ref({
  name: 'Fatima Torres',
  avavtar: '8b97e421-39d2-4295-854f-d194e06a99fc.jpg',
  about: 'I am an IT student at South Texas College learning and getting my bachelors degree in Computers and Information Technology',
  skills: ['SQL', 'Vue.js', 'JavaScript', 'python', 'C++'],
  email: 'ftorresm@stu.southtexascollege.edu ',
  location: 'McAllen Texas'
})
</script>
<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:py-12">
          <RouterLink
      to="/"
      class="mt-8 self-start text-sm text-gray-400 underline-offset-4 transition-colors duration-200 hover:underline hover-text-green-400"
      > <- Back to Links
    </RouterLink>

    <!--Profile Card-->

    <div class="w-full max-w-lg rounded-2xl border border-gray-700 bg-gray-800 p-6 shadow-xl shadow-gray-900/50 sm:p-8">

  

    <!--Header-->
    <div class="mb-6 flex flex-col items-center text-center sm:flow-row sm:text-left ">
    <div class="mb-4 h-20 w-20 shrink-0 overflow-hidden rounded-full border-4 border-green-400 sm:mr-6 sm:mb-0">
    <img 
    :src="bio.avatar"
    :alt="bio.name"
    class="h-full w-full object-cover" /> 
    </div>  
    <div>
      <h1 class="mb-1 font-display text-2xl font-bold text-black">{{bio.name}}</h1>
      <p class="text-sm text-gray-400"> {{bio.location}}</p>
    </div>
  </div>

  <!--About Section-->
  <div class="mb-6">
    <h2 class="mb-3 text-lg font-semibold text-black"> About</h2>
    <p class="leading-relaxed text-gray-300">{{bio.about}}</p>
  </div>

  <!--Skills Section-->
  <div>
    <h2 class="mb-3 text-lg font-semibold text-black"> Skills</h2>
    <div class="flex flex-wrao gap-2">
      <span
      v-for="skill in bio.skills"
      :key="skill"
      class="rounded-full bg-green-900/50 px-3 py-1 text-sm text-green-300" >
      {{skill}}
    </span>
  </div>
</div>

<!--Contact-->
<div>
  <h2 class="mb-3 text-lg font-semibold text-black"> Get in Touch </h2>
  <a :href="`mailto:${bio.email}`"
  class="group inline-flex items-center gap-2 rounded-xl bg-green-500 px-6 py-3 font-medium text-white shadow-lg shadow-green-500/30 transition-all duration-200 hover:scale-105 hover:bg-green-600 hover:shadow-xl hover:shadow-green-500/40 active:scale-95"
  >
    <svg
     data-slot="icon" 
     fill="none" 
     stroke-width="1.5" 
     stroke="currentColor" 
     viewBox="0 0 24 24" 
     xmlns="http://www.w3.org/2000/svg" 
     aria-hidden="true"
     class="h-5 w-5 transition-transform duration-200 group-hover:rotate-12">
  <path 
  stroke-linecap="round" 
  stroke-linejoin="round" 
  d="M16.5 12a4.5 4.5 0 1 1-9 0 4.5 4.5 0 0 1 9 0Zm0 0c0 1.657 1.007 3 2.25 3S21 13.657 21 12a9 9 0 1 0-2.636 6.364M16.5 12V8.25">
</path>
</svg>
Send email</a>
</div>
      </div>
  </main>
</template>
