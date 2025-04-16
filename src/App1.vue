<script setup>
import { ref } from "vue";

let firstNumber = ref();
let secondNumber = ref();
let operator = ref("+");
let result = ref();
let resultText = ref("");

const calculate = () => {
  if(operator.value === "+"){
    result.value = parseFloat(firstNumber.value) + parseFloat(secondNumber.value)
    resultText.value = "Result: " + result.value
  }if(operator.value === "-"){
    result.value = parseFloat(firstNumber.value) - parseFloat(secondNumber.value)
    resultText.value = "Result: " + result.value
  }if(operator.value === "*"){
    result.value = parseFloat(firstNumber.value) * parseFloat(secondNumber.value)
    resultText.value = "Result: " + result.value
  }if(operator.value === "/"){
    result.value = parseFloat(firstNumber.value) / parseFloat(secondNumber.value)
    resultText.value = "Result: " + result.value
  }
};
</script>

<template>
  <div class="bg-black min-h-screen w-screen">
    <div class="flex justify-center">
      <div class="border border-white p-5 bg-white space-y-5">
        <h1 class="text-2xl text-center">Online Calculator</h1>
        <form @submit.prevent class="flex flex-wrap flex-row gap-4">
          <input
            type="text"
            v-model="firstNumber"
            class="border"
            placeholder="Enter a number"
            readonly
          />
          <select v-model="operator" id="operator" class="border">
            <option value="+" >+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
          </select>
          <input
            type="text"
            v-model="secondNumber"
            class="border"
            placeholder="Enter a number"
          />
          <button class="px-4 py-2 bg-blue-500 text-white cursor-pointer" @click="calculate">
            Calculate
          </button>
        </form>
        <p class="bg-green-300 text-center py-2" id="resultText">
          {{ resultText ? resultText : 'Result will be displayed here' }}
        </p>
      </div>
    </div>
  </div>
</template>
