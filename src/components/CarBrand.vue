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

    <BrandSelect
      v-model="carBrand"
      v-bind:car-brand-updated="availableBrands"
    />
    <BrandRadio v-model="carBrand" :car-brand-updated="availableBrands" />

    <!-- :car-brand="carBrand" @car-brand-updated="carBrand = $event" -->

    <!-- <div>
      <label for="">Brand</label>
      <select v-model="carBrand">
        <option v-for="(val, key) in availableBrands" :key="key" :value="key">
          {{ val }}
        </option>
      </select>
    </div> -->

    <div>
      <span>Brand</span>
      <div v-for="(val, key) in availableBrands">
        <label for="">{{ val }}</label>
        <input
          type="radio"
          :value="key"
          :checked="key === carBrand"
          @change="carBrand = $event.target.value"
        />
      </div>
    </div>
  </div>
</template>
<!-- <input
  type="radio"
  :value="key"
  :checked="key === carBrand"
  @change="carBrand = $event.target.value"
/> -->
