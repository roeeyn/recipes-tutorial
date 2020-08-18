<template>
  <div class="container">
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
   background: deepskyblue;
 }

</style>
