<template>
  <div class=" right">
    <div class="cover" v-for="skills in Skill" :key="skills.id1">
      <div class="skills">
        <div class="skill-name">{{ skills.name }}</div>
        <div class="skill-bar">
          <div
            class="skill-per"
            :per="skills.pers+'%'"            
            :style="{'max-width':skills.pers +'%'}"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HorizontalProgress",
  data() {
    return {
      Skill: [],
    };
  },
  created() {
    const jsonData = require("../../assets/DatasJSON/OtherSkill.json");
    this.Skill = jsonData;
  },
};
</script>

<style scoped>
.right {
  width:100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  /* background: #4b4bc8; */
  border-radius:20px;
}
.right .cover {
  width:100%;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  /* background: darkorange; */
  margin: 2rem;
}
.skills{
    width: 100%;
    padding: 0 30px;
}
.skill-name{
    font-size: 18px;
    font-weight: 700;
    color: #f1f1f1;
    text-transform:uppercase;
    margin: 20px 0px;
}
.skill-bar{
    height: 14px;
    background:#282828;
    border-radius:3px;
}
.skill-per{
    height: 14px;
    background:#4b4bc8;
    /* background: #d13639; */
    border-radius: 3px;
    position: relative;
    animation:fillBars 4s linear ;
    animation-delay:4s;
}
.skill-per::after{
    content: attr(per);
    position:absolute;
    padding:6px 9px;
    background:#f1f1f1;
    border-radius:4px;
    font-size: 12px;
    font-weight: 700;
    top: -35px;
    right: 0;
    color: #4b4bc8;
}
.skill-per::before{
content:'';
position: absolute;
width: 10px;
height:10px;
background: #f1f1f1;
top:-15px;
right:20px;
transform: translateX(50%) rotate(45deg);
border-radius:3px;
}
@keyframes fillBars {
    from{
        width: 0;
        transition:2.5s;
        animation-delay:3s;
    }
    to{
        width:100%;
        transition:2.5s;
        animation-delay:3s;
    }
}
</style>
