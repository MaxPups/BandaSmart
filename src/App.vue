<template>
  <div id="app">
    <main class="block">
      <Profile :data="user" />
      <Beer :beer="beer" :getBeer="getBeer"/>
    </main>
  </div>
</template>

<script>
import Profile from "./components/profile.vue";
import Beer from './components/beer.vue';
export default {
  name: "App",
  components: {
    Profile,
    Beer
  },
  data() {
    return {
      user: null,
      beer: null,
    };
  },
  methods: {
    getBeer() {
      fetch("https://random-data-api.com/api/beer/random_beer")
        .then((i) => i.json())
        .then((data) => {
          console.log(data);
          this.beer = data;
        });
    },
  },
  mounted() {
    fetch("https://random-data-api.com/api/users/random_user")
      .then((i) => i.json())
      .then((data) => {
        console.log(data);
        this.user = data;
      });
  },
};
</script>

<style>
* {
  margin: 0%;
  padding: 0%;
  box-sizing: border-box;
}
@media (min-width: 768px){
main {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  height: 100vh;
  background: blue;
}
}
@media (max-width: 768px){

main {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(4, 1fr);
  height: 100vh;
}
}
</style>
