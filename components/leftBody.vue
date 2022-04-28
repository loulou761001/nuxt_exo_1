<template>
  <div>
      <h1 class="bold">Make<br>remote work</h1>
      <p class="mainText">Get your team in sync, no matter your location. <br>Streamline processes, create team rituals, and watch productivity soar</p>
      <a href="/about"><p class="bold">Learn more</p></a>
  </div>
</template>

<script>
export default {
  name: "leftBody"
}
</script>

<style scoped>

.mainText {
  color: var(--mediumGray);
}
h1 {
  font-size: 110px;
  line-height: 0.9;
  margin-bottom: 5vw;
}
a p {
  display: inline-block;
  padding: 10px 25px;
  border-radius: 10px;
  color: var(--almostWhite);
  background-color: var(--almostBlack);
  margin-top: 3vw;
  margin-bottom: 10vw;
}
a p:hover {
  color: var(--almostBlack);
  background-color: var(--almostWhite);
  outline: solid 2px var(--almostBlack);
}
</style>
