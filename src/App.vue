<script setup>
import { ref } from "vue";

let input = ref("");

function appendValue(val) {
  input.value += val;
}

function evaluate() {
  try {
    input.value = eval(input.value).toString();
  } catch (err) {
    input.value = "Error";
  }
}

function clear() {
  input.value = "";
}

function erase() {
  input.value = input.value.slice(0, -1);
}
</script>

<template>
  <div class="bg-gray-800 min-h-screen">
    <div class="flex justify-center md:pt-15 max-sm:min-h-screen">
      <div class="bg-black py-5">
        <form @submit.prevent>
          <div class="flex justify-center">
            <input
              type="text"
              v-model="input"
              readonly
              class="focus:outline-none w-[96%] ps-3 h-40 mb-5 bg-gray-800 rounded-xl text-5xl text-white"
            />
          </div>

          <div class="grid grid-cols-4 justify-items-center gap-y-3">
            <button
              @click="clear()"
              class="rounded-full size-20 bg-yellow-500 text-white text-5xl font-bold cursor-pointer hover:bg-yellow-400"
            >
              C
            </button>
            <button
              @click="erase()"
              class="rounded-full size-20 bg-yellow-500 text-white text-5xl font-bold cursor-pointer hover:bg-yellow-400"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="size-12 ms-3"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M10.5 19.5 3 12m0 0 7.5-7.5M3 12h18"
                />
              </svg>
            </button>
            <button></button>
            <button></button>
            <button
              @click="appendValue('+')"
              class="rounded-full size-20 bg-yellow-500 text-white text-5xl font-bold cursor-pointer hover:bg-yellow-400"
            >
              +
            </button>
            <button
              @click="appendValue('7')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              7
            </button>
            <button
              @click="appendValue('8')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              8
            </button>
            <button
              @click="appendValue('9')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              9
            </button>
            <button
              @click="appendValue('-')"
              class="rounded-full size-20 bg-yellow-500 text-white text-5xl font-bold cursor-pointer hover:bg-yellow-400"
            >
              -
            </button>
            <button
              @click="appendValue('4')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              4
            </button>
            <button
              @click="appendValue('5')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              5
            </button>
            <button
              @click="appendValue('6')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              6
            </button>
            <button
              @click="appendValue('*')"
              class="rounded-full size-20 bg-yellow-500 text-white text-5xl font-bold cursor-pointer hover:bg-yellow-400"
            >
              x
            </button>
            <button
              @click="appendValue('1')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              1
            </button>
            <button
              @click="appendValue('2')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              2
            </button>
            <button
              @click="appendValue('3')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              3
            </button>
            <button
              @click="appendValue('/')"
              class="rounded-full size-20 bg-yellow-500 text-white text-5xl font-bold cursor-pointer hover:bg-yellow-400"
            >
              &#247;
            </button>
            <button
              @click="appendValue('0')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              0
            </button>
            <button
              @click="appendValue('.')"
              class="rounded-full size-20 bg-gray-500 text-white text-5xl font-bold cursor-pointer hover:bg-gray-400"
            >
              .
            </button>
            <button
              @click="evaluate()"
              class="rounded-full size-20 bg-blue-500 text-white text-5xl font-bold cursor-pointer hover:bg-blue-400"
            >
              =
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
