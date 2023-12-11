<script setup>
import { ref } from "vue"


const valuueModel = ref("")
const emits = defineEmits(['addModule'])

function addModule(valuueModel) {
  emits('addModule', valuueModel)
}
</script>

<template>
  <select class="w-48 outline-none border border-gray-300 rounded-[5px] py-2 pl-2" v-model="valuueModel" >
     <option disabled value="">Seleccione un modulo</option>
    <option  value="0" class="outline-none border-none border-0">Modulo 1</option>
    <option  value="1" class="outline-none border-none border-0">Modulo 2</option>
    <option  value="2" class="outline-none border-none border-0">Modulo 3</option>
  </select>

  <button
    class="bg-purple-400 text-white mx-6 p-2 rounded-[5px] hover:bg-purple-600"
    @click="addModule(valuueModel)"
  >
    Agregar Turno
  </button>
</template>
