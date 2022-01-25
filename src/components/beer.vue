<template>
  <div class="result">
    <div class="content" v-if="beer">
      <p>Брэнд: {{ beer.brand }}</p>
      <p>Название: {{ beer.name }}</p>
      <p>Вид: {{ beer.style }}</p>
      <p>Alc/strong: {{ beer.alcohol }}/{{ beer.blg }}</p>
    </div>
    <div class="content" v-else>
      <Button title="BEER" :getBeer="getBeer" />
    </div>
    <Button title="BEER" :getBeer="getBeer" v-if="beer" />
  </div>
</template>
<script>
import Button from "./button.vue";
export default {
  name: "Beer",
  props: ["beer", "getBeer"],
  components: {
    Button,
  },
};
</script>
<style scoped>
@media (min-width: 768px) {
  .result {
    padding: 20px;
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
@media(max-width: 768px){
  .result {
    padding: 20px;
    background: #f14f29;
    grid-column-start: 1;
    grid-column-end: 5;
     grid-row-start: 3;
    grid-row-end: 5;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .content {
  }

  .content > p {
    text-align: center;
    line-height: 150%;
    font-size: 1rem;
    color: black;
  }
}
</style>
