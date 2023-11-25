<template>
  <div class="container" id="contact">
    <h1 style="color: #00f">Profile Card</h1>
    <div
      class="row"
      @mousemove="MouseMove"
      @mouseleave="MouseLeave"
      @mouseenter="MouseEnter"
    >
      <div class="container1">
        <div class="cont" :class="{ Turn: btnShow }">
          <div class="card">
            <div class="leftTag" :class="{ sideExpand: side }">
              <div class="Box">
                <p>
                  One machine can do the work of fifty ordinary men. No machine
                  can do the work of one extraordinary man.
                </p>
                <LeftSlide :Leftshot="side" />

                <button @click="side = !side">Interst Roll</button>
                <div class="cirall">
                  <div class="cir"></div>
                  <div class="cir"></div>
                  <div class="cir"></div>
                </div>
              </div>
            </div>
            <aside class="profile-card">
              <header>
                <a target="_blank" href="#">
                  <img
                    src="../assets/Image/Mon1.jpg"
                    class="hoverZoomLink"
                    width="300"
                    height="100"
                  />
                </a>
                <h1>Vijay kumar</h1>
                <h2>
                  Fullstack & Software <br />
                  developer
                </h2>
              </header>
              <div class="profile-bio">
                <p>
                  The more seriously you take your growth, the more seriously
                  your people will take you.
                </p>
              </div>
              <button
                class="btn btn-success mainbtn"
                @click="btnShow = !btnShow"
              >
                View Profile
              </button>
            </aside>
            <div class="rightTag" :class="{ sideExpand: side1 }">
              <div class="Box">
                <p>
                  In order to build a rewarding employee experience, you need to
                  understand what matters most to your people.
                </p>
                <RightSlide :rshow="side1" />
                <button @click="side1 = !side1">Specific Roll</button>
                <div class="cirall">
                  <div class="cir"></div>
                  <div class="cir"></div>
                  <div class="cir"></div>
                </div>
              </div>
            </div>
          </div>
          <div class="card_back">
            <BioCard @changeBack="changeB($event)" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BioCard from "./BioCard.vue";
import RightSlide from "./Skill/RightTag.vue";
import LeftSlide from "./Skill/LeftTag.vue";
export default {
  name: "DesignCardBio",
  components: {
    BioCard,
    RightSlide,
    LeftSlide,
  },
  data() {
    return {
      btnShow: false,
      side: false,
      side1: false,
    };
  },
  methods: {
    changeB(change) {
      this.btnShow = change;
    },
    MouseMove(e) {
      let card = document.querySelector(".container1");
      let horizontal = (e.clientX / window.innerWidth - 0.5) * 30;
      let vertical = (e.clientY / window.innerHeight - 0.5) * 30;
      card.style.cursor = "pointer";
      console.log(horizontal, vertical);
      card.style.transform = `rotateX(${horizontal}deg) rotateY(${vertical}deg)`;
      card.style.transition = ".2s";
    },
    MouseLeave() {
      let card = document.querySelector(".container1");
      card.style.transform = "rotateX(0deg) rotateY(0deg)";
    },
    MouseEnter() {
      let box = document.querySelector(".cont");
      box.style.transition = ".1s";
    },
  },
};
</script>
<style scoped>
* {
  perspective: 1000px;
}
.row {
  width: 100%;
  max-height: 70%;
  height: 600px;
  perspective: 1000px;
  margin: 15rem 0;
}
.container1 {
  background-color: transparent;
  width: 100%;
  height: 600px;
  perspective: 1000px;
}
.cont {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(210, 185, 185, 0.2);
  background: #000;
}
.Turn {
  transform: rotateY(180deg);
}

.card,
.card_back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  -webkit-backface-visibility: hidden;
  overflow: hidden;
  transform: transform 0.5s;
}

.card_back {
  color: white;
  transform: rotateY(-180deg);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: -2;
  background: transparent;
  width: 100%;
  height: 100%;
}

.card {
  min-height: 70vh;
  width: 100%;
  border-radius: 30px;
  box-shadow: 5px 5px 6px rgba(0, 0, 0, 0.5), -5px -5px 6px rgba(0, 0, 0, 0.5);
  flex-wrap: wrap;
  background: #000;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0px;
  margin: 0px;
  overflow: hidden;
  position: fixed;
}

.card:before {
  content: "";
  height: 0px;
  padding: 0px;
  border: 130em solid #090a0f;
  position: absolute;
  left: 50%;
  top: 100%;
  z-index: 2;
  display: block;
  -webkit-border-radius: 50%;
  border-radius: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  -webkit-animation: puff 0.5s 1.8s cubic-bezier(0.55, 0.055, 0.675, 0.19)
      forwards,
    borderRadius 0.2s 2.3s linear forwards;
  animation: puff 0.5s 1.8s cubic-bezier(0.55, 0.055, 0.675, 0.19) forwards,
    borderRadius 0.2s 2.3s linear forwards;
}

