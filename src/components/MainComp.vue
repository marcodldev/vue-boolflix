<template>
  <div class="bg-black d-flex container-fluid flex-wrap overflow-auto">
    
    <div class="container-fluid text-light">
      <h1 v-if="card != '' " >Movies</h1>
      <div class="d-flex container-fluid overflow-auto flex-nowrap">
        <FilmList v-for="(elem, index) in card" :key="index" :card="elem" />
      </div>
    </div>
    <div class="container-fluid text-light">
      <h1 v-if="tvcard != '' ">Series</h1>
      <div class="d-flex container-fluid overflow-auto flex-nowrap scroll">
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

::-webkit-scrollbar {
  height: 6px;
}

::-webkit-scrollbar-thumb {
  background-color: rgb(160, 8, 8);
}

::-webkit-scrollbar-track {
  background-color: black;
}

</style>