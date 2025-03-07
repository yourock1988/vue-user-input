<script>
import CarBrand from './components/CarBrand.vue'

export default {
  components: { CarBrand },
}
</script>

<template>
  <div>
    <h1>Car</h1>

    <CarBrand />

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
