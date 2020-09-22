<template>
  <!-- ========================= Contact Us ============================= -->
  <div id="contactUs" class="wrapper">
    <header>
      <h1 class="contact">Contact Us</h1>
    </header>

    <div class="contact-content-splitter">
      <div class="contact-content">
        <div class="form-wrapper">
          <form action="#" class="form">
            <div class="form-overlay">
              <!-- <img src="./assets/pittsburgh-min.jpg" alt="pittsburgh" class="top"> -->
              <img src="../assets/newyork_sunset-min.jpg" alt="newyork" class="bottom" />
              <div class="input-group">
                <input type="text" name="name" id="name" required autocomplete="off" />
                <label for="name">Name</label>
              </div>

              <div class="input-group">
                <input type="text" name="subject" id="subject" required autocomplete="off" />
                <label for="subject">Subject</label>
              </div>

              <div class="input-group">
                <input type="email" name="email" id="email" required autocomplete="off" />
                <label for="email">Email</label>
              </div>

              <div class="input-group">
                <input
                  type="tel"
                  pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
                  name="phone"
                  id="phone"
                  required
                  autocomplete="off"
                />
                <label for="phone">Phone</label>
              </div>

              <div class="input-group textarea">
                <textarea type="text" name="message" id="message" required autocomplete="off"></textarea>
                <label for="message"></label>
              </div>
            </div>
            <button type="submit" class="submit-btn">Submit</button>
          </form>
        </div>
      </div>

      <div class="contact-icons-container">
        <div class="contact-text">
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
            Praesentium tenetur
            voluptatem veniam corrupti hic ut placeat pariatur. Sint beatae
            officia asperiores
            dignissimos. Odit recusandae ducimus laboriosam animi voluptatem
            omnis ipsam?
          </p>
        </div>
        <div class="contact-me-icons phone-contact-wrapper">
          <a href="tel:+123-456-7890">
            <ion-icon name="call-outline" class="phone"></ion-icon>
          </a>
          <h3>Phone</h3>
          <p class="phone-text">(123) 456-7890</p>
        </div>
        <div class="contact-me-icons email-contact-wrapper">
          <a href="mailto:info@ssslogistics.vip">
            <ion-icon name="mail-outline" class="email"></ion-icon>
          </a>
          <h3>Email</h3>
          <p class="email-text">info@ssslogistics.vip</p>
        </div>

        <div class="contact-me-icons address-contact-wrapper">
          <a href="https://www.google.com/maps/place/Pittsburgh,+PA" target="_blank">
            <ion-icon name="earth-outline" class="address"></ion-icon>
          </a>
          <h3>Address</h3>
          <p class="address-text">Pittsburgh, PA</p>
        </div>
      </div>
    </div>
    <!-- contact-content-splitter ends here -->
  </div>
</template>

<script>
import { gsap } from "gsap";
import * as ScrollMagic from "scrollmagic";

export default {
  name: "Contact",
  methods: {
    scrollContact() {
      var controllerContact = new ScrollMagic.Controller();

      // animate Contact Header
      let animate_contact_h1 = gsap.timeline({
        defaults: { opacity: 0, ease: "linear", autoAlpha: 0 },
      });
      animate_contact_h1.from("header .contact", {
        duration: 1.5,
        scale: 0,
        transformOrigin: "50% 50%",
        stagger: 0.5,
      });
      new ScrollMagic.Scene({
        triggerElement: "header .contact",
        triggerHook: 0.9,
      })
        .setTween(animate_contact_h1)
        .addTo(controllerContact);

      //  Animate Contact Icons
      new ScrollMagic.Scene({
        triggerElement: ".contact-icons-container",
        triggerHook: 0.7,
      })
        .setClassToggle(".contact-icons-container", "fade-in")
        .addTo(controllerContact);

      // Animate Contact Form
      new ScrollMagic.Scene({
        triggerElement: ".contact-content",
        triggerHook: 0.7,
      })
        .setClassToggle(".contact-content", "fade-in")
        .addTo(controllerContact);
    },
  },
  mounted: function () {
    this.scrollContact();
  },
};
</script>

