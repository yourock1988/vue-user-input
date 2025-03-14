<script>
export default {
  components: {},
  props: ['modelValue'],

  emits: ['update:model-value'],

  data() {
    return {
      carPrice: '',
    }
  },
}
</script>
<template>
  <div>
    <label for="priceRange">price Range </label>
    <input
      type="range"
      id="priceRange"
      min="0"
      max="100000"
      :value="modelValue"
      @input="$emit('update:model-value', $event.target.value)"
    />
  </div>
</template>
<style>
#priceRange {
  width: 500px;
}
</style>
