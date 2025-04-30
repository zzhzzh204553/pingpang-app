<template>
  <div id="app">
    <h1>岳阳市乒协档位20250325</h1>
    <div v-if="loading">加载中...</div>
    <div v-else-if="error">加载失败，请稍后重试。错误信息：{{ error }}</div>
    <DataTable v-for="(players, level) in playerRanks" :key="level" :title="level" :data="formatData(players)" />
  </div>
</template>

<script>
import appLogic from './App.js'; // Import the JavaScript logic
// import DataTable from './components/DataTable.vue';

export default {
  ...appLogic, // Use the imported logic by spreading the object
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

h1 {
  margin-bottom: 30px;
}

.loading {
  font-size: 1.2em;
  color: #777;
  margin-top: 20px;
}

.error {
  color: red;
  margin-top: 20px;
  font-weight: bold;
}
</style>