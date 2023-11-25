<template>
  <div class="container">
    <div class="row" id="contacts">
      <div class="contactUS">
        <div class="title">
          <h2>Contact Us</h2>
        </div>
        <div class="box">
          <div class="contact form">
            <h3>Send a Message</h3>
            <form @submit.prevent="onSubmit">
              <div class="formBox">
                <div class="row50">
                  <div class="inputBox">
                    <span> First Name</span>
                    <input type="text" placeholder="Vijay" name="fname" ref="fname"/>
                  </div>
                  <div class="inputBox">
                    <span> Last Name</span>
                    <input type="text" placeholder="kumar" name="lname" ref="lname"/>
                  </div>
                </div>

                <div class="row50">
                  <div class="inputBox">
                    <span> Email</span>
                    <input type="email" placeholder="vijaycse7935@gmail.com" name="email" ref="email"/>
                  </div>
                  <div class="inputBox">
                    <span> Mobile </span>
                    <input type="text" placeholder="+91 7010239965" name="pnum" ref="pnum" />
                  </div>
                </div>

                <div class="row100">
                  <div class="inputBox">
                    <span>Message</span>
                    <textarea
                      placeholder="Write your message here ..."
                      name="msg"
                      ref="msg"
                    ></textarea>
                  </div>
                </div>

                <div class="row100">
                  <div class="inputBox">
                    <input type="submit" value="Send" />
                  </div>
                </div>
              </div>
            </form>
          </div>
          <div class="contact info">
            <h3>Contact Info</h3>
            <div class="infoBox">
              <div>
                <span><ion-icon name="location"></ion-icon></span>
                <p>kumbakonam , TamilNadu<br />India</p>
              </div>

              <div>
                <span><ion-icon name="mail"></ion-icon></span>
                <a href="mailto:vijayaarthi9965@gmail.com"
                  >vijayaarthi9965@gmail.com</a
                >
              </div>
              <div>
                <span><ion-icon name="call"></ion-icon></span>
                <a href="mailto:vijayaarthi9965@gmail.com">+91 7010239965</a>
              </div>
              <ul class="sci">
                <li>
                  <a href="#"><ion-icon name="logo-facebook"></ion-icon></a>
                </li>
                <li>
                  <a href="#"><ion-icon name="logo-twitter"></ion-icon></a>
                </li>
                <li>
                  <a href="www.linkedin.com/in/vijay-k-0831b4228"><ion-icon name="logo-linkedin"></ion-icon></a>
                </li>
                <li>
                  <a href="#"><ion-icon name="logo-instagram"></ion-icon></a>
                </li>
                <li>
                  <a href="https://github.com/vijaycse2003"><ion-icon name="logo-github"></ion-icon></a>
                </li>
              </ul>
            </div>
          </div>
          <div class="contact map">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d7831.5990929676245!2d79.40693734095328!3d11.053650406449675!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3a552c9ab3d4ddf5%3A0xa30eded0cbd79e7d!2sSozhapuram%2C%20Cholapuram%2C%20Tamil%20Nadu%20612503!5e0!3m2!1sen!2sin!4v1699848950081!5m2!1sen!2sin"
              width="300"
              height="350"
              style="border: 0"
              allowfullscreen=""
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
            ></iframe>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {initializeApp} from "firebase/app";
import { getFirestore,addDoc, collection} from "firebase/firestore";
// import {getAnalytics} from 'firebase/analytics'




const firebaseConfig = {
  apiKey: "AIzaSyBmRnoKuPy1zwkpdBmCInEcWwVoe2F5JxQ",
  authDomain: "port-contact-efba4.firebaseapp.com",
  projectId: "port-contact-efba4",
  storageBucket: "port-contact-efba4.appspot.com",
  messagingSenderId: "828081523486",
  appId: "1:828081523486:web:941eca788a586a7c8ed70f",
  measurementId: "G-0XJT1JEDTV"
};

//


const app=initializeApp(firebaseConfig);

