<template>
  <div class="box">
    <h3 class="title is-5">{{ name }}</h3>
    <span>
      <div
        v-for="(ingredient, index) in ingredients"
        :key="index"
        class="tag is-primary"
      >
        {{ index + 1 }}: {{ ingredient }}
      </div>
    </span>
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
