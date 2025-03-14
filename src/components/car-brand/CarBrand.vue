<script>
import BrandInputText from '../car-brand/BrandInputText.vue'
import BrandTextarea from '../car-brand/BrandTextarea.vue'
import BrandSelect from '../car-brand/BrandSelect.vue'
import BrandRadio from '../car-brand/BrandRadio.vue'

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
    <h3>Выберите Бренд</h3>

    <button @click="availableBrands[carBrand] = carBrand">ADD</button>

    <BrandInputText v-model="carBrand" />

    <BrandTextarea v-model="carBrand" />

    <BrandSelect v-model="carBrand" :available-brands="availableBrands" />

    <BrandRadio v-model="carBrand" :available-brands="availableBrands" />
  </div>
</template>
