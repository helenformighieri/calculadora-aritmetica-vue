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
      Resultado: <span>{{ result }}</span>
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
  padding: 3%;
}

input{
  width: 25%;
  font-weight: 800;
  border: 2px solid hotpink;
}

select{
  margin: 10px;
  color: hotpink;
  border: none;
}

input:focus, input:focus{
  outline: none;
}

.resultado{
  margin: 15px;
  display: block;
  font-weight: 800;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

span{
  display: block;
  margin: auto;
  width: 100px;
  border: 3px solid hotpink;
  border-radius: 50px;
}
</style>
