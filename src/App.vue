<template>
  <h1>Cryptocurrency</h1>
  <div class="cardContainer">
    <div class="wrapper">
      <Card />
    </div>
  </div>
</template>

<script>
import Card from "./components/Card";
export default {
  name: "App",
  components: { Card },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.cardContainer {
  display: flex;
  flex-direction: column;

  flex-wrap: wrap;
  overflow-x: hidden;
  margin: auto;
}

.wrapper {
  display: flex;
flex-wrap: wrap;
}
</style>
