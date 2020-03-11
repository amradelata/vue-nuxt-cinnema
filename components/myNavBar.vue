<template>
  <div>
    <nav class="navbar is-transparent">
      <div class="navbar-brand">
        <a class="navbar-item" href="http://localhost:3000/">
          <img
            src="https://i.ibb.co/kXKjRG8/IMGBIN-event-tickets-balboa-theatre-discounts-and-allowances-cinema-logo-png-n-Y0v-UPit-1.png"
            alt="Bulma: a modern CSS framework based on Flexbox"
          />
        </a>
        <div
          class="navbar-burger burger"
          data-target="navbarExampleTransparentExample"
          @click="togel()"
        >
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>

      <div id="navbarExampleTransparentExample" class="navbar-menu">
        <div class="navbar-start">
          <a class="navbar-item" href="http://localhost:3000/">Home</a>
          <div class="navbar-item has-dropdown is-hoverable"></div>
        </div>

        <div class="navbar-end">
          <div class="navbar-item">
            <div class="field is-grouped">
              <p class="control">
                <a
                  class="bd-tw-button button"
                  data-social-network="mywebsite"
                  data-social-action="mywebsite"
                  target="_blank"
                  href="https://www.amradelata.com/"
                >
                  <span>My website</span>
                </a>
              </p>
              <p class="control">
                <a
                  class="button is-primary"
                  href="https://github.com/amradelata/portfolio-vue/blob/master/assets/cv/Amr-adel-ata-frontEndCV.pdf"
                >
                  <span class="icon">
                    <i class="fas fa-download"></i>
                  </span>
                  <span>Download</span>
                </a>
              </p>
            </div>
          </div>
        </div>
      </div>
    </nav>

    <nav class="navPhone" ref="navPhone">
      <div class>
        <a class href="http://localhost:3000/">
          <img
            src="https://i.ibb.co/kXKjRG8/IMGBIN-event-tickets-balboa-theatre-discounts-and-allowances-cinema-logo-png-n-Y0v-UPit-1.png"
            alt="Bulma: a modern CSS framework based on Flexbox"
          />
        </a>
      </div>

      <div>
        <div class="navbar-start">
          <a class="navbar-item" href="http://localhost:3000/">Home</a>
          <div class="navbar-item has-dropdown is-hoverable"></div>
        </div>

        <div class="navbar-end">
          <div class="navbar-item">
            <div class="field is-grouped">
              <p class="control">
                <a
                  class="bd-tw-button button"
                  data-social-network="mywebsite"
                  data-social-action="mywebsite"
                  target="_blank"
                  href="https://www.amradelata.com/"
                >
                  <span>My website</span>
                </a>
              </p>
              <p class="control">
                <a
                  class="button is-primary"
                  href="https://github.com/amradelata/portfolio-vue/blob/master/assets/cv/Amr-adel-ata-frontEndCV.pdf"
                >
                  <span class="icon">
                    <i class="fas fa-download"></i>
                  </span>
                  <span>Download</span>
                </a>
              </p>
            </div>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  methods: {
    togel() {
      this.$refs["navPhone"].classList.toggle("myblock");
    }
  }
};
</script>

<style>
.navPhone {
  display: none;
  position: absolute;
  z-index: 99999;
}
.myblock {
  display: block;
}
@media screen and (max-width: 768px) {
  .navPhone {
    width: 100%;
    background: #ffffff;
    text-align: center;
  }
  /* .navPhone .control {
    display: block;
  } */
  .field.is-grouped {
    justify-content: space-between;
  }
}
</style>