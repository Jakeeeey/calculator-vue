<script setup>
import { ref } from "vue";

const currentInput = ref("");

// Add number
const appendNumber = (num) => {
  currentInput.value += num;
};

// Add operator
const appendOperator = (op) => {
  if (currentInput.value === "") return;
  const lastChar = currentInput.value.slice(-1);
  if ("+-*/".includes(lastChar)) {
    currentInput.value = currentInput.value.slice(0, -1) + op;
  } else {
    currentInput.value += op;
  }
};

// Clear input
const clear = () => {
  currentInput.value = "";
};

// Delete last character
const deleteLast = () => {
  currentInput.value = currentInput.value.slice(0, -1);
};

// Calculate result
const calculate = () => {
  try {
    currentInput.value = eval(currentInput.value).toString();
  } catch {
    currentInput.value = "Error";
  }
};
</script>

<template>
  <div class="flex flex-col items-center justify-center min-h-screen bg-gray-100">
    <div class="flex flex-col w-full md:w-md bg-white p-4 md:rounded-2xl shadow-lg">
      <!-- Display -->
      <div class="bg-gray-200 text-right text-6xl p-3 py-9 rounded-lg mb-8 md:mb-4">
        {{ currentInput || "0" }}
      </div>

      <!-- Buttons -->
      <div class="grid grid-cols-4 gap-2">
        <button @click="clear" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">C</button>
        <button @click="deleteLast" class="bg-gray-300 rounded-lg p-6 text-2xl font-bold hover:bg-gray-400">⌫</button>
        <button @click="appendOperator('/')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">÷</button>
        <button @click="appendOperator('*')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">×</button>

        <button @click="appendNumber('7')" class="bg-gray-300 rounded-lg p-6 text-2xl font-bold hover:bg-gray-400">7</button>
        <button @click="appendNumber('8')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">8</button>
        <button @click="appendNumber('9')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">9</button>
        <button @click="appendOperator('-')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">−</button>

        <button @click="appendNumber('4')" class="bg-gray-300 rounded-lg p-6 text-2xl font-bold hover:bg-gray-400">4</button>
        <button @click="appendNumber('5')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">5</button>
        <button @click="appendNumber('6')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">6</button>
        <button @click="appendOperator('+')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">+</button>

        <button @click="appendNumber('1')" class="bg-gray-300 rounded-lg p-6 text-2xl font-bold hover:bg-gray-400">1</button>
        <button @click="appendNumber('2')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">2</button>
        <button @click="appendNumber('3')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">3</button>
        <button @click="calculate" class="bg-blue-500 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400 row-span-2 text-white">=</button>

        <button @click="appendNumber('0')" class="bg-gray-300 rounded-lg p-6 text-2xl font-bold hover:bg-gray-400 col-span-2">0</button>
        <button @click="appendNumber('.')" class="bg-gray-300 rounded-lg p-3 text-2xl font-bold hover:bg-gray-400">.</button>
      </div>
    </div>
  </div>
</template>