.card_back:before {
  content: "";
  height: 0px;
  padding: 0px;
  /* border: 130em solid #021973; */
  position: absolute;
  left: 50%;
  top: 100%;
  z-index: -12;
  display: block;
  -webkit-border-radius: 50%;
  border-radius: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  -webkit-animation: puff 0.5s 1.8s cubic-bezier(0.55, 0.055, 0.675, 0.19)
      forwards,
    borderRadius 0.2s 2.3s linear forwards;
  animation: puff 0.5s 1.8s cubic-bezier(0.55, 0.055, 0.675, 0.19) forwards,
    borderRadius 0.2s 2.3s linear forwards;
}
h1,
h2 {
  font-weight: 500;
  margin: 0px 0px 5px 0px;
}

h1 {
  font-size: 24px;
}

h2 {
  font-size: 16px;
}

p {
  margin: 0px;
}

.profile-card {
  background: #ffb300;
  width: 56px;
  height: 56px;
  position: absolute;
  left: 50%;
  top: 0;
  z-index: 2;
  overflow: hidden;
  opacity: 0;
  margin-top: 70px;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  -webkit-border-radius: 50%;
  border-radius: 50%;
  -webkit-box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.16),
    0px 3px 6px rgba(0, 0, 0, 0.23);
  box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.16), 0px 3px 6px rgba(0, 0, 0, 0.23);
  -webkit-animation: init 0.5s 0.2s cubic-bezier(0.55, 0.055, 0.675, 0.19)
      forwards,
    moveDown 1s 0.8s cubic-bezier(0.6, -0.28, 0.735, 0.045) forwards,
    moveUp 1s 1.8s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards,
    materia 0.5s 2.7s cubic-bezier(0.86, 0, 0.07, 1) forwards;
  animation: init 0.5s 0.2s cubic-bezier(0.55, 0.055, 0.675, 0.19) forwards,
    moveDown 1s 0.8s cubic-bezier(0.6, -0.28, 0.735, 0.045) forwards,
    moveUp 1s 1.8s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards,
    materia 0.5s 2.7s cubic-bezier(0.86, 0, 0.07, 1) forwards;
}

.profile-card header {
  width: 100%;
  height: 280px;
  padding: 40px 20px 30px 20px;
  display: inline-block;
  float: left;
  border-right: 2px dashed #eeeeee;
  background: #ffffff;
  color: #000000;
  margin-top: 50px;
  opacity: 0;
  text-align: center;
  -webkit-animation: moveIn 1s 3.1s ease forwards;
  animation: moveIn 1s 3.1s ease forwards;
}

.profile-card header h1 {
  color: #ff5722;
}

.profile-card header a {
  display: inline-block;
  text-align: center;
  position: relative;
  margin: 25px 30px;
}

.profile-card header a:after {
  position: absolute;
  content: "";
  bottom: 3px;
  right: 3px;
  width: 20px;
  height: 20px;
  border: 4px solid #ffffff;
  -webkit-transform: scale(0);
  transform: scale(0);
  background: -webkit-linear-gradient(
    top,
    #2196f3 0%,
    #2196f3 50%,
    #ffc107 50%,
    #ffc107 100%
  );
  background: linear-gradient(
    #2196f3 0%,
    #2196f3 50%,
    #ffc107 50%,
    #ffc107 100%
  );
  -webkit-border-radius: 50%;
  border-radius: 50%;
  -webkit-box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.1);
  box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.1);
  -webkit-animation: scaleIn 0.3s 3.5s ease forwards;
  animation: scaleIn 0.3s 3.5s ease forwards;
}

.profile-card header a > img {
  width: 50%;
  max-width: 100%;
  -webkit-border-radius: 50%;
  border-radius: 50%;
  -webkit-transition: -webkit-box-shadow 0.3s ease;
  transition: box-shadow 0.3s ease;
  -webkit-box-shadow: 0px 0px 0px 8px rgba(0, 0, 0, 0.06);
  box-shadow: 0px 0px 0px 8px rgba(0, 0, 0, 0.06);
}

.profile-card header a:hover > img {
  -webkit-box-shadow: 0px 0px 0px 12px rgba(0, 0, 0, 0.1);
  box-shadow: 0px 0px 0px 12px rgba(0, 0, 0, 0.1);
}

.profile-card .profile-bio {
  width: 175px;
  height: 180px;
  display: inline-block;
  float: right;
  padding: 50px 20px 30px 20px;
  background: #fff;
  color: #333333;
  margin-top: 50px;
  text-align: center;
  opacity: 0;
  -webkit-animation: moveIn 1s 3.1s ease forwards;
  animation: moveIn 1s 3.1s ease forwards;
}

@keyframes init {
  0% {
    width: 0px;
    height: 0px;
  }
  100% {
    width: 56px;
    height: 56px;
    margin-top: 0px;
    opacity: 1;
  }
}

@keyframes puff {
  0% {
    top: 100%;
    height: 0px;
    padding: 0px;
  }
  100% {
    top: 50%;
    height: 100%;
    padding: 0px 100%;
  }
}

