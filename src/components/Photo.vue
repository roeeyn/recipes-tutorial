<template>
  <div class="photo-container">
    <img :src="imgUrl" alt="Thumbnail" />
  </div>
</template>

<script>
export default {
  props: ["imgUrl"]
}
</script>

<style scoped>
 img {
   border-radius: 50%;
   width: 80%;
 }
</style>
