<template>
  <div class="flex items-center justify-center min-h-screen">
    <div class="p-8 text-center">
      <h1 class="text-2xl text-black-500 mb-4">Nama Data Sekolah</h1>
      <ChildComponent @change-text="addText" />
      <div v-if="formData.length">
        <h2 class="text-xl text-black-500 mt-4 mb-2">Data yang telah dimasukkan:</h2>
        <ul>
          <li v-for="(data, index) in formData" :key="index" class="text-black-500 flex justify-between mb-2">
            <span class="flex-grow">{{ data }}</span>
            <button @click="deleteText(index)" class="px-2 py-1 mr-20 bg-red-500 text-white rounded hover:bg-red-700">Delete</button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ChildComponent from './ChildComponent.vue';

const formData = ref([]);

function addText(newText) {
  formData.value.push(newText);
}

function deleteText(index) {
  formData.value.splice(index, 1);
}
</script>
