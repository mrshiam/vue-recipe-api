<script setup>
defineProps({
  recipes: {
    type: Object,
  },
});
</script>

<template>
  <div class="grid gap-8 justify-items-center grid-cols-3 mt-8">
    <div v-for="recipe in recipes">
        <img class="rounded-xl" :src="recipe.image" alt="">
        <h3 class="text-center mt-2"><a :href="recipe.url">{{ recipe.label }}</a></h3>
    </div>
  </div>
</template>