<template>
  <div class="calculadora">
    <div class="display">0.5656565</div>
    <div class="">C</div>
    <div class="">+/-</div>
    <div class="">%</div>
    <div class="">÷</div>
    <div class="">7</div>
    <div class="">8</div>
    <div class="">9</div>
    <div class="">x</div>
    <div class="">4</div>
    <div class="">5</div>
    <div class="">6</div>
    <div class="">-</div>
    <div class="">1</div>
    <div class="">2</div>
    <div class="">3</div>
    <div class="">+</div>
    <div class="">0</div>
    <div class="">.</div>
    <div class="">=</div>
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
</style>
