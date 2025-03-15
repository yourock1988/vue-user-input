<script>
export default {
  props: ['modelValue'],

  emits: ['update:model-value'],
  data() {
    return {
      digits: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9],
      number: '',
    }
  },

  computed: {
    structuredNumber() {
      return this.modelValue.toString().split('').map(Number)
    },
  },
  methods: {
    updateNumber(index, value) {
      let numberArray = this.structuredNumber.slice()
      numberArray[index] = +value
      this.number = +numberArray.join('')
      this.$emit('update:model-value', this.number)
    },
  },
}
</script>

<template>
  <h1>{{ this.modelValue }}</h1>
  <h2>{{ structuredNumber }}</h2>
  <div>
    <select
      v-for="(partVal, partKey) in structuredNumber"
      :key="partKey"
      :value="partVal"
      @change="updateNumber(partKey, $event.target.value)"
    >
      <option v-for="digit of digits" :key="digit">
        {{ digit }}
      </option>
    </select>
  </div>
</template>

<style>
select,
option {
  font-size: 24px;
  font-family: sans-serif;
  color: #234;
  font-weight: bold;
  padding: 5px;
}
</style>
