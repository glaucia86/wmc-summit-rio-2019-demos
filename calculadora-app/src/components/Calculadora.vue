<template>
  <div class="calculadora">
    <div class="display">{{ valorCorrente || '0' }}</div>
    <div @click="limpar" class="botao">C</div>
    <div @click="sinal" class="botao">+/-</div>
    <div @click="porcentagem" class="botao">%</div>
    <div @click="dividir" class="botao operadores">÷</div>
    <div @click="juntarNumeros('7')" class="botao">7</div>
    <div @click="juntarNumeros('8')" class="botao">8</div>
    <div @click="juntarNumeros('9')" class="botao">9</div>
    <div @click="multiplicar" class="botao operadores">x</div>
    <div @click="juntarNumeros('4')" class="botao">4</div>
    <div @click="juntarNumeros('5')" class="botao">5</div>
    <div @click="juntarNumeros('6')" class="botao">6</div>
    <div @click="diminuir" class="botao operadores">-</div>
    <div @click="juntarNumeros('1')" class="botao">1</div>
    <div @click="juntarNumeros('2')" class="botao">2</div>
    <div @click="juntarNumeros('3')" class="botao">3</div>
    <div @click="somar" class="botao operadores">+</div>
    <div @click="juntarNumeros('0')" class="botao zero">0</div>
    <div @click="ponto" class="botao">.</div>
    <div @click="resultado" class="botao operadores">=</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numeroAnterior: null,
      valorCorrente: '',
      operador: null,
      operadorClicado: false,
    };
  },

  methods: {
    // Método responsável por limpar o display da Calculadora
    limpar() {
      this.valorCorrente = '';
    },

    /*
    * Método responsável por colocar o sinal '-' ou '+' para realização de operações
    * matemáticas especiais.
    */
    sinal() {
      this.valorCorrente = this.valorCorrente.charAt(0) === '-'
        ? this.valorCorrente.slice(1)
        : `-${this.valorCorrente}`;
    },

    // Método responsável por realizar operações com 'porcentagem':
    porcentagem() {
      this.valorCorrente = `${parseFloat(this.valorCorrente) / 100}`;
    },

    // Método responsável por juntar os números no display da Calculadora:
    juntarNumeros(numero) {
      if (this.operadorClicado) {
        this.valorCorrente = '';
        this.operadorClicado = false;
      }
      this.valorCorrente = `${this.valorCorrente}${numero}`;
    },

    // Método responsável por adicionar 'ponto' no display da Calculadora:
    ponto() {
      if (this.valorCorrente.indexOf('.') === -1) {
        this.juntarNumeros('.');
      }
    },

    // Método responsável por 'resetar' o valor na Calculadora:
    setarValor() {
      this.numeroAnterior = this.valorCorrente;
      this.operadorClicado = true;
    },

    // Método responsável por realizar a operação da 'divisão' da Calculadora
    dividir() {
      this.operador = (a, b) => a / b;
      this.setarValor();
    },

    // Método responsável por realizar a operação da 'multiplicação' da Calculadora
    multiplicar() {
      this.operador = (a, b) => a * b;
      this.setarValor();
    },

    // Método responsável por realizar a operação da 'diminuir' da Calculadora
    diminuir() {
      this.operador = (a, b) => a - b;
      this.setarValor();
    },

    // Método responsável por realizar a operação da 'adição' da Calculadora
    somar() {
      this.operador = (a, b) => a + b;
      this.setarValor();
    },

    // Método responsável por apresentar o resultado das operações na Calculadora
    resultado() {
      this.valorCorrente = `${this.operador(
        parseFloat(this.numeroAnterior),
        parseFloat(this.valorCorrente),
      )}`;
      this.numeroAnterior = null;
    },
  },
};
</script>

<style scoped>
.calculadora {
  margin: 0 auto;
  width: 350px;
  font-size: 40px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
}

.display {
  grid-column: 1 / 5;
  background-color: #333;
  color: white;
}

.zero {
  grid-column: 1 / 3;
}

.botao {
  background-color: #f2f2f2;
  border: 1px solid #999;
}

.operadores {
  background-color: orange;
  color: white;
}
</style>
