

<script setup>
import { ref } from 'vue'
const c = ref(0)
const f = ref(32)
const r = ref(0)
const k = ref(273)

function setC(e, v = +e.target.value) {
  c.value = v
  f.value = v * (9 / 5) + 32
  r.value = v * (4 / 5)
  k.value = v + 273.15
}

function setF(e, v = +e.target.value) {
  f.value = v
  c.value = (v - 32) * (5 / 9)
  r.value = (v - 32) * (4 / 9)
  k.value = (v - 32) * (5 / 9) + 273.15
}

function setR(e, v = +e.target.value) {
  r.value = v
  c.value = v * (5 / 4)
  f.value = v * (9 / 4) + 32
  k.value = v * (5 / 4) + 273.15
}

function setK(e, v = +e.target.value) {
  k.value = v
  c.value = v - 273.15
  f.value = (v - 273.15) * (9 / 5) + 32
  r.value = (v - 273.15) * (4 / 5)
}

</script>

<template>
<p class="mt-10 text-center text-3xl font-bold">Temperatur Converter</p>
<div class="flex justify-center self-center mt-10 ">
  <div class="bg-slate-300 px-10 py-8 rounded-lg shadow-lg">
    <p class="font-bold">Celsius</p>
    <input type="number" class="px-3 py-2 mb-3 font-semibold" :value="c" @change="setC"> 
    <p class="font-bold">Fahrenheit</p>
    <input type="number" class="px-3 py-2 mb-3 font-semibold" :value="f" @change="setF">
    <p class="font-bold">Reamur</p>  
    <input type="number" class="px-3 py-2 mb-3 font-semibold" :value="r" @change="setR">
    <p class="font-bold">Kelvin</p> 
    <input type="number" class="px-3 py-2 mb-3 font-semibold" :value="k" @change="setK">
  </div>
</div>
</template>
