<template>
  <div class="row" id="home">
    <div class="col-lg-5 col-md-5 order-lg-1 order-md-1 col-12 order-2 left">
      <div class="cover justify-content-md-center">
        <h1>Think Less,<br />Create More</h1>
        <h3>Hi,There I'm Vijay</h3>
        <h6>
          Hi,I'm Fullstack developer & UI Designer Creating bold & brave <br />
          interface design of companies all across the world
        </h6>
        <div class="social-media">
          <i class="fa fa-instagram"></i>
          <i class="fa fa-facebook"></i>
          <i class="fa fa-twitter"></i>
          <i class="fa fa-github"></i>
          <i class="fa fa-whatsapp"></i>
          <i class="fa fa-linkedin"></i>
        </div>
        <a href="#"    @click="Profile" >Let's Talk</a>
      </div>
    </div>
    <div
      class="col-lg-5 col-md-5 col-12 order-1 order-lg-2 order-md-2 m"
      style="position: relative"
    >
      <div
        class="right circle"
        data-aos="flip-right"
        data-aos-easing="linear"
        data-aos-duration="1800"
      >
        <div class="logo">
          <div class="text">
            <p ref="textAni">
             <span style="transform:rotate(0deg)"> </span>
             <span style="transform:rotate(6.2deg)">-</span>
             <span style="transform:rotate(12.4deg)">-</span>
             <span style="transform:rotate(18.6deg)">V</span>
             <span style="transform:rotate(24.8deg)">i</span>
             <span style="transform:rotate(31deg)">j</span>
             <span style="transform:rotate(37.2deg)">a</span>
             <span style="transform:rotate(43.4deg)">y</span>
             <span style="transform:rotate(49.6deg)"> </span>
             <span style="transform:rotate(55.800000000000004deg)">k</span>
             <span style="transform:rotate(62deg)">u</span>
             <span style="transform:rotate(68.2deg)">m</span>
             <span style="transform:rotate(74.4deg)">a</span>
             <span style="transform:rotate(80.60000000000001deg)">r</span>
             <span style="transform:rotate(86.8deg)">-</span>
             <span style="transform:rotate(93deg)">F</span>
             <span style="transform:rotate(99.2deg)">u</span>
             <span style="transform:rotate(105.4deg)">l</span>
             <span style="transform:rotate(111.60000000000001deg)">l</span>
             <span style="transform:rotate(117.8deg)">s</span>
             <span style="transform:rotate(124deg)">t</span>
             <span style="transform:rotate(130.20000000000002deg)">a</span>
             <span style="transform:rotate(136.4deg)">c</span>
             <span style="transform:rotate(142.6deg)">k</span>
             <span style="transform:rotate(148.8deg)"> </span>
             <span style="transform:rotate(155deg)">&amp;</span>
             <span style="transform:rotate(161.20000000000002deg)"> </span>
             <span style="transform:rotate(167.4deg)">M</span>
             <span style="transform:rotate(173.6deg)">L</span>
             <span style="transform:rotate(179.8deg)"> </span>
             <span style="transform:rotate(186deg)">d</span>
             <span style="transform:rotate(192.20000000000002deg)">e</span>
             <span style="transform:rotate(198.4deg)">v</span>
             <span style="transform:rotate(204.6deg)">e</span>
             <span style="transform:rotate(210.8deg)">l</span>
             <span style="transform:rotate(217deg)">o</span>
             <span style="transform:rotate(223.20000000000002deg)">p</span>
             <span style="transform:rotate(229.4deg)">e</span>
             <span style="transform:rotate(235.6deg)">r</span>
             <span style="transform:rotate(241.8deg)"> </span>
             <span style="transform:rotate(248deg)">a</span>
             <span style="transform:rotate(254.20000000000002deg)">n</span>
             <span style="transform:rotate(260.40000000000003deg)">d</span>
             <span style="transform:rotate(266.6deg)"> </span>
             <span style="transform:rotate(272.8deg)">C</span>
             <span style="transform:rotate(279deg)">r</span>
             <span style="transform:rotate(285.2deg)">e</span>
             <span style="transform:rotate(291.40000000000003deg)">a</span>
             <span style="transform:rotate(297.6deg)">t</span>
             <span style="transform:rotate(303.8deg)">i</span>
             <span style="transform:rotate(310deg)">v</span>
             <span style="transform:rotate(316.2deg)">e</span>
             <span style="transform:rotate(322.40000000000003deg)"> </span>
             <span style="transform:rotate(328.6deg)">T</span>
             <span style="transform:rotate(334.8deg)">h</span>
             <span style="transform:rotate(341deg)">i</span>
             <span style="transform:rotate(347.2deg)">n</span>
             <span style="transform:rotate(353.40000000000003deg)">k</span>
             <span style="transform:rotate(359.6deg)">i</span>
             <span style="transform:rotate(365.8deg)">n</span>
             <span style="transform:rotate(372deg)">g</span>
             <span style="transform:rotate(378.2deg)">-</span>
             <span style="transform:rotate(384.40000000000003deg)">-</span>
             <span style="transform:rotate(390.6deg)"> </span>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Header",
};
</script>

