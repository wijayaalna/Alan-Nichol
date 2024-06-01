<template>
  <div class="flex flex-col items-center">
    <input 
      type="text" 
      v-model="inputText" 
      placeholder="Isi nama anda" 
      class="px-4 py-2 border rounded w-96 mb-4" 
    />
    <button @click="changeText" class="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-700">
      Submit
    </button>
  </div>
</template>

<script setup>
import { ref, defineEmits } from 'vue';

const emit = defineEmits(['change-text']);
const inputText = ref('');

function changeText() {
  emit('change-text', inputText.value);
  inputText.value = ''; 
}
</script>
