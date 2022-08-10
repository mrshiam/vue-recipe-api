<script setup>
import { defineEmits, ref } from 'vue';
  var ingridient = ref("");

const emit = defineEmits(["getIngridient"]);

    function getRecipes(){
        emit('getIngridient', ingridient.value)
    }
</script>

<template>
  <h1 class="mt-8 text-2xl text-white text-center">Find Your Recipe</h1>
    <form @submit.prevent="getRecipes" class="m-2" action="">
        <input
        class="text-black p-1 m-1 rounded"
        type="text"
        placeholder="Enter Ingridient Name"
        v-model="ingridient"
        />
        <button
        type="submit"
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-1 px-3 rounded"
        >
        Search
        </button>
    </form>
</template>