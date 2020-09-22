<template>
  <!-- =============================Footer ========================= -->
  <footer class="footer wrapper">
    <div class="footer-info">
      <p>Copyright © 2020. All Rights Reserved</p>
      <div class="social">
        <a href="#">
          <ion-icon name="logo-facebook" class="facebook"></ion-icon>
        </a>
        <a href="#">
          <ion-icon name="logo-google" class="google"></ion-icon>
        </a>
        <a href="#">
          <ion-icon name="logo-instagram" class="instagram"></ion-icon>
        </a>
      </div>
    </div>
    <div class="coded-dev">
      <p>Hard Coded by</p>
      <a href="https://github.com/Durdona" target="_blank">
        <ion-icon name="logo-github" class="github"></ion-icon>
      </a>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
  methods: {},
};
</script>

<style scoped>
/* ============================================= Footer Page =================================== */
.footer {
  height: 15vh;
  background-image: linear-gradient(
      190deg,
      rgba(40, 40, 40, 0.9) 0%,
      rgba(40, 40, 40, 0.9) 50%,
      transparent 50%
    ),
    url("../assets/body.jpg");
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.footer-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-flow: row wrap;
  height: 100%;
  letter-spacing: 1px;
  font-weight: lighter;
  padding-left: 10px;
}
.footer-info .social {
  margin-left: 20px;
}
.coded-dev {
  display: flex;
  justify-content: center;
  align-items: center;
  color: rgba(255, 255, 255, 0.3);
}
.coded-dev .github {
  font-size: 1.5rem;
  margin-left: 10px;
  color: rgba(255, 255, 255, 0.3);
}
.coded-dev .github:hover {
  color: lightgreen;
}
/* ====================================================================== */
.social-container {
  position: absolute;
  bottom: 2rem;
  right: 2rem;
}
.social {
  display: flex;
}
.social ion-icon {
  margin-right: 1rem;
  font-weight: 700;
  font-size: 1.4rem;
  font-family: sans-serif;
  font-weight: 400;
  color: lightgrey;
  /* color: bisque; */
}
.social ion-icon.instagram {
  margin-right: 0;
}
.facebook {
  border-radius: 30%;
}
.facebook:hover {
  color: #4267b2;
  transition: all 0.5s ease-in;
  -webkit-transition: all 0.5s ease-in;
}
.google:hover {
  color: #3cba54;
  transition: all 0.5s ease-in;
  -webkit-transition: all 0.5s ease-in;
}
.instagram:hover {
  color: #bc2a8d;
  transition: all 0.5s ease-in;
  -webkit-transition: all 0.5s ease-in;
}

/* =========================================== Small Smartphones =================================  */
/*  ======================================= Footer =========================================== */

@media (max-width: 499px) {
  .footer {
    height: initial;
    flex-direction: column;
    padding: 1.5rem;
    align-items: flex-start;
    font-family: sans-serif;
    font-weight: lighter;
    color: rgba(255, 255, 255, 0.6);
  }
  .footer-info {
    padding-left: 0;
    padding-bottom: 0.5rem;
  }

  .coded-dev .github {
    font-size: 1.4rem;
    margin-left: 5px;
  }
  .social {
    display: none;
  }
}

/* ===========================================  Small Smartphones Landscape =================================  */
@media (min-width: 500px) and (max-width: 736px) {
  .footer {
    color: rgba(255, 255, 255, 0.6);
  }
  .footer-info {
    display: flex;
    justify-content: space-evenly;
    align-items: flex-start;
    flex-flow: row wrap;
    height: 100%;
    letter-spacing: 1px;
    font-weight: lighter;
    padding-left: 10px;
    flex-direction: column;
  }
  .footer-info .social {
    margin-left: 0;
    padding-top: ;
  }
  .coded-dev {
    width: 40%;
  }
  .social {
    display: none;
  }
}
</style>