<template>
  <div id="app">
    <Profile title="Max" />
    <!-- <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Profile from "./components/profile/profile.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    Profile,
  },
};
</script>

<style>
* {
  margin: 0%;
  padding: 0%;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
