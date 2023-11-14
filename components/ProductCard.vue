<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  price: {
    type: String,
    required: true,
  },
  image: {
    type: String,
    required: true,
  },
  link: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
});

//pending
const isActive = ref('')
const size = ref([
  'full',
  'half'
  ])

</script>

<template>
  <!-- Improve Coming Soon -->
        <div :class="[size === 'full' ? 'md:col-span-4 md:row-span-2' : 'md:col-span-3 md:row-span-1']" >
            <NuxtLink :to="link" class="relative block aspect-square h-full w-full" activeClass="text-black dark:text-neutral-300">
                <div class="group flex h-full w-full items-center justify-center overflow-hidden rounded-lg border bg-white hover:border-blue-600 dark:bg-black"
                :class="[isActive ? 'border-2 border-blue-600' : 'border-neutral-200 dark:border-neutral-800']">
                    <img :src="image" :alt="`Product ${title}`" class="relative h-full w-full object-contain transition duration-300 ease-in-out group-hover:scale-105 "

                   >

                   <div
                      class='absolute bottom-0 left-0 flex w-full px-4 pb-4 @container/label'
                    >
                      <div class="flex items-center rounded-full border bg-white/70 p-1 text-xs font-semibold text-black backdrop-blur-md dark:border-neutral-800 dark:bg-black/70 dark:text-white">
                        <h3 class="mr-4 line-clamp-2 flex-grow pl-2 leading-none tracking-tight">{{title}}</h3>
                        <p
                          class="flex-none rounded-full bg-blue-600 p-2 text-white"
                        >{{ price }}</p>
                       </div>
                    </div>
                 </div>
            </NuxtLink>
        </div>
  </template>

