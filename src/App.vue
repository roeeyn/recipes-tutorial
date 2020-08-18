<template>
  <main>
    <Header />
    <section class="wrapper">
      <div class="content">
        <section class="description-container">
          <div class="description">
            <meal-description :meal="meal" />
          </div>
          <div class="picture">
            <Photo :imgUrl="meal.strMealThumb" />
          </div>
        </section>
        <instructions :instructions="meal.strInstructions" />
      </div>
    </section>
  </main>
</template>

<script>
import Header from "./components/Header.vue";
import Instructions from "./components/Instructions.vue";
import Photo from "./components/Photo.vue";
import MealDescription from "./components/MealDescription.vue";

export default {
  components: {
    Header,
    Photo,
    Instructions,
    MealDescription
  },
  created() {
    fetch("https://www.themealdb.com/api/json/v1/1/random.php")
      .then(response => response.json())
      .then(data => (this.meal = data.meals[0]))
      .catch(error => console.error(error));
  },
  data: () => {
    return {
      meal: "",
      mockedData: {
        meals: [
          {
            idMeal: "52771",
            strMeal: "Spicy Arrabiata Penne",
            strDrinkAlternate: null,
            strCategory: "Vegetarian",
            strArea: "Italian",
            strInstructions:
              "Bring a large pot of water to a boil. Add kosher salt to the boiling water, then add the pasta. Cook according to the package instructions, about 9 minutes.\r\nIn a large skillet over medium-high heat, add the olive oil and heat until the oil starts to shimmer. Add the garlic and cook, stirring, until fragrant, 1 to 2 minutes. Add the chopped tomatoes, red chile flakes, Italian seasoning and salt and pepper to taste. Bring to a boil and cook for 5 minutes. Remove from the heat and add the chopped basil.\r\nDrain the pasta and add it to the sauce. Garnish with Parmigiano-Reggiano flakes and more basil and serve warm.",
            strMealThumb:
              "https://www.themealdb.com/images/media/meals/ustsqw1468250014.jpg",
            strTags: "Pasta,Curry",
            strYoutube: "https://www.youtube.com/watch?v=1IszT_guI08",
            strIngredient1: "penne rigate",
            strIngredient2: "olive oil",
            strIngredient3: "garlic",
            strIngredient4: "chopped tomatoes",
            strIngredient5: "red chile flakes",
            strIngredient6: "italian seasoning",
            strIngredient7: "basil",
            strIngredient8: "Parmigiano-Reggiano",
            strIngredient9: "",
            strIngredient10: "",
            strIngredient11: "",
            strIngredient12: "",
            strIngredient13: "",
            strIngredient14: "",
            strIngredient15: "",
            strIngredient16: null,
            strIngredient17: null,
            strIngredient18: null,
            strIngredient19: null,
            strIngredient20: null,
            strMeasure1: "1 pound",
            strMeasure2: "1/4 cup",
            strMeasure3: "3 cloves",
            strMeasure4: "1 tin ",
            strMeasure5: "1/2 teaspoon",
            strMeasure6: "1/2 teaspoon",
            strMeasure7: "6 leaves",
            strMeasure8: "spinkling",
            strMeasure9: "",
            strMeasure10: "",
            strMeasure11: "",
            strMeasure12: "",
            strMeasure13: "",
            strMeasure14: "",
            strMeasure15: "",
            strMeasure16: null,
            strMeasure17: null,
            strMeasure18: null,
            strMeasure19: null,
            strMeasure20: null,
            strSource: null,
            dateModified: null
          }
        ]
      }
    };
  }
};
</script>

<style scoped>
.content {
  width: 60%;
  border: 3px hsl(41, 91%, 12%) solid;
  border-radius: 16px;
  padding: 18px;
  background: hsl(41, 91%, 91%);
  max-width: 850px;
  margin-top: 7%;
  margin-bottom: 22px;
}
.description-container {
  display: flex;
  flex-wrap: wrap-reverse;
}
.description {
  flex: 1;
}
.picture {
  flex: 1;
}
.wrapper {
  display: flex;
  justify-content: center;
  width: 100%;
}
main {
  min-width: 100vw;
  min-height: 100vh;
  background: hsl(155, 100%, 95%);
}
</style>
