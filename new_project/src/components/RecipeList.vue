<template>
  <div>
    <ul>
      <li v-for="(recipe, index) in recipes" :key="index">
        <RecipeItem :name="recipe.name" :ingredients="recipe.ingredients" />
      </li>
    </ul>
  </div>
</template>

<script>
import RecipeItem from "./RecipeItem";

export default {
  name: "RecipeList",
  components: {
    RecipeItem
  },
  data() {
    return {
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
  }
};
</script>
