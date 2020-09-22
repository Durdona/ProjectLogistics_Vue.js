<template>
  <!-- ====================== Why Choose Us Page =========================== -->
  <div id="whyChooseUs" class="wrapper">
    <header>
      <h1 class="why">Why Choose Us</h1>
    </header>
    <div class="div-wrapper">
      <aside class="aside aside1">
        <!-- <img src="../assets/pittsburgh.jpg" alt="pittsburgh"> -->
        <div class="aside-text">
          <h2>On Time Delivery</h2>
          <img src="../assets/clock.svg" alt="clock" class="aside-text-svg" />
          <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Officia
            quae dolor
            reiciendis aperiam consectetur facilis aliquam ut quisquam
            suscipit,
            quasi
            sapiente vitae, nihil alias veniam recusandae est ad consequatur.
            Eaque?
          </p>
        </div>
      </aside>

      <aside class="aside aside2">
        <!-- <img src="../assets/newyork_sunset.jpg" alt="newyork"> -->
        <div class="aside-text">
          <h2>Driver Safety</h2>
          <img src="../assets/safety_.svg" alt="safety" class="aside-text-svg" />
          <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Officia
            quae dolor
            reiciendis aperiam consectetur facilis aliquam ut quisquam
            suscipit,
            quasi
            sapiente vitae, nihil alias veniam recusandae est ad consequatur.
            Eaque?
          </p>
        </div>
      </aside>

      <aside class="aside aside3">
        <!-- <img src="./assets/miami.jpg" alt="miami"> -->
        <div class="aside-text">
          <h2>Our Aim</h2>
          <img src="../assets/truck.svg" alt="driver" class="aside-text-svg" />
          <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Officia
            quae dolor
            reiciendis aperiam consectetur facilis aliquam ut quisquam
            suscipit,
            quasi
            sapiente vitae, nihil alias veniam recusandae est ad consequatur.
            Eaque?
          </p>
        </div>
      </aside>

      <aside class="aside aside4">
        <!-- <img src="./assets/california_bridge.jpg" alt="california"> -->
        <div class="aside-text">
          <h2>Outstanding Dispatching</h2>
          <img src="../assets/dispatch_.svg" alt="dispatch" class="aside-text-svg" />
          <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Officia
            quae dolor
            reiciendis aperiam consectetur facilis aliquam ut quisquam
            suscipit,
            quasi
            sapiente vitae, nihil alias veniam recusandae est ad consequatur.
            Eaque?
          </p>
        </div>
      </aside>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import * as ScrollMagic from "scrollmagic";
import { TweenMax, TimelineMax } from "gsap"; // Also works with TweenLite and TimelineLite
import { ScrollMagicPluginGsap } from "scrollmagic-plugin-gsap";
ScrollMagicPluginGsap(ScrollMagic, TweenMax, TimelineMax);

export default {
  name: "ChooseUs",
  methods: {
    chooseUsSVGs() {
      let animateChoose = gsap.timeline({
        defaults: { opacity: 0, ease: "linear", autoAlpha: 0 },
      });
      const asideSVG = document.querySelectorAll(".aside-text-svg");
      animateChoose.from(
        asideSVG,
        {
          autoAlpha: 0,
          opacity: 0.2,
          yoyo: true,
          repeat: -1,
          duration: 1,
          stagger: 1,
        },
        "-=1"
      );

      var controller = new ScrollMagic.Controller();

      // Animating h1  WhyChooseUs

      animateChoose.from("header .why", {
        duration: 1.5,
        scale: 0,
        transformOrigin: "50% 50%",
        stagger: 0.5,
      });
      new ScrollMagic.Scene({
        triggerElement: "header .why",
        triggerHook: 0.9,
      })
        .setTween(animateChoose)
        .addTo(controller);

      //  aside1 "On Time"
      new ScrollMagic.Scene({
        triggerElement: ".aside1",
        triggerHook: 0.5,
      })
        .setClassToggle(".aside1", "fade-in")
        .addTo(controller);

      //  aside2 "Driver Safety"
      new ScrollMagic.Scene({
        triggerElement: ".aside2",
        triggerHook: 0.5,
      })
        .setClassToggle(".aside2", "fade-in")
        .addTo(controller);

      //  aside3 "our Aim"
      new ScrollMagic.Scene({
        triggerElement: ".aside3",
        triggerHook: 0.5,
      })
        .setClassToggle(".aside3", "fade-in")
        .addTo(controller);

      //  aside4 "Outstanding Dispatching"
      new ScrollMagic.Scene({
        triggerElement: ".aside4",
        triggerHook: 0.5,
      })
        .setClassToggle(".aside4", "fade-in")
        .addTo(controller);
    },
  },
  mounted: function () {
    this.chooseUsSVGs();
  },
};
</script>

