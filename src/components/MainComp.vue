<template>
  <div>
    <FilmList v-for="(elem, index) in card"
          :key="index"
          :card="elem"/>
  </div> 
</template>

<script>
import FilmList from "./FilmList.vue"


export default {
  name: "MainComp",
  components: {
    FilmList
  },
  props: {
    card: Object,
  },
  methods : {

  },
  mounted() {
    console.log(this.card.original_title + "main")
  },
}
</script>

<style lang="scss" scoped>

</style>