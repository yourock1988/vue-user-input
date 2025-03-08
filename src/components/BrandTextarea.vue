<script>
export default {
  // props: ['carBrand'],

  // emits: ['carBrandUpdated'],
  data() {
    return {
      carBrand: '',
      // availableBrands: ['mercedes', 'audi', 'ford'],
      // availableBrands: { mercedes: 'Мерседес', audi: 'Ауди', ford: 'Форд' },
    }
  },
  // watch: {
  //   carBrand(newValue) {
  //     console.log(newValue + '!!!')
  //   },
  // },
}
</script>
<template>
  <div>
    <label for="">Brand</label>
    <textarea
      v-model="carBrand"
      :carBrand="carBrand"
      :value="carBrand"
      @input="$emit('carBrandUpdated', $event.target.value)"
    ></textarea>
  </div>
</template>