@keyframes borderRadius {
  0% {
    -webkit-border-radius: 50%;
  }
  100% {
    border-radius: 0px;
  }
}

@keyframes moveDown {
  0% {
    top: 50%;
  }
  50% {
    top: 40%;
  }
  100% {
    top: 100%;
  }
}

@keyframes moveUp {
  0% {
    background: #ffb300;
    top: 100%;
  }
  50% {
    top: 40%;
  }
  100% {
    top: 50%;
    background: #e0e0e0;
  }
}

@-webkit-keyframes materia {
  0% {
    background: #e0e0e0;
  }
  50% {
    -webkit-border-radius: 4px;
  }
  100% {
    width: 440px;
    height: 280px;
    background: #ffffff;
    -webkit-border-radius: 4px;
  }
}

@keyframes materia {
  0% {
    background: #e0e0e0;
  }
  50% {
    border-radius: 4px;
  }
  100% {
    width: 440px;
    height: 280px;
    background: #ffffff;
    border-radius: 4px;
  }
}

@-webkit-keyframes moveIn {
  0% {
    margin-top: 50px;
    opacity: 0;
  }
  100% {
    opacity: 1;
    margin-top: -20px;
  }
}

@keyframes moveIn {
  0% {
    margin-top: 80px;
    opacity: 0;
  }
  100% {
    opacity: 1;
    margin-top: -20px;
  }
}

@-webkit-keyframes scaleIn {
  0% {
    -webkit-transform: scale(0);
  }
  100% {
    -webkit-transform: scale(1);
  }
}

@keyframes scaleIn {
  0% {
    transform: scale(0);
  }
  100% {
    transform: scale(1);
  }
}

@-webkit-keyframes ripple {
  0% {
    transform: scale3d(0, 0, 0);
  }
  50%,
  100% {
    -webkit-transform: scale3d(1, 1, 1);
  }
  100% {
    opacity: 0;
  }
}

@keyframes ripple {
  0% {
    transform: scale3d(0, 0, 0);
  }
  50%,
  100% {
    transform: scale3d(1, 1, 1);
  }
  100% {
    opacity: 0;
  }
}

@media screen and (min-aspect-ratio: 4/3) {
  body {
    background-size: cover;
  }
  body:before {
    width: 0px;
  }

  @keyframes puff {
    0% {
      top: 100%;
      width: 0px;
      padding-bottom: 0px;
    }
    100% {
      top: 50%;
      width: 100%;
      padding-bottom: 100%;
    }
  }
}

@media screen and (min-height: 480px) {
  .profile-card header {
    width: auto;
    height: auto;
    padding: 30px 20px;
    display: block;
    float: none;
    border-right: none;
  }
  .profile-card .profile-bio {
    width: auto;
    height: auto;
    padding: 15px 20px 30px 20px;
    display: block;
    float: none;
  }
  .profile-social-links {
    width: 100%;
    display: block;
    float: none;
  }

  @keyframes materia {
    0% {
      background: #e0e0e0;
    }
    50% {
      border-radius: 4px;
    }
    100% {
      width: 280px;
      height: 440px;
      background: #ffffff;
      border-radius: 4px;
    }
  }
}
.leftTag {
  position: absolute;
  width: 30%;
  height: 90%;
  left: 2%;
  margin: auto;
  top: auto;
  background: #000;
  z-index: 10;
  transition: 0.5s;
  opacity: 1;
}
.rightTag {
  position: absolute;
  width: 30%;
  height: 90%;
  background: #000;
  right: 5%;
  z-index: 10;
  top: auto;
  transition: 0.5s;
  opacity: 1;
}
.sideExpand {
  width: 100%;
  height: 100%;
  z-index: 44;
  top: 0;
  left: 0;
  transition: 0.5s ease;
}

.Box {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  color: #fff;
  width: 100%;
  height: 100%;
}
p {
  text-align: center;
}
button {
  padding: 10px 30px;
  background: #ff5722;
  color: #fff;
  margin: 1rem 0;
  border-radius: 10px;
  font-size: 1.2rem;
  border: none;
  outline: none;
}
.cirall {
  display: flex;
}
.cirall > .cir {
  width: 13px;
  height: 13px;
  background: #2196f3;
  margin: 10px;
  border-radius: 50%;
}
.cirall .cir:hover {
  position: absolute;
  top: 0;
  left: 0;
  background-color: #ffb300;
  width: 100%;
  height: 100%;
  border-radius: 5%;
  clip-path: circle(70.7% at 50% 50%);
  z-index: 2;
}
.mainbtn {
  position: absolute;
  bottom: 1.5px;
  left: 20%;
  background: #00f;
  -webkit-animation: moveIn 1s 3.1s ease forwards;
  animation: moveIn 1s 3.1s ease forwards;
}
@media screen and (max-width: 700px) {
  .leftTag,
  .rightTag {
    opacity: 0;
    background: #ff5722;
  }
}
</style>
