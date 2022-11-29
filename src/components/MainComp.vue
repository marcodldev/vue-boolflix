<template>
  <div>
    <FilmCard />
  </div>
</template>

<script>
import FilmCard from "./FilmCard.vue"


export default {
  name: "MainComp",
  components: {
    FilmCard
  },
  props: {
    card: Object,
  },
  methods : {

  },
  mounted() {
    console.log(this.card + "main")
  },
}
</script>

<style lang="scss" scoped>

</style>