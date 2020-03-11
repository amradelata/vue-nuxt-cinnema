<template>
  <div>
    <myNavBar />
    <div class="singlePage contaner">
      <div class="mycontent">
        <label class="is-size-2">SEAT INFORMTION</label>
        <p class="is-size-3">{{single.title}}</p>
        <div v-if="single.booked === true">
          <p class="is-size-3 has-text-primary">This seat is available 😃</p>
          <input type="number" class="input is-primary" placeholder="CARD NUMPER" />
          <input type="number" class="input is-primary" placeholder="CARD EX" />
          <button
            @click="book(index = single.id)"
            class="button mybutton is-primary is-outlined"
          >Book Now</button>
        </div>
        <div
          v-if="single.booked === false"
          class="is-size-3 has-text-danger"
        >sorry this seat is taken 😥</div>
      </div>
    </div>
    <myFooter />
  </div>
</template>

<script>
import axios from "axios";
import myNavBar from "~/components/myNavBar.vue";
import myFooter from "~/components/myFooter.vue";
const singleAPI = "http://localhost:4000/cinemaSeats";
export default {
  components: {
    myNavBar,
    myFooter
  },
  data() {
    return {
      id: this.$route.params.id,
      seats: []
    };
  },
  computed: {
    single() {
      return this.seats;
    }
  },
  async created() {
    const res = await axios.get(`http://localhost:4000/cinemaSeats/${this.id}`);
    this.seats = res.data;
  },
  methods: {
    async book(index) {
      const res = await axios.patch(singleAPI + "/" + index, {
        booked: false
      });
      const edit = await axios.get(singleAPI);
      this.singleAPI = res.edit;
    }
  }
};
</script>

<style>
body {
  background: #072327;
  color: aliceblue;
}
.singlePage {
  text-align: center;
  height: 80vh;
}
.mycontent {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
input {
  margin-top: 35px;
  margin-bottom: 35px;
}
.mybutton {
  margin-bottom: 50px;
}
</style>