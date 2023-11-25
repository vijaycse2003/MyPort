<template>
  <div class="container" id="skill">
    <h1 style="color: #00f">Skills</h1>
    <div class="row" :class="{ nactive: isActive }">
     
        <ProCircle />
    
      <HorCircle />
    </div>
    <div class="d-grid gap-2 col-6 mx-auto mt-5 mb-5">
      <button
        class="btn btn-info"
        @click="changeText"
        ref="Toggle"
        type="button"
      >
        Show More
      </button>
    </div>
  </div>
</template>

<script>
import ProCircle from "../components/Skill/CircleProgress.vue";
import HorCircle from "../components/Skill/HorizontalProgress.vue";

export default {
  name: "EduSkills",
  components: {
    ProCircle,
    HorCircle,
  },
  data() {
    return {
      isActive: false,
      loadingComponent: null,
    };
  },
  methods: {
    changeText() {
      this.isActive = !this.isActive;
      this.$refs.Toggle.innerText = this.isActive ? "Show less" : "Show More";
    },
   
  },
};
</script>

<style scoped>
.row {
  position: relative;
  width: 100%;
  margin-bottom: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 10px;
  height: 500px;
  overflow: hidden;
}
.nactive {
  height: 100%;
  overflow: none;
}
</style>
