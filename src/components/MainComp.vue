<template>
  <div class="bg-black d-flex container flex-wrap overflow-auto">
    <div class="container text-light">
      <h1>Movies</h1>
      <div class="d-flex">
        <FilmList v-for="(elem, index) in card" :key="index" :card="elem" />
      </div>
    </div>
    <div class="container text-light">
      <h1>Series</h1>
      <div class="d-flex">
        <TvList v-for="(elem, index) in tvcard" :key="index" :tvcard="elem" />
      </div>
    </div>
  </div>
</template>

<script>
import FilmList from "./FilmList.vue";
import TvList from "./TvList.vue";

export default {
  name: "MainComp",
  components: {
    FilmList,
    TvList,
  },
  props: {
    card: Array,
    tvcard: Array,
  },
  methods: {},
  mounted() {
    //console.log(this.card.original_title + "main")
  },
};
</script>

<style lang="scss" scoped>
</style>