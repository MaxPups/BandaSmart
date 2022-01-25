<template>
  <div>
    <button id="btn" v-on:click="getBeer">{{ title }}</button>
  </div>
</template>
<script>
// import axios from "axios";
export default {
  name: "Button",
  data() {
    return {};
  },
  props: ["title", "getBeer"],
  methods: {},
};
</script>

<style scoped>
@media (min-width: 576px) {
  #btn {
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
}
@media (max-width: 576px) {
  #btn {
    position: absolute;
    left: 50%;
    bottom: 5%;
    transform: translateX(-50%);
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
}
</style>