<style  scoped>
#whyChooseUs {
  width: 100%;
  height: 100vh;
  background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.2)),
    url("../assets/body.jpg") bottom right;
}
.div-wrapper {
  flex-flow: row wrap;
  /* text-align: center; */
  margin: 0 auto 0 auto;
  height: 80%;
}
#whyChooseUs header {
  display: flex;
  justify-content: left;
  align-items: center;
  height: 15vh;
  text-shadow: 2px 2px 0px rgba(0, 0, 0, 0.9);
  font-size: 3.2rem;
}
#whyChooseUs header h1 {
  padding: 20px;
  padding-left: 10px;
  font-weight: 600;
  color: #ccc;
  background-color: #565656;
  color: transparent;
  /* text-shadow: 2px 2px 3px rgba(40, 40, 40, 0.5); */
  text-shadow: -2px -2px rgba(0, 0, 0, 0.2);
  opacity: 0.8;
  -webkit-text-fill-color: transparent;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  background-clip: text;
  filter: drop-shadow(4px 2px 0px rgba(0, 0, 0, 0.9));
}
.aside-text h2 {
  font-weight: 400 !important;
  font-size: 2rem;
  color: bisque;
  padding: 15px;
  padding-top: 18px;
}
.aside-text p {
  padding: 15px;
  padding-bottom: 18px;
  text-align: left;
  line-height: 1.8rem;
  width: 60%;
  letter-spacing: 1px;
  /* font-size: 1.2rem; */
}
.aside {
  padding: 20px;
  margin: 20px;
  flex-basis: 47%;
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.9);
  border-radius: 10px;
  position: relative;
}

/* ==================Aside Hover Animation ====================== */
.aside:before {
  position: absolute;
  content: "";
  height: 0;
  width: 0;
  bottom: 0;
  left: 0;
  border: 8px solid transparent;
  box-sizing: border-box;
}
.aside:after {
  position: absolute;
  content: "";
  height: 0;
  width: 0;
  top: 0;
  right: 0;
  border: 8px solid transparent;
  box-sizing: border-box;
  transition: 0.6s ease-out;
  -webkit-transition: 0.6s ease-out;
}
.aside:hover {
  cursor: pointer;
}

.aside:hover:before {
  background-image: linear-gradient(
    105deg,
    rgba(255, 255, 255, 0.2) 0%,
    rgba(40, 40, 40, 0.2) 60%,
    transparent 50%
  );
  height: 100%;
  width: 100%;
  border: 2px solid lightgrey;
  border-right: none;
  border-bottom: none;
  transition: all 1s ease-in-out, width 0.5s ease-in-out 0.6s;
  -webkit-transition: all 1s ease-in-out, width 0.5s ease-in-out 0.6s;
}
.aside:hover:after {
  background-image: linear-gradient(
    105deg,
    rgba(40, 40, 40, 0.2) 0%,
    rgba(40, 40, 40, 0.2) 60%,
    transparent 50%
  );
  height: 100%;
  width: 100%;
  border: 2px solid lightgrey;
  border-left: none;
  border-top: none;
  transition: all 1s linear, width 0.5s linear 0.5s;
  -webkit-transition: all 1s linear, width 0.5s linear 0.5s;
}
/* ======================================================== Aside Hover Animation Ends here =========== */
.aside img {
  height: 90%;
  width: 100%;
  position: absolute;
  top: 20px;
  left: 200px;
  /* margin: 0 auto; */
  object-fit: contain;
  opacity: 0.3;
  padding: 40px;
}
.aside1,
.aside2,
.aside3,
.aside4 {
  background-image: linear-gradient(
    105deg,
    rgba(40, 40, 40, 0.5) 0%,
    rgba(40, 40, 40, 0.9) 60%,
    transparent 50%
  );
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;
}
.aside1,
.aside3 {
  opacity: 0;
  transform: translateX(-100px);
  transition: all 1s ease-out;
}
.aside2,
.aside4 {
  opacity: 0;
  transform: translateX(100px);
  transition: all 1s ease-out;
}
.aside1.fade-in,
.aside2.fade-in,
.aside3.fade-in,
.aside4.fade-in {
  opacity: 1;
  transform: translateX(0);
}
@media all and (min-width: 800px) {
  .div-wrapper {
    /* width: 100%; */
    display: flex;
    justify-content: space-between;
  }

  .aside1 {
    order: 1;
  }
  .aside2 {
    order: 2;
  }
  .aside3 {
    order: 3;
  }
  .aside4 {
    order: 4;
  }
}

