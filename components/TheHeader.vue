<template>
    <nav class="bg-neutral-800 relative flex items-center justify-between p-4 lg:px-6">
      <div className="block flex-none md:hidden">
        <!-- <MobileMenu /> -->
      </div>
      <div class="flex w-full items-center">
        <div class="flex w-full md:w-1/3">
        <NuxtLink to="/" class="mr-2 flex w-full items-center justify-center md:w-auto lg:mr-6">
          <img  src="/logo.svg" alt="Store logo" />
          <div class="ml-2 flex-none text-sm text-white font-medium uppercase md:hidden lg:block">
            Acme Store
          </div>
        </NuxtLink>
       
          <ul class="hidden gap-6 text-sm md:flex md:items-center">
               <li>
                  <NuxtLink
                    to="#"
                    class="text-neutral-500 underline-offset-4 hover:text-black hover:underline dark:text-neutral-400 dark:hover:text-neutral-300"
                  >
                    All
                  </NuxtLink>
              </li>
              <li>
                  <NuxtLink
                    to="#"
                    class="text-neutral-500 underline-offset-4 hover:text-black hover:underline dark:text-neutral-400 dark:hover:text-neutral-300"
                  >
                  Shirts
                  </NuxtLink>
              </li>
              <li>
                  <NuxtLink
                    to="#"
                    class="text-neutral-500 underline-offset-4 hover:text-black hover:underline dark:text-neutral-400 dark:hover:text-neutral-300"
                  >
                  Stickers
                  </NuxtLink>
              </li>
            </ul>

            
        </div>
        <div class="hidden justify-center md:flex md:w-1/3">
              <!-- <Search /> -->
            </div>
            <div class="flex justify-end md:w-1/3">
              
                <!-- <Cart /> -->
              
            </div>
      </div>
    </nav>
  </template>
  