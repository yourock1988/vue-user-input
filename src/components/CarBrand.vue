<script>
import BrandInputText from './BrandInputText.vue'
import BrandTextarea from './BrandTextarea.vue'
import BrandSelect from './BrandSelect.vue'
import BrandRadio from './BrandRadio.vue'

export default {
  components: { BrandInputText, BrandTextarea, BrandSelect, BrandRadio },

  props: ['carBrandUpdated'],

  emits: ['availableBrands'],

  data() {
    return {
      carBrand: '',
      availableBrands: { mercedes: 'Мерседес', audi: 'Ауди', ford: 'Форд' },
    }
  },
}
</script>
<template>
  <div>
    <h2>Brand</h2>

    <button @click="availableBrands[carBrand] = carBrand">ADD</button>

    <BrandInputText v-model="carBrand" />

    <BrandTextarea v-model="carBrand" />

    <BrandSelect v-model="carBrand" :available-brands="availableBrands" />

    <BrandRadio v-model="carBrand" :available-brands="availableBrands" />
  </div>
</template>
