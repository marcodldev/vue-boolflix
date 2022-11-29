<template>
    <div>
        <h1>{{card.original_title}}</h1>
        <FilmCards />
    </div>
</template>

<script>
import FilmCards from './FilmCards.vue';

export default {
  name: "FilmList" ,
  components: {
    FilmCards
  },
  props: {
    card: Object,
  },
};
</script>

<style lang="scss" scoped>
</style>