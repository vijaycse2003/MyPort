<template>
  <div class="container2">
    <div class="image-section">
      <img src="../assets/Image/Myrg.png" alt="alter" />
    </div>
    <div class="text-content">
      <div class="span">Vijay k</div>
      <div class="span">Fullstack developer & ML and DL</div>
      <p>
        Programmer is someone who writes and maintain the instruction that computers follow to perform specific tasks.They use programming language to create software,apps,websites
      </p>
      <button class="btn" @click="turnback">Read More</button>
      <div class="social-media">
        <i class="fa fa-instagram"></i>
        <i class="fa fa-linkedin"> </i>
        <i class="fa fa-twitter"></i>
        <i class="fa fa-github">  </i>
      </div>
    </div>
    <div class="buble" ref="dynamicEle">
      <span style="--i:1"></span>
        <span style="--i:2"></span>
        <span style="--i:3"></span>
        <span style="--i:4"></span>
        <span style="--i:5"></span>
        <span style="--i:6"></span>
        <span style="--i:7"></span>
        <span style="--i:8"></span>
        <span style="--i:9"></span>
        <span style="--i:10"></span>
        <span style="--i:11"></span>
        <span style="--i:12"></span>
        <span style="--i:13"></span>
        <span style="--i:14"></span>
        <span style="--i:15"></span>
        <span style="--i:16"></span>
        <span style="--i:17"></span>
        <span style="--i:18"></span>
        <span style="--i:19"></span>
        <span style="--i:20"></span>
        <span style="--i:21"></span>
        <span style="--i:22"></span>
        <span style="--i:23"></span>
        <span style="--i:24"></span>
        <span style="--i:25"></span>

    </div>
  </div>
</template>

<script>
export default {
  name: "BioCard",

  methods: {
    turnback() {
      this.$emit("changeBack", false);
    },
  },
  mounted(){
    const buble = this.$refs.dynamicEle;
    for (let i = 0; i < 30; i++) {
      let span = document.createElement("span");
      span.style.setProperty("--i", i);
      buble.appendChild(span);
    }
  }
   
};
    // data-v-1491fe38
</script>

<style scoped>
.container2 {
  height: 100%;
  width: 100%;
  border: 3px solid;
  border-left-color: #066076;
  border-right-color: #066076;
  border-top-color: #2a032b;
  border-bottom-color: #2a032b;
  filter: drop-shadow(0 0 20px #2a032b);
  display: flex;
  justify-content: space-around;
  flex-direction: column;
  align-items: center;
  position: relative;
  background: transparent;
}
.container2 .buble {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  overflow: hidden;
  z-index: 2;
}

.container2 span {
  width: 35px;
  height: 35px;
  background: #4fc3dc;
  margin: 0 10px;
  border-radius: 50%;
  filter: blur(2px);
  box-shadow: 0 0 0 10px #4fc3dc44, 0 0 50px #4fc3dc, 0 0 100px #4fc3dc;
  animation: animate 25s linear infinite;
  animation-duration: calc(35s / (var(--i)) * 2);
}
.container2 span:nth-child(even) {
  background: #ff2d75;
  box-shadow: 0 0 0 10px #4fc3dc44, 0 0 50px #4fc3dc, 0 0 100px #4fc3dc;
  animation: animate 25s linear infinite;
  animation-duration: calc(80s / var(--i));
}
@keyframes animate {
  0% {
    transform: translateY(100vh) scale(0);
  }
  100% {
    transform: translateY(-10vh) scale(1);
  }
}

.container2 .image-section {
  height: 100%;
  width: 100%;
  background: linear-gradient(#0cf, #ec45f2, #0cf, #ec45f2);
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  transition: 0.6s;
  overflow: hidden;
  z-index: 10;
}
.container2:hover .image-section {
  transition: 20s;
  top: 25%;
  width: 300px;
  height: 300px;
  border-radius: 50%;
}
.container2:hover .image-section img {
  transition: 20s;
  width: 90%;
  height: 90%;
}
img {
  border-radius: 50%;
  background: #000;
  object-fit: cover;
  background-position: center;
  background-size: cover;
  width: 50%;
  height: 100%;
}
.container2:hover .text-content {
  transition: 30s;
  opacity: 1;
  transition: 0.3s ease;
}
.container2 .text-content {
  text-align: center;
  color: #fff;
  font-weight: 500;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: absolute;
  top: 50%;
  opacity: 0;
  z-index: 10;
}
.text-content .span:nth-child(1) {
  letter-spacing: 1px;
  font-size: 32px;
  animation: TopSlide 1s ease forwards;
  opacity: 0;
}
@keyframes TopSlide {
  0% {
    transform: translateY(200px);
    opacity: 0;
    filter: blur(5px);
  }
  100% {
    transform: translateY(0px);
    opacity: 1;
    filter: blur(0);
  }
}
.text-content .span:nth-child(2) {
  letter-spacing: 1px;
  font-size: 24px;
  animation: TopSlide 1s ease forwards;
  opacity: 0;
  animation-delay: 0.6s;
}
.text-content p {
  font-size: 13px;
  max-width: 300px;
  margin-bottom: 10px;
  animation: TopSlide 1s ease forwards;
  opacity: 0;
  animation-delay: 0.8s;
}
.btn {
  width: 100px;
  height: 35px;
  font-size: 15px;
  font-weight: 500;
  background: #222;
  color: #0cf;
  border: 2px solid #0cf;
  cursor: pointer;
  margin-bottom: 20px;
}
.container2:hover .btn {
  animation: TopSlide 1s ease forwards;
  opacity: 0;
  animation-delay: 0.1s;
}
.btn:hover {
  background: #0cf;
  color: #222;
  box-shadow: 0 0 10px #0cf;
}
.container2:hover .social-media {
  animation: TopSlide 1s ease forwards;
  opacity: 0;
  animation-delay: 0.12s;
}
.social-media {
  display: flex;
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
