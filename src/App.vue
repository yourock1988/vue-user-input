<script>
import CarBrand from './components/car-brand/CarBrand.vue'

export default {
  components: { CarBrand },

  data() {
    return {
      car: {
        brand: '',
      },
    }
  },
}
</script>

<template>
  <div>
    <h1>Car</h1>

    <h2>Бренд: {{ car.brand }}</h2>

    <CarBrand @car-brand-updated="car.brand = $event" />

    <select name="x10000"></select>
    <select name="x1000"></select>
    <select name="x100"></select>
    <select name="x10"></select>
    <select name="x1"></select>

    <!-- <div>
      <h2>Price</h2>
      <div>
        <label for="">Price</label>
        <input type="number" />
      </div>
      <div>
        <label for="">Price</label>
        <input type="range" />
      </div>
    </div> -->

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
