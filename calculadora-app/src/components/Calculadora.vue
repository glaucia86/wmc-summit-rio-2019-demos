<template>
  <div class="calculadora">
    <div class="display">0.5656565</div>
    <div class="">oi</div>
    <div class="">oi</div>
    <div class="">oi</div>
    <div class="">oi</div>
    <div class="">oi</div>
    <div class="">oi</div>
    <div class="">oi</div>
    <div class="">oi</div>
    <div class="">oi</div>
    <div class="">oi</div>
    <div class="">oi</div>
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
