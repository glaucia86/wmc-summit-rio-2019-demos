<template>
  <div class="calculadora">
    <div class="display">0.5656565</div>
    <div class="botao">C</div>
    <div class="botao">+/-</div>
    <div class="botao">%</div>
    <div class="botao operadores">÷</div>
    <div class="botao">7</div>
    <div class="botao">8</div>
    <div class="botao">9</div>
    <div class="botao operadores">x</div>
    <div class="botao">4</div>
    <div class="botao">5</div>
    <div class="botao">6</div>
    <div class="botao operadores">-</div>
    <div class="botao">1</div>
    <div class="botao">2</div>
    <div class="botao">3</div>
    <div class="botao operadores">+</div>
    <div class="botao">0</div>
    <div class="botao">.</div>
    <div class="botao operadores">=</div>
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

.botao {
  background-color: #eee;
  border: 1px solid #333;
}

.operadores {
  background-color: orange;
  color: white;
}
</style>
