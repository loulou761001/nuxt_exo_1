<template>

  <div class="flex sb">
    <div id="leftDiv" class="flex column">
      <div class="centerDiv">
        <leftBody />
        <leftBrands />
      </div>
    </div>
    <rightBody class="rightbody" />
  </div>
</template>


<script>
export default {
  name: 'IndexPage',
  head() {
    return {
      title: "Homepage"
    };
  },
}
</script>

<style>
.centerDiv {
  margin: auto;
}

</style>
