<template>
  <div class="allLogo flex sb">
    <div class="singleLogo" v-for="brand in brands">
      <img :src="require(`~/assets/imgs/`+brand.logoImg)" :alt="brand.nom+' logo'">
    </div>

  </div>
</template>

<script>
export default {
  name: "leftBrands",
  data() {
    return {
      brands: [
        {nom:"Meet",logoImg:'client-meet.svg'},
        {nom:"Maker",logoImg:'client-maker.svg'},
        {nom:"DataBiz",logoImg:'client-databiz.svg'},
        {nom:"Audiophile",logoImg:'client-audiophile.svg'},
      ]
    }
  }
}
</script>

<style scoped>
.singleLogo {
  width: 23%;
}
.allLogo {
  margin-top: auto;
}
</style>
