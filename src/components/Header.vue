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
   background: gray;
   padding: 0 20px;
 }
 .description {
   flex: 8;
   display: flex;
   justify-content: right;
 }
 .title {
   flex: 2
 }
</style>
