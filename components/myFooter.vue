<template>
  <div>
    <footer class="footer">
      <div class="mycontent has-text-centered">
        <p>
          <strong>maid</strong> by
          <a href="https://www.amradelata.com/">amradelata</a>
          .
          2020
        </p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {};
</script>

<style>
.footer {
  background-image: url("https://www.themoviedb.org/assets/2/v4/footers_v2/MadMaxFuryRoad-9f17bec5f89e26e60ad1e3af8ae17ea7a2e6921e005477046046da2fab832ce8.jpg");
  background-size: cover;
  background-position: center center;
  height: 30vh;
  position: relative;
}
.mycontent {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>