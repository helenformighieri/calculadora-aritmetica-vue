<template>
  <div>
    <input v-model="num1" type="number" placeholder="Número 1" @input="calculate">
    <select v-model="operator" @change="calculate">
      <option value="add">+</option>
      <option value="subtract">-</option>
      <option value="multiply">*</option>
      <option value="divide">/</option>
    </select>
    <input v-model="num2" type="number" placeholder="Número 2" @input="calculate">
    <div class="resultado">
      Resultado: {{ result }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'ArithmeticCalculator',
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: 'add',
      result: 0,
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case 'add':
          this.result = this.num1 + this.num2;
          break;
        case 'subtract':
          this.result = this.num1 - this.num2;
          break;
        case 'multiply':
          this.result = this.num1 * this.num2;
          break;
        case 'divide':
          this.result = this.num1 / this.num2;
          break;
        default:
          this.result = 0;
      }
    },
  },
};
</script>

<style scoped>
*{
  display: flexbox;
  justify-content: center;
  text-align: center;
  font-size: 42px;
}
.resultado{
  margin-top: 15px;
  display: block;
}
</style>
