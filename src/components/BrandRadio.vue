<script>
export default {
  props: ['modelValue', 'availableBrands'],

  emits: ['update:model-value'],
}
</script>

<template>
  <div>
    <span>Brand</span>
    <div v-for="(val, key) in availableBrands">
      <label for="val">{{ val }}</label>
      <input
        type="radio"
        :value="key"
        :checked="key === modelValue"
        @input="$emit('update:model-value', $event.target.value)"
      />
    </div>
  </div>
</template>
