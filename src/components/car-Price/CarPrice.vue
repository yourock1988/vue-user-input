<script>
import CarPriceInput from '../car-Price/CarPriceInput.vue'
import CarPriceRange from '../car-Price/CarPriceRange.vue'

export default {
  components: { CarPriceInput, CarPriceRange },

  emits: ['update:model-value', 'car-price-updated'],

  data() {
    return {
      carPrice: '',
    }
  },

  watch: {
    carPrice(newValue) {
      this.$emit('car-price-updated', newValue)
      console.log(newValue)
    },
  },
}
</script>

<template>
  <div>
    <h3>Цена: {{ carPrice }}</h3>

    <CarPriceInput v-model="carPrice" />

    <CarPriceRange v-model="carPrice" />
  </div>
</template>
