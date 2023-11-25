<template>
  <div class="container" id="certifi">
    <h1 style="color: #00f">Certificates</h1>
    <div class="row" :class="{ active: show }">
      <div class="card" v-for="pro in certi" :key="pro.id">
        <div class="imgBx"><img src="../assets/Image/Lion.jpg" alt="" /></div>
        <div class="content">
          <h2>{{ pro.cname }}</h2>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum odit
            officia rem, soluta voluptates inventore quibusdam maiores, unde
            sint itaque saepe nesciunt recusandae sequi reprehenderit dolorum
            autem dolorem voluptatem eos?
          </p>
          <button
            class="btn btn-danger"
            @click="AlterChange(pro['percentage'], pro['detail'], pro['path'],pro['ins'])"
          >
            View
          </button>
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
import Swal from "sweetalert2";

export default {
  name: "Eduthree",
  data() {
    return {
      certi: [],
      show: false,
    };
  },
  created() {
    const jsonData = require("../assets/DatasJSON/Data.json");
    this.certi = jsonData;
  },
  methods: {
    Handlechange() {
      this.show = !this.show;
      this.$refs.Toggle_bar.innerText = this.show ? "Show less" : "Show More";
    },
    AlterChange(per, detail, url,ins) {
      console.log(per,detail,url,ins)
      Swal.fire({
        title:`Certificates ${ins}`,
        imageUrl:require(`../assets/Cerificate/${url}`),
        imageWidth: 350,
        imageHeight: 350,
        imageAlt: "Error Occured",
        html: `<b>Percentage : ${per} <br> ${detail} </b>`,
        color:"#fff",
        background: "#444",
        confirmButtonText: "Back",
      });
    },
  },
};
</script>
<style scoped>
.row {
  position: relative;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 10px 20px;
  padding: 30px;
  height: 300px;
  overflow: hidden;
}
.active {
  height: 100%;
  overflow: none;
}
.row .card {
  position: relative;
  max-width: 300px;
  height: 215px;
  background: #222;
  margin: 30px 10px;
  padding: 20px 15px;
  display: flex;
  flex-direction: column;
  box-shadow: 0 5px 202px rgba(0, 0, 0, 0.5);
  transition: 0.3s ease-in-out;
}
.row .card:hover {
  height:600px;
  transition: 0.3s;
}
.row .card .imgBx {
  position: relative;
  width: 260px;
  height: 260px;
  top: -60px;
  left: 0;
  display: grid;
  place-items: center;
  z-index: 1;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.5);
}
.row .card .imgBx img {
  width: 250px;
  height: 250px;
  border-radius: 5px;
  border-radius: 30px;
}
.row .card .content {
  position: relative;
  margin-top: -140px;
  padding: 10px 15px;
  text-align: center;
  color: #fff;
  visibility: hidden;
  opacity: 0;
  transition: 0.3s;
}
.row .card:hover .content {
  visibility: visible;
  opacity: 1;
  margin-top: -50px;
  transition-delay: 0.3s;
}
</style>
