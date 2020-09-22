<template>
  <!-- ================== For Drivers ================== -->
  <div id="forDrivers" class="wrapper">
    <header>
      <h1 class="drivers">For Drivers</h1>
    </header>
    <div class="driver-text">
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi
        eveniet est rerum
        soluta eos ipsam earum architecto a facere vel doloremque cupiditate
        quisquam in, at
        incidunt autem distinctio, voluptates minus.
      </p>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import * as ScrollMagic from "scrollmagic";

export default {
  name: "Drivers",
  methods: {
    scrollDrivers() {
      var controllerDrivers = new ScrollMagic.Controller();

      // animate Drivers Header
      let animate_drivers_h1 = gsap.timeline({
        defaults: { opacity: 0, ease: "linear", autoAlpha: 0 },
      });
      animate_drivers_h1.from("header .drivers", {
        duration: 1.5,
        scale: 0,
        transformOrigin: "50% 50%",
        stagger: 0.5,
      });
      new ScrollMagic.Scene({
        triggerElement: "header .drivers",
        triggerHook: 0.9,
      })
        .setTween(animate_drivers_h1)
        .addTo(controllerDrivers);
    },
  },
  mounted: function () {
    this.scrollDrivers();
  },
};
</script>

<style scoped>
#forDrivers {
  /* height: 30%; */
  height: 30vh;
  width: 100%;
  background-image: linear-gradient(
      105deg,
      rgba(40, 40, 40, 0.5) 0%,
      rgba(40, 40, 40, 0.9) 50%,
      transparent 50%
    ),
    url("../assets/body.jpg");
}

#forDrivers header {
  display: flex;
  justify-content: left;
  align-items: center;
  height: 15vh;
  text-shadow: 2px 2px 0px rgba(0, 0, 0, 0.9);
  font-size: 3.2rem;
}

#forDrivers header h1 {
  padding: 20px;
  padding-left: 10px;
  font-weight: 600;
  color: #ccc;
  background-color: #565656;
  color: transparent;
  /* text-shadow: 2px 2px 3px rgba(40, 40, 40, 0.5); */
  text-shadow: -2px -2px rgba(0, 0, 0, 0.2);
  /* opacity: 0.7; */
  -webkit-text-fill-color: transparent;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  background-clip: text;
  filter: drop-shadow(3px 2px 0px rgba(0, 0, 0, 0.5));
}
#forDrivers .driver-text {
  padding: 20px;
  letter-spacing: 1px;
  width: 80%;
  line-height: 1.8rem;
}
/* =========================================== Small Smartphones =================================  */
/* ============================================ For Drivers ====================================== */

@media (max-width: 499px) {
  #forDrivers {
    height: auto;
  }
  #forDrivers header {
    height: auto;
    font-size: 2rem;
  }
  #forDrivers header h1 {
    padding-left: 0;
  }
  #forDrivers .driver-text {
    padding-left: 0;
    width: 100%;
    padding-top: 0;
    color: rgba(255, 255, 255, 0.6);
    padding-bottom: 2rem;
  }
}

/* ===========================================  Small Smartphones Landscape =================================  */
@media (min-width: 500px) and (max-width: 736px) {
}
</style>