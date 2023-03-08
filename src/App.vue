<script>
export default {
  data() {
    return {
      num1:0,
      num2: 0,
      operacao:'soma',
      resultado: 0,
    };
  },
  methods: {
    calcular(){
      switch (this.operacao) {
        case 'soma':
          this.resultado = this.num1 + this.num2;
          break;
        case 'subtracao':
            this.resultado = this.num1 - this.num2;
            break;
        case 'divisao':
            this.resultado = this.num1 / this.num2;
            break;
        case 'multiplicacao':
            this.resultado = this.num1 * this.num2;
            break;
      }
    },
  },
};
</script>

  <template>
  <div class="container">
    <h1>Calculadora Aritmética</h1>
    <div class="calculator">
      <input v-model.number ="num1" type="number" placeholder="Número 1" @change="calcular"> 
    <select v-model = "operacao" @change="calcular"> 
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="divisao">/</option>
      <option value="multiplicacao">*</option>
    </select>
    <input v-model.number="num2" type="number" placeholder="Número 2" @change="calcular">
    <h2>Resultado: {{ resultado }}</h2>
    </div>
  </div>
</template>

<style>
body {
  background-color: #fafafa;
  font-family: 'Roboto', sans-serif;
  font-size: 16px;
}

.container {
  max-width: 600px;
  margin: 0 auto;
  padding: 2rem;
}

h1 {
  text-align: center;
  font-size: 3rem;
  color: #3f51b5;
  margin-bottom: 2rem;
  text-shadow: 1px 1px #ccc;
}

.calculator {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  background-color: #f2f2f2;
  padding: 2rem;
  border-radius: 5px;
  box-shadow: 5px 5px 10px #ccc;
}

input, select {
  font-size: 1.5rem;
  padding: 0.5rem;
  border: none;
  border-radius: 5px;
  box-shadow: inset 1px 1px 5px #ccc;
  margin: 0.5rem;
  width: 25%;
  text-align: center;
}

select{
  background-color: #fff;
  cursor: pointer;
}

input:focus {
  outline: none;
  box-shadow: inset 1px 1px 5px #3f51b5;
}

.calculator-button {
  background-color: #3f51b5;
  color: #fff;
  border:none;
  border-radius: 5px;
  padding: 0.5rem 2rem;
  font-size: 1.2rem;
  cursor: pointer;
  margin: 0.5rem;
  transition: all 0.2s ease-in-out;
  box-shadow: 2px 2px 5px #ccc;
}

.calculate-button:hover {
  background-color: #fff;
  color: #3f51b5;
  border: 2px 2px 5px #ccc;
}

h2 {
  text-align: center;
  font-size: 2rem;
  margin-top: 2rem;
  color: #3f51b5;
  text-shadow: 1px 1px #ccc;
}
</style>

