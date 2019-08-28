<template>
  <div class="box">
    <div class>
      <ul class="columns is-multiline is-mobile">
        <li v-for="(recipe, index) in recipes" :key="index" class="column is-one-third">
          <RecipeItem :name="recipe.name" :ingredients="recipe.ingredients" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import RecipeItem from "./RecipeItem";

export default {
  name: "RecipeList",
  components: {
    RecipeItem
  },
  props: ["recipes"],
  data() {
    return {
      // recipes: [
      //   {
      //     name: "Parfait",
      //     ingredients: ["berries", "granola", "yogurt"]
      //   },
      //   {
      //     name: "Aglio E Olio",
      //     ingredients: ["pasta", "garlic", "olive oil", "red pepper flakes"]
      //   },
      //   {
      //     name: "Stir Fry",
      //     ingredients: ["rice", "mixed vegetables", "onion", "chicken"]
      //   }
      // ]
    };
  }
};
</script>
