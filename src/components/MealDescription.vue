<template>
  <div class="container">
    <div class="title-container">
      <div class="title">
        <h1>
          {{ meal.strMeal
          }}<span class="type"
            ><br> - {{ meal.strArea }},
          {{ meal.strCategory }}
          </span>
        </h1>
      </div>
    </div>
    <div>
      <ul class="tags-container">
        <li v-for="(tag, idx) in parseTags(meal.strTags)" :key="idx">
          {{ tag }}
        </li>
      </ul>
    </div>
    <h2>Ingredients</h2>
    <ul>
      <li class="ingredient" v-for="(ingredient, idx) in parseIngredients(meal)" :key="idx">
        {{ ingredient[0] }} - {{ ingredient[1] }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["meal"],
  methods: {
    parseTags(tags){
      return tags ? tags.split(",") : []
    },
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

<style scoped>
.tags-container {
  display: flex;
  list-style: none;
  padding: 0;
  margin: 0;
}
.tags-container > li {
  background: hsl(42, 82%, 58%);
  padding: 6px 12px;
  margin-right: 12px;
  border-radius: 12px;
  color: hsl(42, 82%, 18%);
}
.title-container {
  margin: 22px 0 11px 0;
  display: flex;
}
 .ingredient {
   margin-bottom: 8px;
 }
 .ingredient:hover {
   font-size: 28px;
 }
.title > h1 {
  padding: 0;
  margin: 0;
  font-size: 36px;
}
.type {
  font-size: 22px;
  font-weight: normal;
  font-style: italic;
}
.container {
  font-family: "Roboto", sans-serif;
  height: 100%;
}
</style>
