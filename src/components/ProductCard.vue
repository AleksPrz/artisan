<template>
  <div
    class="border rounded-lg overflow-hidden bg-white hover:shadow-md transition"
  >
    <img
      :src="product.image"
      :alt="product.name"
      class="w-full h-44 object-cover"
    />

    <div class="p-4">
      <h3 class="text-lg font-medium mb-1">
        {{ product.name }}
      </h3>

      <p class="text-sm text-gray-500 mb-2">
        {{ product.category }}
      </p>

      <p class="text-sm text-gray-700 mb-3">
        {{ product.description }}
      </p>

      <p class="text-base font-semibold">
        $ {{ product.price }}
      </p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  product: {
    type: Object,
    required: true
  }
})
</script>