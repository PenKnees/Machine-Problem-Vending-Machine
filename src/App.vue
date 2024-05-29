<template>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://unicons.iconscout.com/release/v4.0.8/css/line.css">
    <title>Machine Problem</title>
</head>

<div class="container">
  <nav id="header">
    <div class="nav-logo">
      <p class="nav-name">Vending M</p>
      <span>.</span>
    </div>
  </nav>

<main class="wrapper">
  <section class="featured-box" id="home">
                <div class="featured-text">
                    <div class="featured-text-card">
                    </div>
                    <div class="featured-name">
                        <p>I am a <span class="typedText">Vending</span></p>
                    </div>
                    <div class="featured-text-info">
                        <p>A simple app that accepts an initial value for the "Bill" and outputs the "Owed" amount as change, detailing the specific values based on Philippine currency.</p>
                    </div>
                    <div class="featured-text-btn">
                      <!-- <button class="btn" >USE ME!<i class="uil uil-money-withdrawal"></i></button> -->
                    </div>
                    <div class="social-icons">
                        <div class="icons"><i class="uil uil-instagram"></i></div>
                        <div class="icons"><i class="uil uil-linkedin-alt"></i></div>
                        <div class="icons"><i class="uil uil-facebook-f"></i></div>
                        <div class="icons"><i class="uil uil-telegram-alt"></i></div>
                    </div>
                </div>
                <!-- <div class="featured-image">
                    <div class="image">
                      <spline-viewer class="image" url="https://prod.spline.design/mF797fODcNf1eK3d/scene.splinecode"></spline-viewer>
                     
                    </div>
                    <h2 class="signhead">Sign in</h2>
                </div> -->
                <div class="featured-image">
                
                <div class="image col-lg-4 col-md-12 col-sm-12 col-xs-12">
                 <h2 class="signhead">Bill & Owed</h2>
                 <input type="number" v-model.number="bill" placeholder="Bill">
                <input type="number" v-model.number="owed" placeholder="Owed">
                <button @click="displayChange">Calculate Change</button>
                <p v-if="result !== null">Change is:  {{ result }}</p>
                <p v-if="bill1 >= 1">{{ bill1 }} <i class="uil uil-money-bill bill1"></i> P1000 Bill</p>
                <p v-if="bill2 >= 1">{{ bill2 }} <i class="uil uil-money-bill bill2"></i> P500 Bill</p>
                <p v-if="bill3 >= 1"> {{ bill3 }} <i class="uil uil-money-bill bill3"></i> P200 Bill</p>
                <p v-if="bill4 >= 1">{{ bill4 }} <i class="uil uil-money-bill bill4"></i> P100 Bill</p>
                <p v-if="bill5 >= 1">{{ bill5 }} <i class="uil uil-money-bill bill5"></i> P50 Bill</p>
                <p v-if="bill6 >= 1"> {{ bill6 }} <i class="uil uil-money-bill bill6"></i> P20 Bill</p>
                <p v-if="coin1 >= 1"> {{ coin1 }} <i class="uil uil-usd-circle coin"></i> P10 coin(s)</p>
                <p v-if="coin2 >= 1">{{ coin2 }} <i class="uil uil-usd-circle coin"></i> P5 coin(s)</p>
                <p v-if="coin3 >= 1"> {{ coin3 }} <i class="uil uil-usd-circle coin"></i> P1 coin(s)</p>
              </div>
              
              </div>

            </section>
</main>


</div>

</template>


<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}
.container{
    width: 100%;
    position: relative;
}
.btn{
    font-weight: 500;
    padding: 12px 20px;
    background: #efefef;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    transition: .5s;
}
.btn>i{
    margin-left: 10px;
}
.btn:hover{
    background:rgb(192,166,49);
    color: white;
}
i{
    font-size:16px;
}
nav{
    position: fixed;
    display: flex;
    justify-content: space-between;
    width: 100%;
    height: 90px;
    line-height: 90px;
    background-color: white;
    padding-inline: 9vw;
    transition: .3s;
    z-index: 100;
}
.nav-logo{
    position: relative;
}
.nav-name{
    font-size: 30px;
    font-weight: 600;
    color: var(--text-third-color);
}
.nav-logo span{
    position: absolute;
    top: -15px;
    right: -20px;
    font-size: 5em;
    color: var(--text-second-color);
}
.wrapper{
    padding-inline: 10vw;
}
.featured-box{
    position: relative;
    display: flex;
    height: 100vh;
    min-height: 700px;
}
.featured-text{
    position: relative;
    display: flex;
    justify-content: center;
    align-content: center;
    min-height: 80vh;
    flex-direction: column;
    width: 50%;
    padding-left: 20px;
}
.featured-text-card span{
    background: var(--third-color);
    color:rgb(192,166,49);
    padding: 3px 8px;
    font-size: 12px;
    border-radius: 5px;
}
.featured-name{
    font-size: 50px;
    font-weight: 600;
    color: var(--text-second-color);
    margin-block: 20px;
}
.typedText{
    text-transform: capitalize;
    color: rgb(192,166,49);
}
.featured-text-info{
    font-size: 15px;
    margin-bottom: 30px;
    color: rgb(192,166,49);
}
.feature-text-btn{
    display: flex;
    gap: 20px;
}
.featured-text-btn> .blue-btn{
    background:var(--text-third-color);
    color: var(--color-white);
}

