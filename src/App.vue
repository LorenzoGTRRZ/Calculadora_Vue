<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
      resultado: 0
    }
  },
  watch: {
    operacao() {
      this.calculate();
    },
    numero2() {
      this.calculate();
    },
    operacao() {
      this.calculate();
    }
  },
  methods: {
    calculate() {
      switch(this.operacao) {
        case '+':
          this.resultado = parseFloat(this.numero1) + parseFloat(this.numero2);
          break;
        case '-':
          this.resultado = parseFloat(this.numero1) - parseFloat(this.numero2);
          break;
        case '*':
          this.resultado = parseFloat(this.numero1) * parseFloat(this.numero2);
          break;
        case '/':
          this.resultado = parseFloat(this.numero1) / parseFloat(this.numero2);
          break;
      }
    }
  }
}
</script>

<template>
  <div class="container mt-5 bg-light">
    <div class="row">
      <div class="col">
        <input type="number" class="form-control" v-model.number="numero1">
      </div>
      <div class="col">
        <select class="form-control" v-model="operacao">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
      </div>
      <div class="col ">
        <input type="number" class="form-control" v-model.number="numero2">
      </div>
    </div>
    <div class="row mt-3">
      <div class="col ">
        <h4>Resultado: {{ resultado }}</h4>
      </div>
    </div>
  </div>
</template>


<style scoped>
</style>
