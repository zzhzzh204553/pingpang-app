<template>
  <div class="container">
    <!--    <h1>湖南长沙阳光乒协</h1>-->
    <div class="committee">
      <h2>长沙市阳光乒协组委会</h2>
      <!--      <p>（简称组委会）</p>-->
      <ul>
        <li><strong>会&emsp;长： 张军</strong></li>
        <li><strong>副会长：徐灿辉</strong></li>
        <li><strong>秘书长：杨莉</strong></li>
        <li><strong><span>委&emsp;员：</span><span>陈志林、沈云峰、汤维臣、屈屈、小蜜蜂</span></strong></li>
      </ul>
      <h2>乒协口号</h2>
      <strong>心有阳光、快乐乒乓</strong>
      <h2>乒协宗旨</h2>
      <strong>强身健体、快乐乒乓<br/>增进友谊、共同提高</strong>
    </div>

    <!--        <div class="slogan">-->
    <!--&lt;!&ndash;          <h2>口号</h2>&ndash;&gt;-->
    <!--          <p><strong>心有阳光、快乐乒乓！</strong></p>-->
    <!--        </div>-->

    <!--        <div class="purpose-principles">-->
    <!--&lt;!&ndash;          <h2>活动宗旨和原则</h2>&ndash;&gt;-->
    <!--          <p><strong>强身健体,快乐乒乓,增进友谊,共同提高</strong></p>-->
    <!--        </div>-->

    <!--    <div class="guiding-principles">-->
    <!--      <h2>组委会工作的指导方针</h2>-->
    <!--      <p><strong>认真负责、无私无畏、公平公正公开！</strong></p>-->
    <!--    </div>-->
  </div>
  <div id="app" class="page-break">
    <h2><strong>阳光乒协档位</strong></h2>
    <h3><strong>2025/04</strong></h3>
    <div v-if="loading">加载中...</div>
    <div v-else-if="error">加载失败，请稍后重试。错误信息：{{ error }}</div>
    <DataTable v-for="(players, level) in playerRanks" :key="level" :title="level" :data="formatData(players)"/>
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
  margin-top: 40px;
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

body {
  font-family: sans-serif;
  line-height: 1.6;
  margin: 20px;
  background-color: #f4f4f4;
  color: #333;
}

.container {
  background-color: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h1, h2 {
  color: #007bff;
}

h1, h2 {
  text-align: center;
  margin-bottom: 20px;
}

.committee {
  margin-bottom: 20px;

}

.committee ul {
  padding-left: 4em; /* Add left padding for indentation */
  text-align: left; /* Ensure left alignment */
  list-style-position: outside; /* Keep bullet points outside the text */
}

.slogan {
  font-style: italic;
  color: #555;
  text-align: center;
  margin-bottom: 20px;
}

.purpose-principles, .guiding-principles {
  margin-bottom: 20px;
}

strong {
  font-weight: bold;
}

@media print {
  .page-break {
    page-break-before: always;
  }
}
</style>