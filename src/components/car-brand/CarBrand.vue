<script>
import BrandInputText from './BrandInputText.vue'
import BrandTextarea from './BrandTextarea.vue'
import BrandSelect from './BrandSelect.vue'
import BrandRadio from './BrandRadio.vue'

export default {
  components: { BrandInputText, BrandTextarea, BrandSelect, BrandRadio },

  emits: ['car-brand-updated'],

  data() {
    return {
      carBrand: '',
      availableBrands: { mercedes: 'Мерседес', audi: 'Ауди', ford: 'Форд' },
    }
  },

  watch: {
    carBrand(newValue) {
      this.$emit('car-brand-updated', newValue)
    },
  },
}
</script>

<template>
  <div>
    <h2>Бренд: {{ carBrand }}</h2>

    <h3>Выберите бренд:</h3>

    <button @click="availableBrands[carBrand] = carBrand">ADD</button>

    <BrandInputText v-model="carBrand" />

    <BrandTextarea v-model="carBrand" />

    <BrandSelect v-model="carBrand" :available-brands="availableBrands" />

    <BrandRadio v-model="carBrand" :available-brands="availableBrands" />
  </div>
</template>
