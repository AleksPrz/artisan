<template>
  <section class="px-6 py-8">
    <h2 class="text-xl font-semibold mb-6">
      Catálogo
    </h2>

    <!-- LOADING -->
    <div v-if="loading" class="flex justify-center py-20">
      <div
        class="h-10 w-10 border-4 border-gray-300 border-t-gray-700 rounded-full animate-spin"
      />
    </div>

    <div
      class="grid gap-6 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4"
    >
      <ProductCard
        v-for="product in products"
        :key="product.id"
        :product="product"
      />
    </div>
  </section>
</template>

<script setup>
import { onMounted } from "vue";
import { ref } from "vue";
import ProductCard from "./ProductCard.vue"

const products = ref([])
const loading = ref(true)

onMounted(async () => {
    const url = import.meta.env.VITE_API_URL
    const response = await fetch(url)
    products.value = await response.json()
    loading.value = false
})

</script>
