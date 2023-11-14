<script setup>
const { path } = useRoute()

const { data } = await useAsyncData(`content-${path}`, () => {
  return queryContent()
    .where({ _path: path })
    .findOne()
})
</script>

<template>
    <div class="w-full">
        <div class="mx-8 max-w-2xl py-20 sm:mx-auto">
            <ContentRenderer :value="data" class="prose prose-h1:text-white text-white" />
        </div>
    </div>
</template>