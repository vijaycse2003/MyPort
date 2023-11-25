<template>
  <div class="container">
    <div class="row">
      <div class="col-lg-5 col-md-5 col-sm-12 left">
        <div class="box">
          <div class="content">
            <img src=".././assets/Image/tech.jpg" alt="hello" />
            <h2>Someone Famous <br /><span>Fullstack Developer</span></h2>
            <a href="">Hire Me</a>
          </div>
        </div>
      </div>
      <div class="col-lg-5 col-md-5 col-sm-12 right"  data-aos="fade-left"
        data-aos-easing="linear"
        data-aos-duration="1800">
        <h1>About Me</h1>
        <h6>
          I am dedicated and highly motivated IT professional with a passion for
          solving complex technical challanges.My journey in IT began with a
          deep curiosity for technology ,and over the years,I have horned my
          skills through hands-on experience,continous learning,and professional
          certificate such as Python,C,C++ programming languages.One of my
          strength is my abilty to communicate technical concepts in clear and
          understandable manner.
        </h6>
        <div class="datas">
      <ul>
        <li>Name</li>
        <li>Dob</li>
        <li>Address</li>
        <li>Pincode</li>
        <li>Email</li>
        <li>Phno</li>
      </ul>
      <ul>
        <li><span>:</span> Vijay k</li>
        <li><span>:</span>March 24 2003</li>
        <li><span>:</span>Sholapuram(Kumbakonam)</li>
        <li><span>:</span>612 503</li>
        <li><span>:</span>vijtech2003@gmail.com</li>
        <li><span>:</span>+91 7010239965</li>
      </ul>
    </div>
        <a href="#" target="_blank">DOWNLOAD CV</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
};
</script>

<style scoped>
h6 {
  font-size: 1.3rem;
  font-weight: 700;
  line-height: 1.6;
  letter-spacing: 0.03em;
}
  ul {
      width: 50%;
    }
    ul li {
      list-style: none;
    }
    .datas{
        display: flex;
        text-align:left;
        font-size:1.2rem;
        color: azure;
    }
    span{
        padding-right:2rem;
    }
    ul:nth-child(1){
        width: auto;
    }
    ul:nth-child(2){
        width: auto;
    }
.row {
  width:100%;
  height:650px;
  display: flex;
  align-items:center;
  margin-bottom:20%;
  justify-content:space-between;
}
.left {
  width: 60%;
  height: 100%;
  display: grid;
  place-items: center;
}
a[target="_blank"] {
  color: #fff;
  background: #00f;
  text-decoration: none;
  padding: 10px 16px;
  letter-spacing: 0.06em;
  border-radius: 10px;
  transition: 0.6s;
}
a[target="_blank"]:hover {
  border: 2px solid #00ccff;
  transition: 0.5s;
  filter: blur(2px);
}

.right {
  width: 40%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  flex-direction: column;
  text-align: left;
  padding: 10px;
}
.right h1 {
  color: blue;
  text-align: left;
  letter-spacing: 0.2em;
}
.right ul li {
  text-align: left;
  list-style: none;
}
.right ul {
  text-align: left;
}

.box {
  position: relative;
  width: 400px;
  height: 400px;
  background: #162052;
  border-radius: 50%;
  overflow: hidden;
}
.box::before {
  content: "";
  position: absolute;
  inset: -10px 140px;
  background: linear-gradient(315deg, #00ccff, #d400d4);
  transition: 0.5s;
  animation: animate 4s linear infinite;
}
.box:hover::before {
  inset: -20px 0px;
}
.box::after {
  content: "";
  position: absolute;
  inset: 6px;
  background: #000000;
  border-radius: 50%;
  z-index: 1;
}

@keyframes animate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.content {
  position: absolute;
  inset: 30px;
  z-index: 3;
  border: 6px solid #070a1c;
  border-radius: 50%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.content img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: 0.5s;
  pointer-events: none;
  z-index: 3;
}
.box:hover .content img {
  transition: 0.5s;
  opacity: 0;
}
.content h2 {
  font-size: 1.4rem;
  position: relative;
  text-align: center;
  font-weight: 600;
  color: #fff;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}
.content h2 span {
  font-weight: 300;
  font-size: 0.75em;
}
.content a {
  position: relative;
  margin-top: 10px;
  padding: 10px 20px;
  background: #fff;
  color: #070a1c;
  border-radius: 25px;
  text-decoration: none;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  transition: 0.5s;
}
.content a:hover {
  letter-spacing: 0.2em;
}

@media screen and (max-width: 990px) {
  .row {
    width: 100%;
    height: 500px;
    display: flex;
    align-items: center;
    margin-bottom: 80%;
    justify-content: center;
    margin-top: 8rem;
  }
  .left {
    text-align: center;
    width: 100%;
    padding: 2px;
    display: flex;
    align-items: center;
    margin-bottom: 12rem;
    justify-content: center;
  }
  .right h6 {
    flex-wrap: nowrap;
  }
  .right {
    text-align: center;
    width: 100%;
    display: flex;
    max-width: 100%;
    margin-top: 40px;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    padding: 10px;
  }
}
</style>
