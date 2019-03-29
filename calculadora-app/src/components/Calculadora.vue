<template>
  <div class="calculadora">
    <div class="display">0.5656565</div>
    <div class="button">C</div>
    <div class="button">+/-</div>
    <div class="button">%</div>
    <div class="button">÷</div>
    <div class="button">7</div>
    <div class="button">8</div>
    <div class="button">9</div>
    <div class="button">x</div>
    <div class="button">4</div>
    <div class="button">5</div>
    <div class="button">6</div>
    <div class="button">-</div>
    <div class="button">1</div>
    <div class="button">2</div>
    <div class="button">3</div>
    <div class="button">+</div>
    <div class="button">0</div>
    <div class="button">.</div>
    <div class="button">=</div>
  </div>
</template>

<script>
export default {
};
</script>

<style scoped>
.calculadora {
  font-size: 45px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
}

.display {
  grid-column: 1 / 5;
  background-color: red;
}

.zero {
  grid-column: 1/3;
}

.button {
  background-color: #eee;
  border: 1px solid #333;
}
</style>
