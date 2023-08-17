<template>
    <div class="calculadora">
      <input v-model="numero1" type="number" @input="realizarCalculo" />
      <input v-model="numero2" type="number" @input="realizarCalculo" />
      <select v-model="operacao" @change="realizarCalculo">
        <option value="+">Soma</option>
        <option value="-">Subtração</option>
        <option value="*">Multiplicação</option>
        <option value="/">Divisão</option>
      </select>
      <div class="resultado">Resultado: {{ resultado }}</div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        numero1: '',
        numero2: '',
        operacao: "+",
        resultado: '',
      };
    },
    methods: {
      realizarCalculo() {
        switch (this.operacao) {
          case "+":
            this.resultado = this.numero1 + this.numero2;
            break;
          case "-":
            this.resultado = this.numero1 - this.numero2;
            break;
          case "*":
            this.resultado = this.numero1 * this.numero2;
            break;
          case "/":
            this.resultado = this.numero1 / this.numero2;
            break;
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .calculadora {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 20px;
  }
  
  input,
  select {
    margin: 5px;
    padding: 5px;
    font-size: 16px;
  }
  
  .resultado {
    font-size: 18px;
    margin-top: 10px;
  }
  </style>
  