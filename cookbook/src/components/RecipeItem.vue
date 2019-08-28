<template>
  <div class="box">
    <h3 class="title is-5">{{ name }}</h3>

    <div class="tags">
      <div
        v-for="(ingredient, index) in ingredients"
        :key="index"
        class="tag is-primary is-medium"
      >{{ ingredient }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "RecipeItem",
  props: ["name", "ingredients"],
  data() {
    return {};
  }
};
</script>