.feature-text-btn> .blue-btn:hover{
    background: var(--first-color-hover);   
}

.social-icons{
    display: flex;
    margin-top: 1em;
    gap: 30px;
}
.icons{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    box-shadow: 0px 3px 5px 0px rgba(0,0,0,0.5);
    cursor: pointer;
}
/* .featured-image{
    display: flex;
    justify-content: right;
    align-content: center;
    min-height: 80vh;
    width: 50%;
}
.image{
    margin: auto 0;
    width: 500px;
    border-radius: 55% 45% 55% 50%;
    height: 500px;
    overflow: hidden;
   
}
.image img{
    width: 500px;
    height: 500px;
    object-fit: cover;
} */
.featured-image{
    display: flex;
    justify-content: center;
    height: 80vh;
    width: 50%;
}

.image{
    margin-top: 200px;
    width: 380px;
    height: 400px;
    overflow: hidden;
}

.image img{
    width: 380px;
    height: 380px;
    object-fit: cover;
}
.image input {
            width: 100%;
            max-width: 300px;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
            transition: border-color 0.3s ease;
        }
        .image input:focus {
            border-color: #007bff;
            outline: none;
        }
        .image button {
            background-color: #007bff;
            color: #fff;
            border: none;
            cursor: pointer;
            width: 80%;
            height: 40px;
            border-radius: 5px;
        }
        .image button:hover {
            background-color: #0056b3;
        }
.signhead{
  font-family: 'Poppins', sans-serif;
  font-size:50px;
  margin-bottom: 10px
}
.bill1{
  color: blue
}
.bill2{
  color: yellow
}
.bill3{
  color: green
}
.bill4{
  color: violet
}
.bill5{
  color: maroon
}
.bill6{
  color: orange
}
.coin{
  color: slategrey
}
</style>

<script>
import Typed from 'typed.js';
import ScrollReveal from 'scrollreveal';
import SplineViewer from '@splinetool/viewer';
export default {
  name: "indexPage",
  data() {
    return {
      SplineViewer,
      bill: null, //initialize
      owed: null,
      result: null,
      bill1: null,
      bill2: null,
      bill3: null,
      bill4: null,
      bill5: null,
      bill6: null,
      coin1:null,
      coin2:null,
      coin3:null,
    };
  },
   mounted() {
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();

        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
          target.scrollIntoView({
            behavior: 'smooth'
          });
        }
      });
    });

    // Initialize Typed.js
    new Typed(".typedText", {
      strings: ["Vending", "Machine"],
      loop: true,
      typeSpeed: 75,
      backSpeed: 100,
      backDelay: 2000
    });
    const sr = ScrollReveal({
    origin: 'top',
    distance: '80px',
    duration: 2000,
    reset: true
  });

  sr.reveal('.featured-text-card', {});
  sr.reveal('.featured-name', { delay: 100 });
  sr.reveal('.featured-text-info', { delay: 500 });
  sr.reveal('.featured-text-btn', { delay: 600 });
  sr.reveal('.social-icons', { delay: 700 });
  sr.reveal('.featured-image', { delay: 800 });
  sr.reveal('.top-header',{});
  sr.reveal('.item',{});

  },
  methods: {
    getChange(bill,owed){
      return bill-owed;
    },
    displayChange() {
      this.result = this.getChange(this.bill, this.owed);
    this.bill1 = Math.floor(this.result / 1000);
    this.result %= 1000;
    this.bill2 = Math.floor(this.result / 500);
    this.result %= 500;
    this.bill3 = Math.floor(this.result / 200);
    this.result %= 200;
    this.bill4 = Math.floor(this.result / 100);
    this.result %= 100;
    this.bill5 = Math.floor(this.result / 50);
    this.result %= 50;
    this.bill6 = Math.floor(this.result / 20); 
    this.result %= 20;
    this.coin1 = Math.floor(this.result / 10);
    this.result %= 10;
    this.coin2 = Math.floor(this.result / 5);
    this.result %= 5;
    this.coin3 = Math.floor(this.result / 1);


    this.result = this.getChange(this.bill, this.owed);
}

    
    
  },

};
</script>