<template>
  <div v-for="coin in coins" :key="coin.id" class="card">
    <h1>{{ coin.name }}</h1>
    <img :src="coin.image" :alt="coin.name" />
    <p>₹{{ coin.current_price }}</p>
  </div>
</template>

<script>
const axios = require("axios");
export default {
  name: "Card",
  data() {
    return {
      coins: [],
    };
  },
  mounted() {
    axios
      .get(
        "https://api.coingecko.com/api/v3/coins/markets?vs_currency=inr&order=market_cap_desc&per_page=100&page=1&sparkline=false"
      )
      .then((res) => {
        this.coins = res.data;
        console.log(this.coins);
      });
  },
};
</script>

<style>
.card {
  display: flex;
  justify-content: center;
  padding: 10px;
  margin: 10px;
  flex-direction: column;
  border-radius: 7px;
  height: 350px;
  width: 200px;
  cursor: pointer;

  background: rgba(255, 255, 255, 0.25);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border-radius: 10px;
  border: 1px solid rgba(255, 255, 255, 0.18);
}
</style>