<style scoped>
h3{
  font-family:'Amita';
  color: aliceblue;
}
.right {
  font-family: Consolas;
  position: relative;
  border-radius: 50%;
  width: 600px;
  height: 600px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.logo {
  position: absolute;
  width: 480px;
  height: 480px;
  background: url("../assets/Image/tech1.png");
  background-position: center;
  background-size: cover;
  border-radius: 50%;
  filter: brightness(1.5) contrast(1);
}
.text {
  position: absolute;
  width: 100%;
  height: 100%;
  animation: ani 19s linear infinite;
}
@keyframes ani {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
.text span {
  position: absolute;
  left: 50%;
  top: -8%;
  font-size: 1.5em;
  transform-origin: 0 280px;
  font-weight: 800;
  color: cyan;
  padding: 2px;
  filter: blur(1px);
  border-top: 2px solid #fff;
  border-bottom: 2px solid #fff;
}
.text span:hover {
  color: #fff;
  background: transparent;
}

h1 {
  font-family: "Poppins", sans-serif;
  font-size: 4rem;
  font-weight: 900;
  text-align: left;
  color: #fff;
}
h6 {
  text-align: left;
}
img {
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
}
.left .cover {
  position: relative;
  width: 100%;
}

a {
  background: blue;
  text-decoration: none;
  padding: 10px 14px;
  border-radius: 20px;
  border: none;
  outline: none;
  color: #fff;
  letter-spacing: 0.1em;
}

.row {
  width:100%;
  height: 600px;
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  position: relative;
  margin-bottom: 5rem;
}
.left {
  width: 60%;
  height: 100%;
  text-align: left;
  padding-left: 4rem;
  display: flex;
  justify-content: center;
  align-items: center;
}
.m {
  width: 40%;
  height: 60%;
  margin: 5rem 0rem;
  display: flex;
  justify-content: center;
  align-items: center;
  transform: translateY(15px);
  border-radius: 52% 48% 20% 80% / 39% 42% 58% 61%;
  opacity: 0.8;
  transform: translateZ(50%, -50%);
}

img {
  position: absolute;
  border-radius: 50%;
  top: -12px;
  opacity: 0.6;
}

@media screen and (max-width: 990px) {
  .logo {
    width: 300px;
    height: 300px;
  }
  .social-media {
    justify-content: center;
  }
  .text span {
    position: absolute;
    left: 50%;
    top: -10%;
    font-size: 1.5em;
    transform-origin: 0 180px;
  }
  .left {
    text-align: center;
    width: 100%;
    display: -ms-grid;
    place-items: center;
  }
  .m {
    display: -ms-grid;
    place-items: center;
  }
  .row {
    margin-top:5rem;
    margin-bottom: 30rem;
  }
  h1,
  h6 {
    text-align: center;
    padding: 10px;
  }
}

.social-media {
  display: flex;
  margin-bottom: 2rem;
}
.social-media i {
  cursor: pointer;
  height: 40px;
  width: 40px;
  border-radius: 50%;
  border: 2px solid #0cf;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 30px;
  color: #0cf;
  transition: 0.4s;
  margin-left: 20px;
}
.social-media i:hover {
  background: #0cf;
  color: #333;
  box-shadow: 0 0 10px #0cf;
  transition: 0.4s;
}
</style>
