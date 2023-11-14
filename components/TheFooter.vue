<script setup>


const { data: posts } = await useAsyncData('posts', () =>
  queryContent('/page').find()
)

</script>

<template>
  <footer class="bg-neutral-800 text-sm text-neutral-500 dark:text-neutral-400">
      <div class="mx-auto flex w-full max-w-7xl flex-col gap-6 border-t border-neutral-200 px-6 py-12 text-sm dark:border-neutral-700 md:flex-row md:gap-12 md:px-4 min-[1320px]:px-0">
        <div>
          <NuxtLink class="flex items-center gap-2 text-black dark:text-white md:pt-1" to="/">
            <img  src="/logo.svg" alt="Store logo" />
            <div class="ml-2 flex-none text-sm text-white font-medium uppercase md:hidden lg:block">
            Acme Store
          </div>
          </NuxtLink>
        </div>
     
      <div class="flex h-[188px] w-[200px] flex-col gap-2">
           <ul >

            <li>
              <NuxtLink to="/" class="block p-2 text-lg underline-offset-4 hover:text-black hover:underline dark:hover:text-neutral-300 md:inline-block md:text-sm" activeClass="text-black dark:text-neutral-300">
                Home
              </NuxtLink>
            </li>

            <li v-for="post in posts" :key="post.slug">
              <NuxtLink :to="post._path" class="block p-2 text-lg underline-offset-4 hover:text-black hover:underline dark:hover:text-neutral-300 md:inline-block md:text-sm" activeClass="text-black dark:text-neutral-300">
                {{ post.title }}
              </NuxtLink>
            </li>

           </ul>
        
      </div>
    </div>

      <div class="border-t border-neutral-200 py-6 text-sm dark:border-neutral-700">
        <div class="mx-auto flex w-full max-w-7xl flex-col items-center gap-1 px-4 md:flex-row md:gap-0 md:px-4 min-[1320px]:px-0">
          <p>
            &copy; DaniJP 2023. All rights reserved.
          </p>
          <p class="md:ml-auto">
            <a href="#" class="text-black dark:text-white">
              Crafted by ▲ DaniJP
            </a>
          </p>
        </div>
      </div>
    </footer>
</template>