<template>
  <div>
    <myNavBar />
    <div class="movieseats container">
      <h4 class="screen is-size-1">screen</h4>
      <table class="table is-bordered" v-for="seat in movieseat" :key="seat.id">
        <nuxt-link :to="'seats/' + seat.id">
          <th v-if="seat.booked === true" class="is-primary is-outlined border">
            {{seat.title}}
            {{seat.booked}}
          </th>
          <th v-if="seat.booked === false" class="is-danger is-outlined border">
            {{seat.title}}
            {{seat.booked}}
          </th>
        </nuxt-link>
      </table>
    </div>
    <myFooter />
  </div>
</template>

<script>
const seatAPI = "http://localhost:4000/cinemaSeats";
import axios from "axios";
import myNavBar from "~/components/myNavBar.vue";
import myFooter from "~/components/myFooter.vue";
export default {
  components: {
    myNavBar,
    myFooter
  },
  data() {
    return {
      movieseat: [],
      backgroundRed: "red",
      backgroundBlack: "gray",
      colorwhite: "#ecf0f1",
      fontSize: 20
    };
  },
  async created() {
    const res = await axios.get(seatAPI);
    this.movieseat = res.data;
  }
};
</script>

<style>
.border {
  border: 1px solid #fff !important;
}
table,
th {
  display: inline-block;
  cursor: pointer;
  background: #363636;
}
th {
  width: 110px;
  height: 110px;
}
.screen {
  margin-bottom: 100px;
  border: 1px solid #000;
  text-align: center;
  border: 1px solid #fff;
}
.movieseats {
  height: fit-content;
  text-align: center;
  margin-top: 100px;
  margin-bottom: 100px;
}
body {
  background: #072327;
  color: aliceblue;
}
</style>