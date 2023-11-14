<script setup>
const props = defineProps({
  productsCarousel: {
    type: undefined,
    required: true,
  },
});
</script>
<template>
    <div class="mr-4 ml-4" >
      <div class="py-8">
        <h2 class="mb-4 text-2xl font-bold text-white">Related Products</h2>  
        <ul class="flex w-full gap-4 overflow-x-auto pt-1">
          <ProductCarousel
          v-for="product in productsCarousel"
          :key="product.node.id"
          :image="product.node.images.edges[0].node.src"
          :title="product.node.title"
          :price="`${product.node.priceRange.maxVariantPrice.amount} ${product.node.priceRange.maxVariantPrice.currencyCode}`"
          :link="`/products/${product.node.handle}`"
          :description="product.node.description"
          />
        </ul>
      </div>
    </div>
  </template>