<style scoped>
/* ========================================== Contact Us ============================================ */
#contactUs {
  background-image: linear-gradient(
      -105deg,
      rgba(40, 40, 40, 0.5) 0%,
      rgba(40, 40, 40, 0.9) 50%,
      transparent 50%
    ),
    url("../assets/body.jpg");
  /* height: 90%; */
  height: 90vh;
}
#contactUs header {
  display: flex;
  justify-content: left;
  align-items: center;
  height: 15vh;
  text-shadow: 2px 2px 0px rgba(0, 0, 0, 0.9);
  font-size: 3.2rem;
}
#contactUs header h1 {
  padding: 20px;
  padding-left: 10px;
  font-weight: 600;
  color: #ccc;
  background-color: #565656;
  color: transparent;
  /* text-shadow: 2px 2px 3px rgba(40, 40, 40, 0.5); */
  text-shadow: -2px -2px rgba(0, 0, 0, 0.2);
  opacity: 0.7;
  -webkit-text-fill-color: transparent;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  background-clip: text;
  filter: drop-shadow(3px 2px 0px rgba(0, 0, 0, 0.9));
}

.contact-content-splitter {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.contact-content {
  width: 40%;
  order: 2;
  opacity: 0;
  transform: translateX(100px);
  transition: all 1s ease-out;
}
.contact-content.fade-in {
  opacity: 1;
  transform: translateX(0);
}
.contact-icons-container {
  width: 60%;
  order: 1;
}
.contact-text {
  width: 100%;
  letter-spacing: 1px;
  line-height: 1.8rem;
  position: relative;
}
.contact-text p {
  position: absolute;
  width: 100%;
  top: -250px;
}
.contact-content .form-wrapper {
  height: 75%;
  width: 100%;
  display: flex;
  justify-content: flex-end;
  align-content: center;
}
.contact-content .form {
  position: relative;
  width: 100%;
  /* max-width: 40%; */
  padding: 60px 40px;
  box-shadow: 0 15px 25px rgba(0, 0, 0, 0.5);
}
.contact-content .form:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(
      130deg,
      rgba(40, 40, 40, 0.8) 0%,
      rgba(40, 40, 40, 0.8) 52%,
      transparent 50%
    ),
    url("../assets/pittsburgh-min.jpg");
  background-size: cover;
  opacity: 0.5;
  border-radius: 10px;
  pointer-events: none;
}
.contact-content .form img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  pointer-events: none;
}
.contact-content .form img.bottom {
  border-radius: 10px;
  animation-name: cf3FadeInOut;
  animation-timing-function: ease-in-out;
  animation-iteration-count: infinite;
  animation-duration: 7s;
  animation-direction: alternate;
}
@keyframes cf3FadeInOut {
  0% {
    opacity: 0.5;
  }
  45% {
    opacity: 0.5;
  }
  55% {
    opacity: 0;
  }
  100% {
    opacity: 0;
  }
}
.contact-content .form .input-group {
  position: relative;
}
.contact-content .form .input-group input {
  width: 50%;
  padding: 15px 0;
  letter-spacing: 1px;
  margin-bottom: 30px;
  outline: none;
  border: none;
  border-bottom: 1px solid #fff;
  background-color: transparent;
  color: inherit;
  position: relative;
}
.contact-content .form .input-group textarea {
  resize: vertical;
  width: 100%;
  height: 10rem;
  background-color: transparent;
  outline: none;
  border-radius: 5px;
  border: 1px solid #fff;
  color: inherit;
  font-size: 1.2rem;
  font-weight: 400;
  letter-spacing: 1px;
  padding: 20px;
  resize: none;
}

.contact-content .form .input-group label {
  position: absolute;
  top: 0;
  left: 0;
  padding: 5px 0;
  font-size: 1.2rem;
  font-weight: 400;
  letter-spacing: 1px;
  transition: 0.3s ease-out;
}
.contact-content .form .input-group input:focus + label,
.contact-content .form .input-group input:valid + label {
  transform: translateY(-18px);
  color: bisque;
  font-size: 1rem;
  font-weight: 400;
}
.submit-btn {
  margin-top: 2rem;
  margin-left: auto;
  border: none;
  outline: none;
  font-size: 1.2rem;
  font-family: "Syne", sans-serif;
  font-weight: 400;
  padding: 0.8rem 1rem;
  color: black;
  background-color: white;
  border: 1px solid black;
  /* background: rgba(40, 40, 40, 1); */
  float: right;
  border-radius: 5px;
  cursor: pointer;
}

