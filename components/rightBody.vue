<template>
<!--  <img src="@/assets/imgs/image-hero-desktop.png" alt="">-->
  <div class="img">
  </div>
  <!-- /.img -->
</template>

<script>
export default {
  name: "rightBody"
}
</script>

<style scoped>
  .img {
    width: 45%;
    height: auto;
    background-image: url('@/assets/imgs/image-hero-desktop.png');
    background-size: contain;
    background-repeat: no-repeat;
  }

  @media screen and (max-width: 787px) {
    .img {
      width: 100%;
      height: 80vw;
      background-image: url('@/assets/imgs/image-hero-mobile.png');
    }
  }


</style>
