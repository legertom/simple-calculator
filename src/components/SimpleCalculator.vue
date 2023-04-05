<template>
    <div class="calculator">
      <input v-model="operand1" type="number" placeholder="Enter a number" />
      <select v-model="operator">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input v-model="operand2" type="number" placeholder="Enter a number" />
      <button @click="calculate">Calculate</button>
      <p>Result: {{ result }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        operand1: '',
        operand2: '',
        operator: '+',
        result: '',
      };
    },
    methods: {
      calculate() {
  const num1 = parseFloat(this.operand1);
  const num2 = parseFloat(this.operand2);

  switch (this.operator) {
    case '+':
      this.result = num1 + num2;
      break;
    case '-':
      this.result = num1 - num2;
      break;
    case '*':
      this.result = num1 * num2;
      break;
    case '/':
      if (num2 === 0) {
        alert('Division by zero is not allowed!');
        return;
      }
      this.result = num1 / num2;
      break;
    default:
      alert('Invalid operator!');
  }
}

 
    },
  };
  </script>
  
  <style scoped>
 .calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  background-color: #f5f5f5;
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  width: 300px;
}

input,
select {
  border: none;
  border-bottom: 2px solid #1976d2;
  background-color: transparent;
  outline: none;
  width: 100%;
  font-size: 18px;
  padding: 5px 0;
  color: #333;
  transition: border-color 0.3s ease-in;
}

input:focus,
select:focus {
  border-color: #2196f3;
}

button {
  background-color: #2196f3;
  border: none;
  border-radius: 5px;
  color: #fff;
  font-size: 18px;
  padding: 10px 20px;
  cursor: pointer;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s ease-in;
}

button:hover {
  background-color: #1976d2;
}

p {
  font-size: 18px;
  color: #333;
}
  </style>
  