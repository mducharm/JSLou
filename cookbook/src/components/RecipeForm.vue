<template>
  <div class="box columns is-centered">
    <div class="column is-one-third">
      <div class="field">
        <label class="label">Recipe Name</label>
        <div class="control">
          <input class="input" type="text" v-model="recipeName" />
        </div>
      </div>

      <div class="field has-addons">
        <div class="control is-expanded">
          <input class="input" type="text" v-model="ingredient" @keyup.enter="addIngredient" />
        </div>
        <div class="control">
          <button class="button" @click="addIngredient">Add Ingredient</button>
        </div>
      </div>

      <div class="box">
        <h3 class="title is-5">{{recipeName}}</h3>
        <ul>
          <li v-for="(ingredient, index) in recipeIngredients" :key="index">{{ ingredient }}</li>
        </ul>
      </div>

      <div class="control">
        <button @click="submitNewRecipe" class="button is-primary is-fullwidth">Add to Cookbook</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "RecipeForm",
  data() {
    return {
      recipeName: "",
      ingredient: "",
      recipeIngredients: []
    };
  },
  computed: {
    recipe() {
      return {
        name: this.recipeName,
        ingredients: this.recipeIngredients
      };
    }
  },
  methods: {
    addIngredient() {
      this.recipeIngredients.push(this.ingredient);
      this.ingredient = "";
    },
    submitNewRecipe() {
      this.$emit("new-recipe", this.recipe);
    }
  }
};
</script>
<style scoped>
label {
  text-align: left;
}
</style>