<script setup>
  import { ref } from "vue";
  import Axios from "axios";
  import RecipeShowVue from "../components/RecipeShow.vue";
  import SearchRecipe from "../components/SearchRecipe.vue";

  var allRecipe = ref([]);
  var allData = ref([]);

  async function getRecipes(name) {
    var recipeApi = `https://api.edamam.com/api/recipes/v2?type=public&q=${name}&app_id=bbb3e735&app_key=cbaf54fdf80717c6a9ac4a88872cefd7`;
    var recipes = await Axios.get(recipeApi);
    allData.value = recipes.data.hits;
    allRecipe.value = allData.value.map((a) => a.recipe);
    return allRecipe;
  }
  
</script>

<template>
  <main class="flex flex-col justify-center items-center">
    <SearchRecipe @getIngridient="getRecipes"/>
    <RecipeShowVue :recipes="allRecipe"/>
  </main>
</template>
