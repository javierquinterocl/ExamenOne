<script setup>
import { ref } from "vue";
import  ModuleAdd  from '@/components/ModuleINM.vue';

const moduleOne = ref(["XDCHH", "HT550"])
const moduleTwo = ref(["WW99", "JKPL"])
const moduleThree = ref(["LOLJ7", "NMKI"])
const inputValue = ref()
const valueIndex = ref( moduleOne.value.length + moduleTwo.value.length + moduleThree.value.length)
function addModulo(modulee) {
  if (modulee == 0) {
    moduleOne.value.push(inputValue.value);
   inputValue.value = ""
  }
  if (modulee == 1) {
    moduleTwo.value.push(inputValue.value);
    inputValue.value = ""
  }
  if (modulee == 2) {
    moduleThree.value.push(inputValue.value);
    inputValue.value = ""
  }
   valueIndex.value = moduleOne.value.length + moduleTwo.value.length + moduleThree.value.length
}

</script>

<template>
  <div class="flex flex-wrap">
    <div class="flex flex-col mx-auto mt-28 max-w-6xl rounded-xl bg-slate-200 flex-wrap px-5">
      <div class="mx-auto mt-8">
        <span class="text-xl text-center font-bold">Sistema de turnos</span>
      </div>
      <div class="mt-12 flex flex-wrap space-x-7">
        <div class="mx-auto flex flex-col w-72 rounded bg-slate-100 mb-5 flex-wrap">
          <span class="text-center text-white bg-blue-400 py-3 font-semibold rounded-t-md"
            >MODULO 1</span
          >
          <div class="p-4 flex flex-col">
            <span v-for="(modulo,index) in moduleOne" :key="index">{{ modulo }}</span>
            
          </div>
        </div>
        <div class="mx-auto flex flex-col w-72 rounded bg-slate-100 mb-5 flex-wrap">
          <span class="text-center text-white bg-orange-400 py-3 font-semibold rounded-t-md"
            >MODULO 2</span
          >
          <div class="p-4 flex flex-col">
            <span v-for="(modulo,index) in moduleTwo" :key="index">{{ modulo }}</span>
          </div>
        </div>
        <div class="mx-auto flex flex-col w-72 rounded bg-slate-100 mb-5 flex-wrap">
          <span class="text-center text-white bg-green-600 py-3 font-semibold rounded-t-md"
            >MODULO 3</span
          >
          <div class="p-4 flex flex-col">
           <span v-for="(modulo,index) in moduleThree" :key="index">{{ modulo }}</span>
          </div>
        </div>
      </div>
      <div class="mt-12 flex bg-white mb-10 py-2 rounded justify-between">
        <span class="text-xl font-semibold pl-3"
          >{{ valueIndex }} <span class="text-lg text-gray-400 pl-4">TURNOS</span></span
        >
        <div class="">
          <input
            type="text"
            class="outline-slate-300 border-2 border-gray-300 rounded px-5 w-44 mr-5 py-2"
            placeholder="Codigo" v-model="inputValue"
          />
          <ModuleAdd @addModule="addModulo"/>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
