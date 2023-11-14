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
  }
});

//pending
const active = ref('')

</script>
<template>
<!-- Improve Coming Soon -->
        <li
            
            class="relative aspect-square h-[30vh] max-h-[275px] w-2/3 max-w-[475px] flex-none md:w-1/3"
          >
            <NuxtLink :to="link" class="relative h-full w-full">
              <div class="group flex h-full w-full items-center justify-center overflow-hidden rounded-lg border bg-white hover:border-blue-600 dark:bg-black"
                :class="active ? 'border-2 border-blue-600' : 'border-neutral-200 dark:border-neutral-800'">
                    <img :src="image" :alt="`Product ${title}`" class="relative h-full w-full object-contain transition duration-300 ease-in-out group-hover:scale-105 "
                    sizes="(min-width: 1024px) 25vw, (min-width: 768px) 33vw, 50vw"
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
          </li>

</template>