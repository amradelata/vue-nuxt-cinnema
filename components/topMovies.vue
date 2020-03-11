<template>
  <div class="topmovis">
    <div class="cards">
      <div class="card" v-for="movie in topMovies" :key="movie.id">
        <nuxt-link to="seats">
          <div
            class="image"
            :style="{ backgroundImage: 'url(' + 'http://image.tmdb.org/t/p/w780/'+ movie.backdrop_path + ')' }"
          ></div>
          <div class="content">
            <h3>{{movie.title}}</h3>
            <p style="color: #ffeb3b">{{movie.vote_average}} / 10</p>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
const API =
  "https://api.themoviedb.org/3/discover/movie?sort_by=popularity.desc&api_key=f305b625a831b59ac3860c237234faae";
export default {
  data() {
    return {
      topMovies: []
    };
  },
  async created() {
    const res = await axios.get(API);
    this.topMovies = res.data.results;
  }
};
</script>

<style>
.cards {
  display: flex;
  flex-wrap: wrap;
}

.card {
  flex-basis: calc(33.333% - 10px);
  display: inline-block;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
  margin: 5px;
  overflow: hidden;
  background: #063b34;
}
.card:hover {
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 50px 50px rgba(0, 0, 0, 0.22);
}
.card .image {
  width: 100%;
  height: 500px;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;
}

.card .content {
  padding: 15px;
  text-align: center;
  color: #dcdde1;
}
.card .content h3 {
  margin: 0;
  font-size: 25px;
  color: #dcdde1;
}
.card .content p {
  margin: 0;
  font-size: 20px;
  font-weight: bold;
}
@media screen and (max-width: 768px) {
  .card {
    flex-basis: calc(100% - 10px);
  }
  .contaner {
    padding: 0;
  }
}
</style>