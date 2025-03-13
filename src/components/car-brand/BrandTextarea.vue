<script>
export default {
  props: ['modelValue'],

  emits: ['update:model-value'],
}
</script>

<template>
  <div>
    <label for=""> Brand </label>
    <textarea
      :value="modelValue"
      @input="$emit('update:model-value', $event.target.value)"
    ></textarea>
  </div>
</template>
