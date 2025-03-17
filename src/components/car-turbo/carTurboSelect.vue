<script>
export default {
  components: {},
  props: ['modelValue'],

  emits: ['update:model-value'],

  data() {
    return {}
  },
  methods: {
    updateValue(event) {
      this.$emit('update:model-value', event.target.value === 'true')
    },
  },
}
</script>
<template>
  <div>
    <label for="">hasTurbo</label>
    <select name="" id="" :value="modelValue" @change="updateValue">
      <option :value="true">Да</option>
      <option :value="false">Нет</option>
    </select>
  </div>
</template>
