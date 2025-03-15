<script>
import CarPriceInput from './CarPriceInput.vue'
import CarPriceRange from './CarPriceRange.vue'
import CarPriceSuperSelect from './CarPriceSuperSelect.vue'

export default {
  components: { CarPriceInput, CarPriceRange, CarPriceSuperSelect },

  emits: ['update:model-value', 'car-price-updated'],

  data() {
    return {
      carPrice: 0,
    }
  },

  watch: {
    carPrice(newValue) {
      this.$emit('car-price-updated', newValue)
    },
  },
}
</script>

<template>
  <div>
    <h2>Price: {{ carPrice }}</h2>

    <h3>Выберите цену:</h3>

    <CarPriceInput v-model="carPrice" />

    <CarPriceRange v-model="carPrice" />

    <CarPriceSuperSelect v-model="carPrice" />
  </div>
</template>
