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
    structuredNumber2() {
      return this.modelValue.toString().split('').map(Number)
    },
  },
  methods: {
    updateDigit(index, value) {
      let numberArray = this.structuredNumber2.slice()
      numberArray[index] = +value
      this.number = +numberArray.join('')
      this.$emit('update:model-value', this.number)
    },
  },
}
</script>

<template>
  <h1>{{ this.modelValue }}</h1>
  <h2>{{ structuredNumber2 }}</h2>
  <div>
    <select
      v-for="(partVal, partKey) in structuredNumber2"
      :key="partKey"
      :value="partVal"
      @change="updateDigit(partKey, $event.target.value)"
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
