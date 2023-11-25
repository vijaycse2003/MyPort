
<template>
<NavBar/>
<Header/>
<About/>
<EduOne/>
<EduTwo/>
<EduSkills/>
<EduCardDesign/>
<EduThree/>
<Contact/>
<Footer/>
</template>

<script>
import NavBar from './components/Nav.vue'
import Header from './components/Header.vue'
import About from './components/About.vue'
import EduOne from './components/EduQuality.vue'
import EduTwo from './components/EduProject.vue'
import EduSkills from './components/EduSkills.vue'
import EduCardDesign from './components/DesignCardBio.vue'
import EduThree from './components/EduCertificate.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Header,
    About,
    EduOne,
    EduTwo,
    EduSkills,
    EduCardDesign,
    EduThree,
    Contact,
    Footer,
  }
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@500&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Poppins&family=Roboto:wght@500&display=swap');
@import "https://fonts.googleapis.com/css?family=Sofia";
@import "https://fonts.googleapis.com/css?family=Amita";


#app {
  font-family:'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
  margin:0;
  padding:0;
  width: 100vw;
  box-sizing:border-box;
  overflow:hidden;
  background-color:#000;
}

</style>
