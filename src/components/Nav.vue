<template>
  <header>
    <figure class="brand">
      <h2>Portfolio</h2>
      <h2>Portfolio</h2>
    </figure>
    <nav class="menu">
      <input type="checkbox" id="menuToggle" />
      <label for="menuToggle" class="menu-icon"
        ><i class="fa fa-bars"></i
      ></label>
      <ul>
        <a
          href="#"
          ><li>Home</li></a
        >
        <a href="#skill"><li>Skill</li></a>
        <a href="#project"><li>projects</li></a>
        <a href="#certifi"><li>Certificate</li></a>
        <a href="#contacts"><li>Contact</li></a>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "nav-bar",
};
</script>

<style scoped>
.brand {
  position: relative;
}
.brand h2 {
  position: absolute;
  transform: translate(-50%, -50%);
  color: #000;
  padding-top: 45px;
  padding-left:45px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  /* font-size:3em; */
}

.brand h2:nth-child(1) {
  color: transparent;
  -webkit-text-stroke: 2px #03a9f4;
}

.brand h2:nth-child(2) {
  color: #fff;
  animation: animate 4s ease-in-out infinite;
}
@keyframes animate {
  0%,100%{
    clip-path: polygon(
      0% 45%,
      15% 44%,
      32% 50%,
      54% 60%,
      70% 61%,
      84% 59%,
      100% 52%,
      100% 100%,
      0% 100%
    );
  }
  50%{
    clip-path: polygon(
      0% 60%,
      16% 65%,
      34% 66%,
      51% 62%,
      67% 50%,
      84% 45%,
      100% 46%,
      100% 100%,
      0% 100%
    );
  }
}

a {
  text-decoration: none;
}
li {
  list-style: none;
}
header {
  width: 100%;
  height:50px;
  line-height: 50px;
  text-align: center;
  font-family: sans-serif;
  background-color: #000;
  position:relative;
  clear: both;
}
.brand {
  width:50%;
  height: 100%;
  float: left;
  text-align: center;
  font-size: 2.4rem;
  font-weight: 800;
  padding-left:5rem;
}

.menu {
  width: 50%;
  height: 100%;
  float: right;
}
.menu ul {
  width: 100%;
  height: inherit;
  margin: 0;
  padding: 0;
  display: -webkit-box; /* OLD - iOS 6-, Safari 3.1-6 */
  display: -moz-box; /* OLD - Firefox 19- (buggy but mostly works) */
  display: -ms-flexbox; /* TWEENER - IE 10 */
  display: -webkit-flex; /* NEW - Chrome */
  display: flex; /* NEW, Spec - Opera 12.1, Firefox 20+ */
}
.menu ul a {
  width: 15%;
  height: inherit;
  display: inline-block;
  color: #fff;
  font-size: 1.2rem;
  transition: 0.2s;
  font-weight: 400;
}
.menu ul a:hover {
  opacity: 0.7;
  transition: 0.2s;
  color: #e9c7c7;
  font-weight: 400;
  filter: blur(.4px);
}
#menuToggle {
  display: none;
}
.menu-icon {
  display: none;
}
/*Início das configurações da Navigation com dispositivos < 768px*/
@media screen and (max-width: 768px) {
  .menu {
    width: 100%;
    height: auto;
  }
  .menu ul {
    display: block;
    max-height: 0px;
    overflow: hidden;
    transition: 0.3s;
  }
  .menu ul a {
    text-align: center;
    width: 100%;
    height: 50px;
    background-color: #000;
    padding: 10px 0px 10px 5%;
    color: #fff;
    font: 1.3rem 700 "Roboto";
  }
  .menu-icon {
    width: 100px;
    height: inherit;
    display: block;
    position: absolute;
    top: 0;
    right: 0;
    line-height: 60px;
  }
  #menuToggle:checked ~ ul {
    max-height: 350px;
  }
  .menu-icon i {
    font-size: 1.7em;
  }
}
</style>
