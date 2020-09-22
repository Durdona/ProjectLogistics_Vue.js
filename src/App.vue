<template>
  <div id="app">
    <Home />
    <ChooseUs />
    <Drivers />
    <Contact />
    <Footer />
  </div>
</template>

<script>
import Home from "./components/Home";
import ChooseUs from "./components/ChooseUs";
import Drivers from "./components/Drivers";
import Contact from "./components/Contact";
import Footer from "./components/Footer";

export default {
  name: "App",
  components: {
    Home,
    ChooseUs,
    Drivers,
    Contact,
    Footer,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Syne:wght@400;500&display=swap");

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body,
#app {
  overflow-x: hidden;
}
.logo-hidden-desktop,
.info-hidden {
  display: none;
}
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  font-family: "Syne", sans-serif;
  color: white;
  font-weight: 400;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.wrapper {
  width: 100%;
  height: 100vh;
  padding-left: 10%;
  padding-right: 10%;
  /* border-top: 1px dotted rgba(40, 40, 40, 0.9); */
  border-top: 1px dotted gray;
}
@media (min-width: 1681px) {
  body {
    font-size: 1.1rem;
    font-weight: 400;
  }
}
</style>
