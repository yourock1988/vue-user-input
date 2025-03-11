<script>
export default {
  props: ['modelValue', 'carBrandUpdated'],

  emits: ['update:model-value'],
}
</script>

<template>
  <div>
    <label for="">Brand</label>
    <select
      :value="modelValue"
      @input="$emit('update:model-value', $event.target.value)"
    >
      <option v-for="(val, key) in carBrandUpdated" :key="key" :value="key">
        {{ val }}
      </option>
    </select>
  </div>
</template>
