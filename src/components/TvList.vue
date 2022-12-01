<template>
  <div class="">
    <div class="card m-2" style="width: 14rem">
      <img
        :src="`http://image.tmdb.org/t/p/w342/${tvcard.poster_path}`"
        class="card-img-top"
        alt="..."
      />
      <div class="display">
        <div class="card-body cardbodycustom">
          <h5 class="card-title">{{ tvcard.name }}</h5>
          <h6>{{ tvcard.original_title }}</h6>
          <div class="imgcustom">
            <img
              :src="require(`../assets/${tvcard.original_language}.png`)"
              alt=""
            />
          </div>
          <font-awesome-icon
            v-for="(elem, index) in transvote()"
            :key="index"
            icon="fa-solid fa-star"
            style="color: orange"
          />
          <font-awesome-icon
            v-for="(elem, index) in transvote2()"
            :key="index"
            icon="fa-regular fa-star"
            style="color: orange"
          />
          <p class="card-text">
            {{ tvcard.overview }}
          </p>
        </div>
      </div>
    </div>
    <h1></h1>
  </div>
</template>
  
  <script>
export default {
  name: "FilmList",
  components: {},
  data() {
    return {
      stars: 0,
      starsVuote: 0,
    };
  },
  props: {
    card: Object,
    tvcard: Object,
  },
  methods: {
    transvote() {
      this.stars = parseInt(this.tvcard.vote_average) / 2;
      if (this.stars > 5) {
        return 5;
      } else if (this.stars < 5) {
        return parseInt(this.stars);
      }
    },
    transvote2() {
      this.starsVuote = 5 - this.stars;
      return this.starsVuote;
    },
  },
  mounted() {
    this.transvote(),
      // console.log(parseInt(this.card.vote_average))
      console.log(this.transvote());
  },
};
</script>
  
  <style lang="scss" scoped>
.cardbodycustom {
  max-height: 300px;
  min-height: 300px;
  overflow: auto;
}

.card-body.cardbodycustom {
  background-color: black;
  color: white;
}

.imgcustom img {
  vertical-align: middle;
  width: 30px;
}

.display {
  display: none;
  max-height: 330px;
  min-height: 330px;
}

.card:hover .display {
  display: block;
}

.card:hover .card-img-top {
  display: none;
}

</style>