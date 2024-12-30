<script setup>
const route = useRoute();
const { data } = await useFetch('/api/tickers/?id=' + route.params.id);
console.log(data);
const coin = data.value.data[0];
console.log(coin);
</script>
<template>
    <div v-if="coin">
      <h2>{{ coin.name }} Detail page</h2>
      <table border="1 px solid">
        <thead>
          <th>Symbol</th>
          <th>Rank</th>
          <th>Price - US $</th>
          <th>Market Cap - US $</th>
        </thead>
        <tr>
          <td>{{ coin.symbol }}</td>
          <td>{{ coin.rank }}</td>
          <td>{{ coin.price_usd }}</td>
          <td>{{ coin.market_cap_usd }}</td>
        </tr>
      </table>
    </div>
  </template>