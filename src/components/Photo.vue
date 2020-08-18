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
 .photo-container {
   display: flex;
   justify-content: center;
   align-items: center;
   width: 100%;
   height: 100%;
   min-width: 255px;
 }
 @media (max-width: 500px) {
   .photo-container {
     min-width: 144px;
   }
 }
 img {
   border-radius: 50%;
   border: 3px hsl(41, 91%, 12%) solid;
   width: 80%;
 }
</style>
