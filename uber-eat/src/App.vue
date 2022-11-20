<template>
  <div id="app">
    <!-- <RestaurantCard />
    <RestaurantCard />
    <RestaurantCard /> -->
    <!-- <RestaurantRow /> -->
    <Home />
  </div>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  
</template>

<script>
import Home from './pages/Home'
// import RestaurantRow from './components/RestaurantRow.vue'
// import HelloWorld from './components/HelloWorld.vue'
// import RestaurantCard from './components/RestaurantCard.vue';
export default {
  name: 'App',
  // components: {
  //   HelloWorld
  // }
  components: {
    // RestaurantCard
    // RestaurantRow,
    Home,
  }
}
</script>

<style>
@import url('./style/reset.css');
@import url('https://fonts.googleapis.com/css2?family=Roboto%3Awght%40300%3B400%3B700&display=swap');
#app {
  font-family: 'Roboto', sans-serif;
  /* -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
  padding: 20px;
}
</style>