/* =========================================== Small Smartphones =================================  */
/* ======================================== Why Choose Us Page ================================== */

@media (max-width: 499px) {
  .wrapper {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }
  #whyChooseUs {
    height: initial;
    padding-bottom: 2rem;
  }
  #whyChooseUs header {
    height: auto;
    font-size: 2rem;
  }
  #whyChooseUs header h1 {
    padding-left: 0;
  }
  .div-wrapper {
    flex-direction: column;
    text-align: center;
    height: initial;
  }
  .aside {
    padding: 0;
    margin: 0;
    flex-basis: 0;
    margin-bottom: 20px;
  }
  .aside:nth-child(4) {
    margin-bottom: 0;
  }
  .aside-text p {
    width: 100%;
    padding-top: 10px;
    font-size: 1rem;
    color: rgba(255, 255, 255, 0.6);
  }
  .aside-text h2 {
    padding-bottom: 10px;
  }
  .aside img {
    left: 0;
  }
}

/* ===========================================  Small Smartphones Landscape =================================  */
@media (min-width: 500px) and (max-width: 736px) {
  .wrapper {
    padding-left: 6%;
    padding-right: 6%;
  }
  #whyChooseUs {
    height: initial;
    padding-bottom: 2rem;
  }
  #whyChooseUs header {
    height: auto;
    font-size: 2rem;
  }
  #whyChooseUs header h1 {
    padding-left: 0;
  }
  .div-wrapper {
    flex-direction: column;
    text-align: center;
    height: initial;
  }
  .aside {
    padding: 0;
    margin: 0;
    flex-basis: 0;
    margin-bottom: 20px;
  }
  .aside:nth-child(4) {
    margin-bottom: 0;
  }
  .aside-text p {
    width: 60%;
    padding-top: 10px;
    font-size: 1rem;
    color: rgba(255, 255, 255, 0.6);
  }
  .aside-text h2 {
    padding-bottom: 10px;
  }
  .aside img {
    width: 70%;
  }
}

/* ===========================================  Tablets ==============================  */

@media (min-width: 737px) and (max-width: 980px) {
  html,
  body {
    overflow-x: hidden !important;
  }
  .wrapper {
    padding-left: 3rem;
    padding-right: 3rem;
  }
  #whyChooseUs {
    height: initial;
    padding-bottom: 35px;
  }
  #whyChooseUs header {
    height: auto;
    font-size: 2.8rem;
  }
  #whyChooseUs header h1 {
    padding-left: 0;
  }
  .div-wrapper {
    flex-direction: column;
    text-align: center;
    height: initial;
  }
  .aside {
    padding: 0;
    margin: 0;
    flex-basis: 0;
    margin-bottom: 35px;
  }
  .aside:nth-child(4) {
    margin-bottom: 0;
  }
  .aside-text p {
    width: 60%;
    padding-top: 10px;
    font-size: 1.3rem;
    color: rgba(255, 255, 255, 0.6);
  }
  .aside-text h2 {
    padding-bottom: 20px;
  }
}

/* ===========================================  Tablets  Larger Screen  | iPad Landscape Mode as well ==============================  */

@media (min-width: 981px) and (max-width: 1280px) {
  .wrapper {
    padding-left: 2rem;
    padding-right: 2rem;
  }
  #whyChooseUs {
    height: initial;
    padding-bottom: 35px;
  }
  #whyChooseUs header {
    height: auto;
    font-size: 2.8rem;
  }
  #whyChooseUs header h1 {
    padding-left: 0;
  }
  .div-wrapper {
    flex-flow: row wrap;
    text-align: center;
    height: initial;
  }
  .aside {
    flex-basis: 45vw;
    margin-right: 0;
    margin-left: 0;
  }
  .aside-text p {
    width: 60%;
    padding-top: 10px;
    font-size: 1.1rem;
    color: rgba(255, 255, 255, 0.6);
  }
  .aside img {
    height: 65%;
    width: 62%;
    position: absolute;
    top: 85px;
  }
}
/* =============================   Tablet and Other Larger Screens =============== */
@media (min-width: 1281px) and (max-width: 1680px) {
  .wrapper {
    padding-left: 3rem;
    padding-right: 3rem;
  }
  .aside {
    flex-basis: 46%;
  }
  .aside img {
    height: 90%;
    width: 80%;
  }
}
</style>