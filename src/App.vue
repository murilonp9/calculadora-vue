<script>

export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
      resultado: 0,
    };
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case 'soma':
          this.resultado = parseFloat(this.numero1) + parseFloat(this.numero2);
          break;
        case 'subtracao':
          this.resultado = parseFloat(this.numero1) - parseFloat(this.numero2);
          break;
        case 'multiplicacao':
          this.resultado = parseFloat(this.numero1) * parseFloat(this.numero2);
          break;
        case 'divisao':
          this.resultado = parseFloat(this.numero1) / parseFloat(this.numero2);
          break;
        default:
          this.resultado = 0;
      }
    },
  },
};
</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora Aritimética - Vue</h1>
    </header>
  </div>

  <div id="app" class="container mt-5">
    <div class="form-group">
      <label for="numero1">Número 1:</label>
      <input type="number" v-model="numero1" @input="calcularResultado" class="form-control" id="numero1">
    </div>

    <div class="form-group">
      <label for="operacao">Operação:</label>
      <select v-model="operacao" @change="calcularResultado" class="form-control" id="operacao">
        <option value="soma">Soma</option>
        <option value="subtracao">Subtração</option>
        <option value="multiplicacao">Multiplicação</option>
        <option value="divisao">Divisão</option>
      </select>
    </div>

    <div class="form-group">
      <label for="numero2">Número 2:</label>
      <input type="number" v-model="numero2" @input="calcularResultado" class="form-control" id="numero2">
    </div>

    <div class="form-group">
      <label for="resultado">Resultado:</label>
      <input type="text" :value="resultado" class="form-control" id="resultado" readonly>
    </div>
  </div>
</template>

<style scoped></style>
