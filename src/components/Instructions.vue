<template>
  <div class="container">
    <h1>Instructions</h1>
    <p>
      {{ instructions }}
    </p>
  </div>
</template>

<script>
export default {
  props: ["instructions"]
}

</script>
<style scoped>
 .container {
   font-family: "Roboto", sans-serif;
   line-height: 30px;
 }

</style>
