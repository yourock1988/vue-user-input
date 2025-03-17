<script>
export default {
  components: {},
  props: ['modelValue'],

  emits: ['update:model-value'],

  data() {
    return {}
  },
  methods: {
    checkboxChange(event) {
      this.$emit('update:model-value', event.target.checked)
    },
  },
}
</script>
<template>
  <div>
    <label>hasTurbo</label>
    <input type="checkbox" :checked="modelValue" @change="checkboxChange" />
  </div>
</template>
