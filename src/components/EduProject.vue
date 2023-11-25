<template>
  <div class="container mt-4" id="project">
    <h1 style="color: #00f">Projects</h1>
    <div class="row" :class="{active:show}" >
      <div class="panel" v-for="pro in projects" :key="pro.id">
        <div class="ring">
          <div class="card card1"></div>
          <div class="border">
            <p class="title">{{ pro.pname }}</p>
            <h5 class="mt-5"><span>Domain</span> : {{ pro.domain }}</h5>
            <div class="slide">
              <div class="line">
                <h6 class="para">{{ pro.about }}</h6>
              </div>
              <div class="line">
                <h6 class="para">Language:{{ pro.language }}</h6>
              </div>
              <div class="line">
                <h6 class="para" style="position: relative">
                  <a
                    :href="pro.link"
                    class="btn btn-success btn-md-danger btn-sm-info "
                    id="btn"
                    target="_blank"
                    >View here</a
                  >
                </h6>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="d-grid gap-2 col-6 mx-auto mt-5 mb-5">
      <button
        class="btn btn-info"
        @click="Handlechange"
        ref="Toggle_bar"
        type="button"
      >
        Show More
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "EduTwo",
  data() {
    return {
      projects: [],
      show: false,
    };
  },
  created() {
    const jsonData = require("../assets/DatasJSON/project.json");
    this.projects = jsonData;
  },
  methods:{
    Handlechange(){
      this.show=!this.show;
      this.$refs.Toggle_bar.innerText = this.show? "Show less" : "Show More";
    }
  }
};
</script>

<style scoped>

#btn{
  cursor: pointer;
  z-index:100;
  border:3px solid #50c9c3;
  padding: 5px;
}
.para{
  z-index:100;
}
.row {
  width: 100%;
  padding: 20px 40px;
  position: relative;
  display: flex;
  margin: auto;
  margin-bottom: 3rem;
  margin-top: 3rem;
  /* grid-template-columns: repeat(auto-fit, minmax(320px, 0.5fr)); */
  gap: 4rem;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  border-radius: 30px;
  height:400px;
  overflow: hidden;
  transition:.5s;
}
.active{
  transition:.5s;
  height: 100%;
  overflow:none;
}

.panel {
  height: 350px;
  width: 280px;
  position: relative;

  &:hover {
    .card {
      filter: blur(1.5px);
    }
    .card1 {
      background-size: 215% 135%;
    }
    .card2 {
      background-size: 115% 115%;
    }
    .card3 {
      background-size: 155% 115%;
    }
    .title {
      color: rgba(255, 255, 255, 0.2);
    }
    .border {
      border: 1px solid rgba(255, 255, 255, 1);
    }
    .slide {
      bottom: 0px;
    }
    .ring:before,
    .ring:after {
      transform: translateX(-50%) translateY(-50%) rotate(310deg);
    }
  }
}
.ring,
.card,
.border,
.slide,
.line {
  display: flex;
  justify-content: center;
  align-items: center;
}

.ring {
  color: #fffbf1;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translateX(-50%) translateY(-50%);
  font-size: 170px;
}

.card {
  background: #f0ead6;
  position: relative;
  transition: all 1s;
  height: 350px;
  width: 280px;
  border: 1px solid rgba(255, 255, 255, 1);
}

.card1 {
  /* background-image: url("https://assets.codepen.io/489403/brazil.jpg"); */
  background-image: url("../assets/Image/Tech1.jpeg");

  background-repeat: no-repeat;
  background-size: 200% 120%;
}
/*   */

.ring:before,
.ring:after {
  content: "";
  padding: 0.7em 0.4em;
  position: absolute;
  left: 50%;
  width: 170%;
  top: 50%;
  display: block;
  border: 5px solid #50c9c3;
  border-radius: 50%;
  transition: transform 1s;
  transform: translateX(-50%) translateY(-50%) rotate(50deg);
}

.ring:before {
  border-color: rgb(235, 235, 235) rgb(235, 235, 235) rgba(0, 0, 0, 0)
    rgba(0, 0, 0, 0);
  z-index: -1;
  opacity: 0.4;
}

.ring:after {
  border-color: rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) rgb(235, 235, 235)
    rgb(235, 235, 235);
  opacity: 0.4;
}

p {
  text-align: center;
  position: absolute;
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  font-size: 1.2rem;
}

.title {
  font-size: 1.8rem;
  font-weight: 700;
  transition: all 1s;
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  color: orangered;
  top: 0;
  display: flex;
  background: rgba(0, 0, 0, 0.5);
  align-items: center;
  justify-content: center;
}

.para {
  bottom: 0;
  font-size: 1.1rem;
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
  padding: 10px;
  margin: 0;
  text-align: center;
  background: rgba(0, 0, 0, 0.5);
}

.border {
  position: absolute;
  border: 1px solid rgba(255, 255, 255, 0.5);
  height: 260px;
  width: 180px;
  transition: border 1s;
  overflow: hidden;
}

.slide {
  height: 260px;
  width: 180px;
  position: absolute;
  border: 1px solid black;
  bottom: -270px;
  background: rgba(0, 0, 0, 0.5);
  transition: bottom 1s;
  flex-direction: column;
}

.fa-plane {
  font-size: 16px;
}
</style>
