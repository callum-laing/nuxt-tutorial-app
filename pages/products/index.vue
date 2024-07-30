<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="p in products">
        <ProductCard :product="p" />
      </div>
    </div>
  </div>
</template>

<script setup>
definePageMeta({
  layout: "products",
});

// fetch the products from the fakestore API
const { data: products } = await useFetch("https://fakestoreapi.com/products");
</script>

<style scoped>
h2 {
  font-size: 5rem;
}

.router-link-active {
  color: red;
}
</style>