.submit-btn:hover {
  /* background: rgba(255, 255, 255, 0.7); */
  border: 1px solid white;
  color: white;
  background-color: black;
  transition: all 0.5s ease-in;
  -webkit-transition: all 0.5s ease-in;
}

/* ================= Contact Us Icons ==================== */
.contact-icons-container {
  padding-left: 20px;
  display: flex;
  flex-flow: row wrap;
  width: 50%;
  justify-content: space-between;
  align-items: center;
  opacity: 0;
  transform: translateX(-100px);
  transition: all 1s ease-out;
}
.contact-icons-container.fade-in {
  opacity: 1;
  transform: translateX(0);
}
.contact-me-icons {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
}
.contact-me-icons ion-icon {
  font-size: 5rem;
  color: rgba(255, 255, 255, 0.7);
  font-weight: 400;
  text-shadow: rgba(0, 0, 0, 0.5) 4px 4px 0px;
}

.contact-me-icons h3 {
  font-size: 2rem;
  font-family: "Syne", sans-serif;
  font-weight: 400;
  padding: 10px 0;
  text-shadow: rgba(0, 0, 0, 0.5) 2px 2px 0px;
  color: bisque;
}
.contact-me-icons p {
  line-height: 1.8rem;
  font-size: 1.5rem;
  font-family: "Syne", sans-serif;
  font-weight: 400;
  text-shadow: rgba(0, 0, 0, 0.5) 2px 2px 0px;
  letter-spacing: 1px;
}
.contact-me-icons .phone-text {
  font-family: sans-serif;
  letter-spacing: 0;
}
.contact-me-icons .phone:hover {
  color: bisque;
  transition: all 0.5s ease-in-out;
}
.contact-me-icons .email:hover {
  color: lightgreen;
  transition: all 0.5s ease-in-out;
}
.contact-me-icons .address:hover {
  color: lightblue;
  transition: all 0.5s ease-in-out;
}

/* =========================================== Small Smartphones =================================  */
/* ============================================ Contact Us ====================================== */

@media (max-width: 499px) {
  #contactUs {
    height: initial;
    padding-bottom: 2rem;
  }
  #contactUs header {
    height: auto;
    font-size: 2rem;
  }
  #contactUs header h1 {
    padding-left: 0;
  }
  .contact-text p {
    position: static;
    top: auto;
    color: rgba(255, 255, 255, 0.6);
  }
  .contact-content-splitter {
    flex-direction: column;
    justify-content: center;
  }
  .contact-content {
    width: 100%;
  }
  .contact-content .form-wrapper {
    height: initial;
  }
  .contact-content .form {
    padding: 35px 20px;
    color: rgba(255, 255, 255, 0.6);
  }
  .contact-content .form:before {
    border-radius: 5px;
  }
  .contact-content .form img.bottom {
    border-radius: 5px;
  }
  .contact-content .form .input-group input {
    border-bottom: 1px solid rgba(255, 255, 255, 0.6);
  }
  .contact-content .form .input-group label {
    font-size: 1rem;
  }
  .contact-icons-container {
    width: 100%;
    padding-left: 0;
    flex-direction: column;
    color: rgba(255, 255, 255, 0.6);
  }
  .contact-me-icons {
    padding-bottom: 2rem;
  }
  .phone-contact-wrapper {
    padding-top: 2rem;
  }
  .contact-me-icons ion-icon {
    font-size: 3rem;
  }
  .contact-me-icons h3 {
    font-size: 1.8rem;
  }
  .contact-me-icons p {
    font-size: 1.5rem;
    font-weight: lighter;
  }
}

