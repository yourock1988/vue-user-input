<script>
export default {
  props: ['modelValue', 'carBrandUpdated'],
  emits: ['update:model-value'],
}
</script>
<template>
  <div>
    <span>Brand</span>
    <div v-for="(val, key) in carBrandUpdated">
      <label for="val">{{ val }}</label>
      <input
        type="radio"
        :value="key"
        @input="$emit('update:model-value', $event.target.value)"
        name="carBrand"
        :checked="key === modelValue"
      />
    </div>
  </div>
</template>
