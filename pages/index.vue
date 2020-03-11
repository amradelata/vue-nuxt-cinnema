<template>
  <div>
    <myNavBar />
    <div class="container">
      <topMovies />
    </div>
    <myFooter />
  </div>
</template>

<script>
import myNavBar from "~/components/myNavBar.vue";
import myFooter from "~/components/myFooter.vue";
import topMovies from "~/components/topMovies.vue";
export default {
  components: {
    myNavBar,
    myFooter,
    topMovies
  }
};
</script>
<style>
body {
  background: #072327;
  color: aliceblue;
}
</style>