/* ===========================================  Small Smartphones Landscape =================================  */
@media (min-width: 500px) and (max-width: 736px) {
  #contactUs {
    height: initial;
    padding-bottom: 2rem;
  }
  #contactUs header {
    height: auto;
    font-size: 2rem;
  }
  #contactUs header h1 {
    padding-left: 0;
  }
  .contact-text p {
    position: static;
    top: auto;
    color: rgba(255, 255, 255, 0.6);
  }
  .contact-content-splitter {
    flex-direction: column;
    justify-content: center;
  }
  .contact-content {
    width: 100%;
  }
  .contact-content .form-wrapper {
    height: initial;
  }
  .contact-content .form {
    padding: 35px 20px;
    color: rgba(255, 255, 255, 0.6);
  }
  .contact-content .form:before {
    border-radius: 5px;
  }
  .contact-content .form img.bottom {
    border-radius: 5px;
  }
  .contact-content .form .input-group input {
    border-bottom: 1px solid rgba(255, 255, 255, 0.6);
  }
  .contact-content .form .input-group label {
    font-size: 1rem;
  }
  .contact-icons-container {
    width: 100%;
    padding-left: 0;
    flex-direction: column;
    color: rgba(255, 255, 255, 0.6);
  }
  .contact-me-icons {
    padding-bottom: 2rem;
  }
  .phone-contact-wrapper {
    padding-top: 2rem;
  }
  .contact-me-icons ion-icon {
    font-size: 3rem;
  }
  .contact-me-icons h3 {
    font-size: 1.8rem;
  }
  .contact-me-icons p {
    font-size: 1.5rem;
    font-weight: lighter;
  }
}
/* ===========================================  Tablets ==============================  */
@media (min-width: 737px) and (max-width: 980px) {
  html,
  body {
    overflow-x: hidden !important;
  }
  #contactUs {
    height: initial;
    padding-bottom: 35px;
  }
  #contactUs header {
    height: auto;
    font-size: 2.8rem;
  }
  #contactUs header h1 {
    padding-left: 0;
  }
  .contact-text p {
    font-size: 1.3rem;
    position: static;
    top: auto;
    color: rgba(255, 255, 255, 0.6);
  }
  .contact-content-splitter {
    flex-direction: column;
    justify-content: center;
  }
  .contact-content {
    width: 100%;
  }
  .contact-content .form-wrapper {
    height: initial;
  }
  .contact-content .form {
    padding: 35px 20px;
    color: rgba(255, 255, 255, 0.6);
  }
  .contact-content .form:before {
    border-radius: 5px;
  }
  .contact-content .form img.bottom {
    border-radius: 5px;
  }
  .contact-content .form .input-group input {
    border-bottom: 1px solid rgba(255, 255, 255, 0.6);
  }
  .contact-content .form .input-group label {
    font-size: 1.2rem;
  }
  .contact-icons-container {
    width: 100%;
    padding-left: 0;
    flex-direction: column;
    color: rgba(255, 255, 255, 0.6);
  }
  .contact-me-icons {
    padding-bottom: 2rem;
  }
  .phone-contact-wrapper {
    padding-top: 2rem;
  }
  .contact-me-icons ion-icon {
    font-size: 3.5rem;
  }
  .contact-me-icons h3 {
    font-size: 1.9rem;
  }
  .contact-me-icons p {
    font-size: 1.5rem;
    font-weight: lighter;
  }
}
/* ===========================================  Tablets  Larger Screen  | iPad Landscape Mode as well ==============================  */
@media (min-width: 981px) and (max-width: 1280px) {
  .wrapper {
    padding-left: 2rem;
    padding-right: 2rem;
  }
  #contactUs {
    height: initial;
    padding-bottom: 35px;
  }
  #contactUs header {
    height: auto;
    font-size: 2.8rem;
  }
  #contactUs header h1 {
    padding-left: 0;
  }
  .contact-text p {
    font-size: 1.1rem;
    top: -50px;
    color: rgba(255, 255, 255, 0.6);
    left: 0px;
  }
  /* form itself*/
  .contact-content {
    width: 50%;
  }
  .contact-text {
    width: 97%;
  }

  .contact-icons-container {
    display: flex;
    /* flex-direction: column; */
    flex-direction: row;
    padding-left: 0;
    height: 55vh;
    justify-content: space-evenly;
    margin-top: auto;
  }
  .contact-me-icons {
    padding-top: 2rem;
  }
  .phone-contact-wrapper {
    order: 1;
  }
  .email-contact-wrapper {
    order: 3;
  }
  .address-contact-wrapper {
    order: 2;
  }
}
/* **************************************************************************************** */
@media (min-width: 981px) and (max-width: 1280px) and (orientation: landscape) {
  .contact-text p {
    top: -260px;
  }
}
/* =============================   Tablet and Other Larger Screens =============== */
@media (min-width: 1281px) and (max-width: 1680px) {
  .wrapper {
    padding-left: 3rem;
    padding-right: 3rem;
  }
}
</style>