// const analytics=getAnalytics(app)

const db=getFirestore(app);

export default {
 name:'contact',
methods:{
   onSubmit(){
    addDoc(collection(db,'PortContact'),{
      email:this.$refs.email.value,
      fname:this.$refs.fname.value,
      lname:this.$refs.lname.value,
      pnum:this.$refs.pnum.value,
      msg:this.$refs.msg.value
    })
    this.$refs.email.value='',
      this.$refs.fname.value='',
      this.$refs.lname.value='',
      this.$refs.pnum.value='',
      this.$refs.msg.value=''
   }
 
}
};
</script>

<style scoped>
.row {
  width: 100%;
  height: 100%;
  margin-bottom: 3rem;
}
.contactUS {
  position: relative;
  width: 100%;
  height: 100%;
}
.contactUS .title {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2em;
}
.contactUS .title h2 {
  color: #00f;
  font-size: 2.5rem;
  font-weight: 500;
}
.contact {
  padding: 40px;
  background: #222;
  box-shadow: 0px 5px 35px rgba(0, 0, 0, 0.5);
}
.form {
  grid-area: form;
}
.map {
  grid-area: map;
}
.info {
  grid-area: info;
}
.box {
  position: relative;
  display: grid;
  grid-template-columns: 2fr 1fr;
  grid-template-rows: 5fr 4fr;
  grid-template-areas:
    "form info"
    "form map";
  grid-gap: 20px;
  margin-top: 20px;
}
.contact h3 {
  color: #0e3959;
  font-weight: 500;
  font-size: 1.4em;
  margin-left: 10px;
}
.formBox {
  position: relative;
  width: 100%;
}
.formBox .row50 {
  display: flex;
  gap: 20px;
}
.inputBox {
  display: flex;
  flex-direction: column;
  margin-bottom: 10px;
  width: 50%;
}
.formBox .row100 .inputBox {
  width: 100%;
}
.inputBox span {
  color: #18b7ff;
  margin-top: 10px;
  margin-bottom: 5px;
  font-weight: 500;
}
.inputBox input {
  padding: 10px;
  font-size: 1.1em;
  outline: none;
  border: 1px solid #333;
}
.inputBox textarea {
  padding: 10px;
  font-size: 1.1em;
  outline: none;
  border: 1px solid #333;
  resize: none;
  min-height: 170px;
  margin-bottom: 10px;
}
.inputBox input[type="submit"] {
  background: #00f;
  color: #fff;
  font-size: 1.1em;
  max-width: 120px;
  font-weight: 500;
  cursor: pointer;
  padding: 14px 15px;
}
.inputBox ::placeholder {
  color: #999;
}

.info {
  background: #0e3959;
}
.info h3 {
  color: #fff;
}
.info .infoBox div {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}
.info .infoBox div span {
  min-width: 40px;
  height: 40px;
  color: #fff;
  background: #18b7ff;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.5rem;
  border-radius: 50%;
  margin-right: 15px;
}
.info .infoBox div p {
  color: #fff;
  font-size: 1.1em;
}
.info .infoBox div a {
  margin-top: 40px;
  display: flex;
}
.sci li {
  list-style: none;
  margin-right: 15px;
  margin-top: 20px;
  display: inline-block;
}
.sci li a {
  color: #fff;
  font-size: 1rem;
}
.sci li a ion-icon {
  font-size: 1.7rem;
}
.sci li a:hover {
  color: #fff;
}
.map {
  padding: 0;
}
.map iframe {
  width: 100%;
  height: 100%;
}

@media screen and (max-width: 990px) {
  .box {
    position: relative;
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: auto;
    grid-template-areas:
      "form"
      "info"
      "map";
    grid-gap: 20px;
    margin-top: 20px;
  }
  .map {
    min-height: 300px;
  }
  .formBox .row50 {
    display: flex;
    gap: 0;
    flex-direction: column;
  }
  .inputBox {
    width: 100%;
  }
}
</style>
