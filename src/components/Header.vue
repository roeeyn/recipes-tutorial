<template>
  <section class="header-container">
    <div class="title">
      <p>Random Recipe</p>
    </div>
    <div class="description">
      <p>Each time you refresh, you receive a random recipe</p>
    </div>
  </section>
</template>

<style scoped>
 .header-container {
   display: flex;
   flex-wrap: wrap;
   font-family: "Roboto", sans-serif;
   background: hsl(153, 60%, 80%);
   padding: 0 20px;
 }
 .description {
   flex: 8;
   display: flex;
   min-width: 175px;
   justify-content: right;
 }
 .title {
   flex: 2;
   min-width: 80px;
 }
</style>
