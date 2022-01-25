<template>
  <div class="aside">
    <div class="avatar" v-if="data">
      <img v-bind:src="data.avatar" alt="some photo"/>
     
    </div>
    <div class="avatar_load" v-else>
      <div class="loader"></div>
    </div>
    <ul class="list">
      <li id="name">{{ data.first_name }} {{ data.last_name }}</li>

      <li>телефон: {{ data.phone_number }}</li>

      <li>почта: {{ data.email }}</li>

      <li>город: {{ data.address.city }}</li>
    </ul>
  </div>
</template>

<script>

export default {
  name: "Profile",
  props: ["data"],
  components: {
  },
 
};
</script>
;
<style scoped>
@media (min-width: 768px) {
 
  .aside {
    padding: 30px;
    grid-column-start: 1;
    grid-column-end: 2;
    background: #007cc2;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
  }
  .avatar {
    width: 60%;
    border-radius: 50%;
    overflow: hidden;
    margin: 0 auto;
    background: white;
  }
  .avatar_load {
    width: 250px;
    height: 250px;
    border-radius: 50%;
    background: white;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .loader {
    animation: loading 1s linear;
    border: 5px dashed black;
    width: 50px;
    height: 50px;
    border-radius: 50%;
  }
  @keyframes loading {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg);
    }
  }
  .avatar > img {
    width: 100%;
    height: 100%;
  }
  .list {
    list-style-type: none;
    align-items: left;
    font-size: 1rem;
  }
  .list > li {
    text-align: left;
    line-height: 200%;
  }
  #name {
    font-size: 3rem;
    font-weight: 900;
  }

  /*  */
  .result {
    background: #f14f29;
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
}
@media (max-width: 768px){ 
  .aside {
    padding: 30px;
    grid-column-start: 1;
    grid-column-end: 5;
    grid-row-start: 1;
    grid-row-end: 3;
    background: #007cc2;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
  }
  .avatar {
    width: 40%;
    border-radius: 50%;
    overflow: hidden;
    margin: 0 auto;
    background: white;
  }
  .avatar_load {
    width: 250px;
    height: 250px;
    border-radius: 50%;
    background: white;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .loader {
    animation: loading 1s linear;
    border: 5px dashed black;
    width: 50px;
    height: 50px;
    border-radius: 50%;
  }
  @keyframes loading {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg);
    }
  }
  .avatar > img {
    width: 100%;
    height: 100%;
  }
  .list {
    list-style-type: none;
    align-items: left;
    font-size: 1rem;
  }
  .list > li {
    text-align: left;
    line-height: 200%;
  }
  #name {
    font-size: 2rem;
    font-weight: 900;
  }
  /*  next block*/

  /*  */
  .result {
    background: #f14f29;
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
}




</style>
