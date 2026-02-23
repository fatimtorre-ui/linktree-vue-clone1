<script setup>
defineProps({
    title: {
        type: String,
        required: true,
    },
    url: {
        type: String,
        required: true,
    },
    description: {
        type: String,
        default: '',
    },
    icon: {
        type: String,
        default: 'flag',
    },
})

const icons = {
    flag: '<path d="M9 20.858c-4.5 0-9-6.03-9-11a9 9 0 1 1 18 0c0 4.97-4.5 11-9 11m-1.974-6.181c.529-.192 1.42-1.946.853-3.503c-.566-1.557-2.399-2.32-2.905-2.135c-.506.184-1.42 1.946-.853 3.503c.566 1.557 2.376 2.327 2.905 2.135m3.948 0c.529.192 2.339-.578 2.905-2.135c.567-1.557-.347-3.319-.853-3.503s-2.339.578-2.905 2.135c-.567 1.557.324 3.31.853 3.503" />',
    code: '<path stroke-linecap="round" stroke-linejoin="round" d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5"></path>',
    briefcase: '<path stroke-linecap="round" stroke-linejoin="round" d="M20.25 14.15v4.25c0 1.094-.787 2.036-1.872 2.18-2.087.277-4.216.42-6.378.42s-4.291-.143-6.378-.42c-1.085-.144-1.872-1.086-1.872-2.18v-4.25m16.5 0a2.18 2.18 0 0 0 .75-1.661V8.706c0-1.081-.768-2.015-1.837-2.175a48.114 48.114 0 0 0-3.413-.387m4.5 8.006c-.194.165-.42.295-.673.38A23.978 23.978 0 0 1 12 15.75c-2.648 0-5.195-.429-7.577-1.22a2.016 2.016 0 0 1-.673-.38m0 0A2.18 2.18 0 0 1 3 12.489V8.706c0-1.081.768-2.015 1.837-2.175a48.111 48.111 0 0 1 3.413-.387m7.5 0V5.25A2.25 2.25 0 0 0 13.5 3h-3a2.25 2.25 0 0 0-2.25 2.25v.894m7.5 0a48.667 48.667 0 0 0-7.5 0M12 12.75h.008v.008H12v-.008Z"></path>',
    expense: ' <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 18.75a60.07 60.07 0 0 1 15.797 2.101c.727.198 1.453-.342 1.453-1.096V18.75M3.75 4.5v.75A.75.75 0 0 1 3 6h-.75m0 0v-.375c0-.621.504-1.125 1.125-1.125H20.25M2.25 6v9m18-10.5v.75c0 .414.336.75.75.75h.75m-1.5-1.5h.375c.621 0 1.125.504 1.125 1.125v9.75c0 .621-.504 1.125-1.125 1.125h-.375m1.5-1.5H21a.75.75 0 0 0-.75.75v.75m0 0H3.75m0 0h-.375a1.125 1.125 0 0 1-1.125-1.125V15m1.5 1.5v-.75A.75.75 0 0 0 3 15h-.75M15 10.5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Zm3 0h.008v.008H18V10.5Zm-12 0h.008v.008H6V10.5Z"></path>'
}

</script>

<template>
   <a 
   :href="url" 
   target="_blank" 
   rel="noopener noreferrer"
   class=" group relative flex w-full items-center gap-4 rounded-xl border border-gray-700 bg-gray-800 p-4 shadow-md shadow-gray-900/50 hover:scale-[1.02] hover:border-green-600 hover:shadow-xl hover:shadow-green-500/20 transition-all-300">
   
   <!--Icon Container-->
   <div class="flex h-12 w-12 shrink-0 items-center justify-center rounded-lg bg-gray-700 text-green-400 transition-all duration-300 group-hover:scale-110 group-hover:bg-green-500 group-hover:text-white group-hover:shadow-xl group-hover:shadow-green-500/20">
   <svg
    viewBox="-3 -1.5 24 24" 
     fill="none" 
     stroke="currentColor" 
     class="h-6 w-6 transition-transform duration-300 group-hover:rotate-6">
     v-html="icons[icon] || icons.flag"
     ></svg>
   </div>

   <!--Text Content-->
   <div class=" min-w-0 flex-1"> 
    <h3 class="truncate font-display font-semibold text-white"> {{title}}</h3>
    <p class="truncate text-sm text-gray-400"> {{description}}</p>
   </div>

   <!--Hover Glow Effect-->
   <div class="absolute inset-0 rounded-xl bg-linear-to-r from-green-500/0 via-green-500/10 to-green-500/0 opacity-0 transition-opacity duration-300 group-hover:opacity-100"></div>
   </a>

    </template> 
  <script setup>
</script>  