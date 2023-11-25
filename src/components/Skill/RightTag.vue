<template>
<div class="bodys" v-show="rshow">
     <div class="card">
      <div class="imgBox"><img src="../../assets/Image/Myimg.jpeg" alt="er" ><img src="../../assets/Image/Myrg.png" alt="er" ></div>
      <div class="details">
        <div class="content">
          <h2>Someone Tech<br /><span>Fullstack Developer</span></h2>
          <h6>We don't just build websites, we build websites that SELLS”</h6>
          <div class="social-icons">
            <a href=""><i class="fa fa-facebook"></i></a>
            <a href=""><i class="fa fa-linkedin"></i></a>
            <a href=""><i class="fa fa-instagram"></i></a>
            <a href=""><i class="fa fa-github"></i></a>
          </div>
        </div>
      </div>
    </div>
    </div>
</template>

<script>
export default {
    name:'RightTag',
    props:{
        rshow:Boolean
    }
}
</script>
 
 <style scoped>
  
    .bodys{
      height:100%;
      width:100%;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #000;
    }
    .card {
      position: relative;
      width: 300px;
      color:#fff;
      height: 400px;
      background: #fff;
      transform-style: preserve-3d;
      transform: perspective(1000px);
      box-shadow: 10px 20px 40px rgba(0, 0, 0, 0.25);
      transition:1s;
    }
    .card .details {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      padding: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .card .details .content {
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
    }
    .card .details .content h6{
      text-align:center;
      letter-spacing: 1px;
      color: #333;
      font-weight: 500;
    }
    .card .details .content h2 {
      text-align: center;
      font-weight: 700;
      line-height: 1em;
      color:#000;
    }
    .card .details .content h2 span {
      color: red;
      font-style: 0.8em;
    }
    .card .details .content .social-icons {
      position: relative;
      display: flex;
      margin-top: 10px;
    }
    .card .details .content .social-icons a {
        display: inline-block;
        width: 35px;
        height: 35px;
        background: #333;
        color: #fff;
        display: flex;
        justify-content: center;
        align-items: center;
        text-decoration: none;
        margin: 5px;
        font-size: 18px;
        transition: 0.3s;
    }
    .card .details .content .social-icons a:hover {
        background-color: red;
    }
    .card .imgBox img{
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        transform-style:preserve-3d;
        backface-visibility: hidden;
    }
    .card .imgBox img:nth-child(2){
        transform:rotateY(180deg);
    }
    .card:hover{
        transform: translateX(50%);
    }
    .card .imgBox{
     position: relative;
     width: 100%;
     height: 100%;
     z-index:1;
     transform-origin: left;
     transform-style:preserve-3d;
     background:#000;
     transition:1s;
     box-shadow: 10px 20px 40px rgba(0, 0, 0, 0.25);
    }
    .card:hover .imgBox{
        transform:rotateY(-180deg);
    }
 </style>