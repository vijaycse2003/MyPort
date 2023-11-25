<template>
  <div class="container">
    <div class="row">
      <h1 style="color: #00f">Education</h1>
      <div class="drop" style="--clr: #ff0f8b">
        <div class="content">
          <h1>2018</h1>
          <p>
            <span>90%</span><br>Minerva higher secoundary school<br /><span style="color: blue">
              Kadichambadi</span
            >
          </p>
          <a href="#" @click="AlertChange('https://lh3.googleusercontent.com/p/AF1QipOnCoq0_QZ5f5KFG-qDGbo3hd61pHkEcoySSj0h=s1360-w1360-h1020')">Show</a>
        </div>
      </div>
      <div class="drop" style="--clr: #be01fe">
        <div class="content">
          <h1>2020</h1>
          <p>
           <span>70%</span><br> Town Higher Secoundary School<br /><span style="color: blue"
              >Kumbakonam</span
            >
          </p>
          <a href="#" @click="AlertChange('https://lh3.googleusercontent.com/p/AF1QipMy8WyjADFadA_cUE-Pd3EXNgGa3MWJmX6kRKrV=s1360-w1360-h1020')">Show</a>
        </div>
      </div>
      <div
        class="drop"
        style="--clr: #01b4ff; border-radius: 73% 27% 59% 41% / 57% 59% 42% 43%"
      >
        <div class="content">
          <h1>2024</h1>
          <p>
           <span>8.5cgpa</span><br> Anjalai ammal Mahalingam Engineering College<br /><span
              style="color: blue"
              >Thiruvarur</span
            >
          </p>
          <a href="#" @click="AlertChange('https://lh3.googleusercontent.com/p/AF1QipNLLIrEEGWjBwf81SAMtwaZDf0-Zv0dcXekTl2x=s1360-w1360-h1020')">Show</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Swal from "sweetalert2";
export default {
  name: "EduOne",
  methods: {
    AlertChange(url) {
      Swal.fire({
        title: "Education System",
        imageUrl:url,
        imageWidth:350,
        imageHeight:350,
        imageAlt:'Error Occured',
        html: "<b>My Education Path Travel gain for Some Knowldge</b>",
        background: "#333",
        confirmButtonText: "Back",
      });
    },
  },
};
</script>

<style scoped>
.row {
  width: 100%;
  margin-top: 3rem;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #0e0f09;
  flex-wrap: wrap;
  padding: 30px 20px;
  gap: 40px 60px;
  border-radius: 20px;
  color: #fff;
}
.row .drop {
  position: relative;
  width: 350px;
  height: 350px;
  box-shadow: inset 20px 20px 20px #00000033, 25px 35px 20px #00000033,
    25px 30px 30px #00000033, inset -20px -20px 25px #1f1919cc;
}
.row .drop:nth-child(1) {
  border-radius: 47% 53% 70% 30% / 30% 43% 57% 70%;
}
.row .drop:nth-child(2) {
  border-radius: 57% 43% 59% 41% / 43% 43% 57% 57%;
}
.row .drop:nth-child(3) {
  border-radius: 73% 27% 59% 41% / 57% 59% 42% 43%;
}
.row .drop:hover {
  border-radius: 50%;
  transition: 0.5s;
}
.row .drop::before {
  content: "";
  position: absolute;
  top: 50px;
  left: 90px;
  width: 35px;
  height: 35px;
  background: #222;
  border-radius: 50%;
}
.row .drop::after {
  content: "";
  position: absolute;
  top: 90px;
  left: 110px;
  width: 15px;
  height: 15px;
  background: #222;
  border-radius: 50%;
}
.row .drop .content {
  width: 100%;
  height: 100%;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  flex-direction: column;
  padding: 40px;
  font-size: 1.2rem;
  gap: 15px;
}
.row .drop .content h1 {
  position: relative;
  padding: 20px;
  background: #0a0c10;
  border-radius: 50%;
  box-shadow: inset 2px 5px 10px rgba(0, 0, 0, 0.5),
    inset -2px -5px 10px #483f3f, 15px 5px 10px rgba(0, 0, 0, 0.5),
    15px 5px 15px rgba(0, 0, 0, 0.25);
  display: grid;
  place-items: center;
  font-size: 2em;
  color: var(--clr);
}
.row .drop .content a {
  position: relative;
  padding: 10px 45px;
  background: var(--clr);
  text-decoration: none;
  color: #fff;
  border-radius: 25px;
  font-weight: 600;
  letter-spacing: 0.02em;
  opacity: 0.75;
  transition: 0.5s;
  text-shadow: 0 2px 2px rgba(0, 0, 0, 0.25);
}
.row .drop .content a:hover {
  opacity: 1;
  transition: 0.5s;
}

@media screen and (max-width: 990px) {
  .row {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 65rem;
    flex-direction: column;
  }
}
</style>
