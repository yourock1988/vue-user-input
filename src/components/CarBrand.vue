<script>
import BrandInputText from './BrandInputText.vue'
import BrandTextarea from './BrandTextarea.vue'

export default {
  components: { BrandInputText, BrandTextarea },
  props: ['carBrandUpdated'],

  data() {
    return {
      carBrand: '',
      // availableBrands: ['mercedes', 'audi', 'ford'],
      availableBrands: { mercedes: 'Мерседес', audi: 'Ауди', ford: 'Форд' },
    }
  },

  watch: {
    carBrand(newValue, oldValue) {
      // console.log('watch', newValue, oldValue)
    },
  },
}
</script>
<template>
  <div>
    <h2>Brand</h2>

    <button @click="availableBrands[carBrand] = carBrand">ADD</button>

    <!-- :model-value="carBrand"
    @update:model-value="carBrand = $event" -->

    <BrandInputText v-model="carBrand" />

    <BrandTextarea v-model="carBrand" />

    <!-- 

      :car-brand="carBrand"
      @car-brand-updated="carBrand = $event"

    <div>
      <label for="">Brand</label>
      <select v-model="carBrand">
        <option v-for="(val, key) in availableBrands" :key="key" :value="key">
          {{ val }}
        </option>
      </select>
    </div>

    <div>
      <span>Brand</span>
      <div v-for="(val, key) in availableBrands">
        <label for="">{{ val }}</label>
        <input type="radio" :value="key" v-model="carBrand" />
      </div>
    </div> -->
  </div>
</template>
<!-- <input
          type="radio"
          :value="key"
          :checked="key === carBrand"
          @change="carBrand = $event.target.value"
        /> -->
