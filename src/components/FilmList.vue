<template>
    <div>
        <h1>FILMList TEXT</h1>
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
};
</script>

<style lang="scss" scoped>
</style>