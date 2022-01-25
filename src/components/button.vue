<template>
  <div>
    <button class="btn" v-on:click="getBeer">{{ title }}</button>
  </div>
</template>
<script>
export default {
  name: "Button",
  props: ["title", 'getBeer']

};
</script>

<style scoped>
@media (min-width: 768px) {
  .btn {
    margin-top: 50px;
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
  .btn:active {
    font-size: 28px;
    transition: 0.1s;
  }
}
@media (max-width: 768px) {
   .btn {
    margin-top: 50px;
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
  .btn:active {
    font-size: 28px;
    transition: 0.1s;
  }
}
</style>
