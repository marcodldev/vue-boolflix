<template>
  <div>
    <div class="card m-2" style="width: 14rem">
      <img
        :src="`http://image.tmdb.org/t/p/w342/${card.poster_path}`"
        class="card-img-top"
        alt="..."
      />
      <div class="card-body cardbodycustom">
        <h5 class="card-title">{{ card.original_title }}</h5>
        <h6>{{ card.original_language }} "{{ card.original_title }}"</h6>
        <p>{{this.transvote()}}</p>
        <p class="card-text">   
          {{ card.overview }}
          
        </p>
        <font-awesome-icon icon="fa-solid fa-star" />
      </div>
    </div>
    <h1></h1>
  </div>
</template>

<script>

export default {
  name: "FilmList",
  components: {},
  props: {
    card: Object,
  },
  methods: {
  transvote (){
    let stars = parseInt(this.card.vote_average)
      if (this.card.vote_average > 5) {
        return 5
      }
    return stars 
  }
},
mounted() {
  this.transvote (),
  // console.log(parseInt(this.card.vote_average))
  console.log(this.transvote());
},
}
</script>

<style lang="scss" scoped>
.cardbodycustom {
  max-height: 300px;
  min-height: 300px;
  overflow: auto;
}
</style>