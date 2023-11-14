<script setup>
const props = defineProps({
  products: {
    type: undefined,
    required: true,
  },
  productsCarousel: {
    type: undefined,
    required: true,
  },
});
</script>
<template>
    <section class="mx-auto grid max-w-screen-2xl gap-4 px-4 pb-4 md:grid-cols-6 md:grid-rows-2">
        <ProductCard
        v-for="product in products"
        :key="product.node.id"
        :image="product.node.images.edges[0].node.src"
        :title="product.node.title"
        :price="`${product.node.priceRange.maxVariantPrice.amount} ${product.node.priceRange.maxVariantPrice.currencyCode}`"
        :link="`/products/${product.node.handle}`"
        :description="product.node.description"
        />
    </section>

    <div class=" w-full overflow-x-auto pb-6 pt-1" >
      <ul class="flex animate-carousel gap-4">
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
  </template>