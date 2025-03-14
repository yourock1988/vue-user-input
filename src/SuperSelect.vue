<script>
export default {
  data() {
    return {
      structuredNumber: [5, 6, 7, 8, 9],

      digits: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9],
    }
  },

  computed: {
    number() {
      return +this.structuredNumber.toString().replaceAll(',', '')
    },
  },
}
</script>

<template>
  <h1>{{ number }}</h1>
  <h2>{{ structuredNumber }}</h2>
  <div>
    <select
      v-for="(partVal, partKey) in structuredNumber"
      :key="partKey"
      :value="partVal"
      @change="structuredNumber[partKey] = +$event.target.value"
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
