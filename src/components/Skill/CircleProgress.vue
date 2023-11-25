<template>
  <div class="left col-md-5 col-lg-5 col-sm-12 col-12">
    <div class="cont" v-for="bars in Bar" :key="bars.id">
      <div class="card">
        <div class="percent" :style="{'--clr':bars.color,'--num':bars.pers}">
          <div class="dot"></div>
          <svg>
            <circle cx="70" cy="70" r="70"></circle>
            <circle cx="70" cy="70" r="70"></circle>
          </svg>
          <div class="number">
            <h2>{{ bars.pers }}<span>%</span></h2>
            <p>{{ bars.cname }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CircleProgress",
  data() {
    return {
      Bar: [],
    };
  },
  created() {
    const jsonData = require("../../assets/DatasJSON/Skill.json");
    this.Bar= jsonData;
  },
};
</script>

<style scoped>

.left {
  max-width:100%;
  width:100%;
  margin:10px 0px;
  padding: 20px 40px;
  position: relative;
  display: grid;
  margin: auto;
  margin-bottom: 20px;
  grid-template-columns: repeat(auto-fit, minmax(150px,1fr));
  grid-gap: 3.8em;
  border-radius: 30px;
  background:#151710;
}

.cont {
  width: 100%;
  height: 100%;
}
.cont .card {
  position: relative;
  width: 180px;
  height: 200px;
  background:transparent;
  border-radius:50%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.cont .card .percent {
  height: 150px;
  width: 150px;
  position: relative;
}
.cont .card .percent svg {
  height: 150px;
  width: 150px;
  position: relative;
  transform: rotate(270deg);
}
.cont .card .percent svg circle {
  width: 100%;
  height: 100%;
  fill: transparent;
  stroke-width: 4;
  stroke: #19191919;
  transform: translate(5px, 5px);
}
.cont .card .percent svg circle:nth-child(2) {
  stroke: var(--clr);
  stroke-dasharray: 440;
  stroke-dashoffset: calc(440 - (440 * var(--num)) / 100);
  opacity: 0;
  animation: fadeIn 1s linear forwards;
  animation-delay: 2.5s;
}
@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.dot {
  position: absolute;
  inset: 5px;
  z-index: 10;
  transform: rotate(calc(3.6deg * var(--num)));
  animation: animDot 2s linear forwards;
}
@keyframes animDot {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(calc(3.6deg * var(--num)));
  }
}
.dot:before {
  content: "";
  position: absolute;
  width: 20px;
  height: 12px;
  background: var(--clr);
  top: -5px;
  left: 50%;
  border-radius: 50%;
  box-shadow: 0 0 10px var(--clr), 0 0 30px var(--clr);
}
.number {
  position: absolute;
  inset: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  opacity: 0;
  animation: fadeIn 1s linear forwards;
  animation-delay: 2.5s;
}
.number h2 {
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
  font-weight: 700;
  font-size: 2.5rem;
}
.number span {
  font-weight: 300;
  color: #fff;
  font-size: 0.5em;
}
.number p {
  font-weight: 300;
  font-size: 0.75em;
  letter-spacing: 2px;
  position: absolute;
  bottom: 20%;
  text-transform: uppercase;
  color: rgba(255, 255, 255, 0.75);
}

</style>
