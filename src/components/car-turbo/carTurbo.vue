<script>
import CarTurboCheckbox from './CarTurboCheckbox.vue'
import carTurboRadio from './carTurboRadio.vue'
import carTurboSelect from './carTurboSelect.vue'

export default {
  components: { CarTurboCheckbox, carTurboRadio, carTurboSelect },

  emits: ['car-hasTurbo-updated'],

  data() {
    return {
      hasTurbo: true,
    }
  },

  watch: {
    hasTurbo(newValue) {
      this.$emit('car-hasTurbo-updated', newValue)
    },
  },
}
</script>

<template>
  <div>
    <h2>HasTurbo: {{ hasTurbo }}</h2>

    <CarTurboCheckbox v-model="hasTurbo" />

    <carTurboRadio v-model="hasTurbo" />

    <carTurboSelect v-model="hasTurbo" />
  </div>
</template>
