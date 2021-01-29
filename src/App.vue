<template>
  <main>
    <h2>Banned ingredients for curly hair 👩🏻‍🦱</h2>
    <input type="text" v-model="query" placeholder="Search ingredient" />
    <div v-for="ingredient in filteredIngredients" :key="ingredient">
      {{ ingredient }}
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      ingredients: [
        "AD alcohol 40",
        "Alcohol Denat",
        "Alkyl benzene sulfonate",
        "Alkylbenzene sulfonate",
        "Petroleum Sodium carboxylate",
      ],
      query: "",
    };
  },

  computed: {
    filteredIngredients() {
      if (!this.query) return this.ingredients;

      return this.ingredients.filter((ingredient) =>
        ingredient.toLowerCase().includes(this.query.toLowerCase())
      );
    },
  },
};
</script>

<style>
</style>
