<script>
export default {
  props: ['modelValue'],

  emits: ['update:model-value'],

  watch: {
    carBrand(newValue) {
      console.log(newValue + '!!!')
    },
  },
}
</script>

<template>
  <div>
    <label for="">Brand</label>
    <input
      :value="modelValue"
      @input="$emit('update:model-value', $event.target.value)"
    />
  </div>
</template>
