<script setup lang="ts" >
const { data } = await useAsyncData("products", () =>
  GqlProducts({ first: 4 }),

);
const { data: carousel } = await useAsyncData("productsCarousel", () =>
  GqlProducts({ first: 13 }),

);
</script>

<template>
  
  <div  >
    <ProductList :products="data.products.edges" :productsCarousel="carousel.products.edges" />
    
  </div>
</template>
