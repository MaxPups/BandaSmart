<template>
  <main class="block">
    <div class="aside">
      <div class="avatar">
        <img v-bind:src="user.avatar" alt="some photo" />
      </div>
      <ul class="list">
        <li id="name">{{ user.name }} {{ user.astName }}</li>

        <li>телефон: {{ user.phone }}</li>

        <li>почта: {{ user.email }}</li>

        <li>город: {{ user.address }}</li>
      </ul>
      <button v-on:click="getBeer" id="btn" v-if="beer">BEER</button>
    </div>
    <div class="result">
      <div class="content" v-if="beer">
        <p>Брэнд: {{ beer.brand }}</p>
        <p>Название: {{ beer.name }}</p>
        <p>Вид: {{ beer.style }}</p>
        <p>Alc/strong: {{ beer.alcohol }}/{{ beer.blg }}</p>
      </div>
      <div class="content" v-else>
        <button v-on:click="getBeer" id="btn">BEER</button>
    
      </div>
    </div>
  </main>
</template>

<script>
// import axios from "axios";
// import Button from "./button.vue";
export default {
  name: "Profile",
  data() {
    return {
      user: {
        username: null,
        name: null,
        lastName: null,
        email: null,
        address: null,
        phone: null,
        avatar: null,
      },
      beer: null,
    };
  },
  methods: {
    getBeer() {
      fetch("https://random-data-api.com/api/beer/random_beer")
        .then((i) => i.json())
        .then((i) => {
          console.log(i);
          this.beer = i;
        });
    },
  },
  mounted() {
    //
    fetch("https://random-data-api.com/api/users/random_user")
      .then((i) => i.json())
      .then((i) => {
        this.user.username = i.username;
        this.user.name = i.first_name;
        this.user.lastName = i.last_name;
        this.user.avatar = i.avatar;
        this.user.email = i.email;
        this.user.address = i.address.state;
        this.user.phone = i.phone_number;
      });
    // https://random-data-api.com/api/beer/random_beer
    //  fetch('https://random-data-api.com/api/beer/random_beer')
    // .then(i=>i.json())
    // .then(i=>{
    //   console.log(i);
    //   this.beer = i;
    // })
    // i.brand i.name i.style i.alcohol i.blg(крепость)
  },
};
</script>
;
<style scoped>
main {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  height: 100vh;
  background: blue;
}
.aside {
  /* position: relative; */
  padding: 30px;
  grid-column-start: 2;
  grid-column-end: 1;
  background: #007cc2;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}
.avatar {
  width: 250px;
  height: 250px;
  border-radius: 50%;
  /* border: 1px solid red; */
  overflow: hidden;
  margin: 0 auto;
  background: white;
}
.avatar > img {
  width: 100%;
  height: 100%;
}
.list {
  list-style-type: none;
  align-items: left;
  font-size: 20px;
}
.list > li {
  text-align: left;
  line-height: 200%;
}
#name {
  font-size: 44px;
  font-weight: 900;
}
/*  next block*/
#btn {
  /* position: absolute;
  left: 50%;
  bottom: 5%; */
  width: 150px;
  height: 50px;
  border-radius: 20px;
  border: none;
  background: #f2cb1d;
  color: white;
  font-weight: 900;
  font-size: 30px;
  transition: 0.1s;
}
#btn:active {
  font-size: 28px;
  transition: 0.1s;
}
/*  */
.result{
background: #F14F29;
grid-column-start: 2;
  grid-column-end: 5;
  display: flex;
  flex-direction: column;
    align-items: center;
    justify-content: center;
}
.content {
  
}
.content > p {
    text-align: left;

  font-size: 44px;
  color: black;
}
</style>
