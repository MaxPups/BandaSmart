<template>
  <div>
    <button id="btn" v-on:click="">{{ title }}</button>
  </div>
</template>
<script>
// import axios from "axios";
export default {
  name: "Button",
  data() {
    return {

    };

  },
  props: ["title", "fnc"],
  methods: {
     
  },
};
</script>

<style scoped>
#btn {
  padding: 10px 25px;
  border-radius: 12px;
  font-size: 24px;
  color: white;
  background: gold;
  border: none;
    transition:0.1s;

}
#btn:active {
  font-size: 20px;
  transition:0.1s;
}
</style>
