<script setup>
import { PlusIcon } from '@heroicons/vue/24/outline';
const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
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
  loading: {
    type: Boolean,
    required: true,
  },
});

const emit = defineEmits(["button-clicked"]);
</script>

<template>
  <section>
    <div class="mx-auto max-w-screen-2xl px-4">
        <div class="flex flex-col rounded-lg border border-neutral-200 bg-white p-8 dark:border-neutral-800 dark:bg-black md:p-12 lg:flex-row lg:gap-8">
            <div class="h-full w-full basis-full lg:basis-4/6">
                <img
                    :src="image"
                    :alt="`Product ${title}`"
                />
            </div>
      
      <div class="basis-full lg:basis-2/6">
        <div class="mb-6 flex flex-col border-b pb-6 dark:border-neutral-700">
        <h1 class="mb-4 text-5xl font-medium text-white">{{ title }}</h1>
        <div class="mr-auto w-auto rounded-full bg-blue-600 p-2 text-sm text-white">
         <p><span class="ml-1 inline">{{ price }}</span></p>
        </div>
      </div>

      <div class="mb-8 text-sm text-white mt-6">
        <p>{{ description }}</p>
      </div>

        <button
          @click="emit('button-clicked')"
          class="relative flex w-full items-center justify-center rounded-full bg-blue-600 p-4 tracking-wide text-white hover:bg-blue-700"
        >
        <div class="absolute left-0 ml-4">
          <PlusIcon class="h-5" />
        </div>
          {{ loading ? "Redirecting" : `Add to cart` }}
        </button>
      
      </div>
    </div>
    </div>
  </section>
</template>
