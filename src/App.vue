<script setup>
import { ref } from "vue";

let input = ref();
/* const add = "+"
const minus = "-"
const subtract = "-"
const divide = "/"
const one = 1
const two = 2
const three = 3
const four = 4
const five = 5
const six = 6
const seven = 7
const eight = 8
const nine = 9
const zero = 0 */

function appendValue(val) {
  input.value += val;
}

function evaluate() {
  try {
    input.value = eval(input.value);
  } catch (err) {
    result.value = "Error";
  }
}

function clear() {
  input.value = "";
}
</script>

<template>
  <div class="bg-black min-h-screen">
    <div class="flex justify-center">
      <div class="">
        <form @submit.prevent>
          <input
            type="text"
            v-model="input"
            readonly
            class="border w-full h-28 mb-5 text-3xl bg-white rounded-xl"
          />
          <div class="grid grid-cols-4 justify-items-center gap-y-3">
            <button
              @click="appendValue('+')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              +
            </button>
            <button
              @click="appendValue('7')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              7
            </button>
            <button
              @click="appendValue('8')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              8
            </button>
            <button
              @click="appendValue('9')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              9
            </button>
            <button
              @click="appendValue('-')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              -
            </button>
            <button
              @click="appendValue('4')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              4
            </button>
            <button
              @click="appendValue('5')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              5
            </button>
            <button
              @click="appendValue('6')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              6
            </button>
            <button
              @click="appendValue('*')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              *
            </button>
            <button
              @click="appendValue('1')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              1
            </button>
            <button
              @click="appendValue('2')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              2
            </button>
            <button
              @click="appendValue('3')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              3
            </button>
            <button
              @click="appendValue('/')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              /
            </button>
            <button
              @click="appendValue('0')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              0
            </button>
            <button
              @click="appendValue('.')"
              class="rounded-full size-20 bg-gray-300 text-3xl"
            >
              .
            </button>
            <button @click="evaluate()" class="rounded-full size-20 bg-blue-400 text-3xl">
              =
            </button>
            <button @click="clear()" class="rounded-full size-20 bg-gray-300 text-3xl">
              C
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
