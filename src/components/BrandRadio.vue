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
      <label for="">{{ val }}</label>
      <input type="radio" :value="key" @input="modelValue" />
    </div>
  </div>
</template>
