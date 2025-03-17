<script>
export default {
  components: {},
  props: ['modelValue'],

  emits: ['update:model-value'],

  data() {
    return {}
  },
  methods: {
    updateValue(newValue) {
      this.$emit('update:model-value', newValue)
    },
  },
}
</script>
<template>
  <div>
    <label>Да</label>
    <input
      name="radio"
      type="radio"
      :value="true"
      :checked="modelValue"
      @change="updateValue(true)"
    />
  </div>
  <div>
    <label>Нет</label>
    <input
      name="radio"
      type="radio"
      :value="false"
      :checked="!modelValue"
      @change="updateValue(false)"
    />
  </div>
</template>
