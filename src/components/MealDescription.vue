<template>
  <div class="container">
    <h1>{{ meal.strMeal }}</h1>
    <p>
      {{ meal.strCategory }}
      {{ meal.strArea }}
    </p>
    <ul>
      <li v-for="(ingredient, idx) in parseIngredients(meal)" :key="idx">
        {{ ingredient[0] }} - {{ ingredient[1] }}
      </li>
    </ul>
    <p>
      {{ meal.strTags }}
    </p>
  </div>
</template>

<script>
export default {
  props: ["meal"],
  methods: {
    parseIngredients(meal) {
      return Array.from({ length: 20 }, (_, i) => i)
        .map(num => [
          meal[`strIngredient${num + 1}`],
          meal[`strMeasure${num + 1}`]
        ])
        .filter(([ingredient, measure]) => ingredient && measure);
    }
  }
};
</script>
