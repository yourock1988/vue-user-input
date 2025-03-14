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
  <label for="priceInput">Price </label>
  <input
    type="number"
    id="priceInput"
    :value="modelValue"
    @input="$emit('update:model-value', +$event.target.value)"
  />
</template>
