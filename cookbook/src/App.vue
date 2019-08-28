<template>
  <div id="app" class="container box">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <h3 class="title">My Cookbook</h3>
    <button @click="showRecipeForm" class="button">Add Recipe</button>
    <button @click="showRecipeList" class="button">Show Recipes</button>
    <RecipeList v-if="activeView === 1" :recipes="recipes" />
    <RecipeForm v-if="activeView === 2" @new-recipe="addRecipe" />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import RecipeList from "./components/RecipeList.vue";
import RecipeForm from "./components/RecipeForm.vue";

export default {
  name: "app",
  components: {
    // HelloWorld,
    RecipeList,
    RecipeForm
  },
  data() {
    return {
      activeView: 0,
      recipes: [
        {
          name: "Parfait",
          ingredients: ["berries", "granola", "yogurt"]
        },
        {
          name: "Aglio E Olio",
          ingredients: ["pasta", "garlic", "olive oil", "red pepper flakes"]
        },
        {
          name: "Stir Fry",
          ingredients: ["rice", "mixed vegetables", "onion", "chicken"]
        }
      ]
    };
  },
  methods: {
    showRecipeForm() {
      this.activeView = 2;
    },
    showRecipeList() {
      this.activeView = 1;
    },
    addRecipe(recipe) {
      this.recipes.push(recipe);
      this.showRecipeList();
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
html {
  background-image: url("./assets/food.jpg");
  background-attachment: fixed;
  background-size: cover;
}
</style>
