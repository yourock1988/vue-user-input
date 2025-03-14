<script>
import CarBrand from './components/car-brand/CarBrand.vue'
import CarPrice from './components/car-price/CarPrice.vue'
import SuperSelect from './SuperSelect.vue'

export default {
  components: { CarBrand, CarPrice, SuperSelect },

  data() {
    return {
      // single source of truth
      car: {
        brand: 'йцук',
        price: 10000,
      },
    }
  },
}
</script>

<template>
  <div>
    <SuperSelect></SuperSelect>

    <!-- <h1>Car {{ car }}</h1>

    <CarBrand @car-brand-updated="car.brand = $event" />

    <CarPrice @car-price-updated="car.price = $event" /> -->

    <!-- <div>
      <h2>HasTurbo</h2>
      <div>
        <label>hasTurbo</label>
        <input type="checkbox" />
      </div>
      <div>
        <span>hasTurbo</span>
        <div>
          <label>да</label>
          <input type="radio" />
        </div>
        <div>
          <label>нет</label>
          <input type="radio" />
        </div>
        <div>
          <label for="">hasTurbo</label>
          <select name="" id="">
            <option value="hasTurbo">да</option>
            <option value="hasTurbo">нет</option>
          </select>
        </div>
      </div>
    </div> -->
  </div>
</template>

<style>
* {
  box-sizing: border-box;
}

div {
  padding: 5px;
}

html {
  font-family: sans-serif;
  font-size: 18px;
  color: #234;
}
</style>
