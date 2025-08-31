<template>
  <div id="app">
    <navbar/>
    <div class="c-home">
      <div class="c-home-background" :style="{'background-image':'url(background1.jpg)'}"></div>
      <div class="c-c-home-social-icon">
        <div class="c-home-social-icon">
          <i class="fab fa-facebook-f"></i>
          <i class="fab fa-instagram"></i>
          <i class="fab fa-github"></i>
        </div>
      </div>
      <div class="c-home-ulust">
        <h1 class="c-home-ulust-first-sent">AIR</h1>
        <img src="spa1.png">
        <h1 class="c-home-ulust-second-sent">MAX</h1>
      </div>
      <div class="c-c-home-colors">
        <div class="c-home-colors">
            <div class="first-color"></div>
            <div class="second-color"></div>
            <div class="third-color"></div>
        </div>
      </div>
    </div>
    <div class="c-c-after-home">
       <div class="c-c-new-version">
         <div class="c-new-version-title">
           <h2 class="new-version-title">New Version</h2>
         </div>
         <div class="c-new-version">
            <div class="version" v-for="shoe in shoes" :key="shoe.shoe_name">
              <div class="new-version-img" :style="{ backgroundImage: `url(${shoe.shoe_img})` }"></div>
              <div class="new-version-info"><h3 class="new-version-name">{{shoe.shoe_name}}</h3><h4 class="new-version-price">{{shoe.shoe_price}}</h4></div>
            </div>
         </div>
       </div>
       <div class="shoes-video">
         <div class="background-shoes-video"></div>
         <i class="fas fa-play" @click="getdata"></i>
       </div>
       <div class="c-c-products">
         <div class="c-c-products-title">
           <h1>Products</h1>
          </div>
         <div class="c-products">
           <div class="product" v-for="product in data.data.sneakers.slice(0,20)" :key="product.brand_name">
             <div class="product-image" :style="{ backgroundImage: `url(${product.original_picture_url})` }"></div>
             <div class="c-product-title"><h3>{{product.brand_name}}</h3><like/></div>
             <div class="c-product-price"><h4>53.45$</h4></div>
           </div>
         </div>
         <div class="c-view-more">
           <button class="view-more">View More</button>
         </div>
       </div>
       <div class="c-about">
            <div class="background-about"></div>
            <h2>About Us</h2>
            <p>Lorem Ipsum est simplement est le faux texte standard de l'imprimerie depuis les années 1500, quand un imprimeur anonyme assembla ensemble des morceaux de texte pour réaliser un livre spécimen de polices de texte.</p>
            <button>More</button>
       </div>
        <div class="c-markes">
          <div class="markes">
            <img src="https://www.freepnglogos.com/uploads/michael-jordan-logo-png-hd-10.png">
            <img src="https://www.freepnglogos.com/uploads/reebok-logo-png/reebok-hd-logo-picture-4.png">
            <img src="https://www.freepnglogos.com/uploads/adidas-logo-png-black-0.png">
            <img src="https://freepngimg.com/thumb/nike_logo/6-2-nike-logo-free-png-image.png">
            <img src="https://www.freepnglogos.com/uploads/puma-logo-png-1.png">
          </div>
        </div>
       </div>
       <div class="footer">
         <h4>All rights reserved © 2021 , <a href="https://www.facebook.com/mostapha.elkaddaoui.9889/">elkaddaoui</a></h4>
       </div>
    </div>
</template>

<script>
import navbar from './navbar.vue'
import axios from 'axios'
import like from './like.vue'
export default {
  name: 'App',
  components: {
      navbar,
      like,
  },
  data: function(){
    return{
     data:"",
     shoes:[
      {
        shoe_img:"https://images.pexels.com/photos/4252970/pexels-photo-4252970.jpeg?auto=compress&cs=tinysrgb&h=750&w=1260",
        shoe_name:"Nike Air Max",
        shoe_price:"55.53$",
      },
      {
        shoe_img:"https://images.pexels.com/photos/1464624/pexels-photo-1464624.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940",
        shoe_name:"Nike Loden",
        shoe_price:"79.99$",
      },
      {
        shoe_img:"https://images.pexels.com/photos/6540939/pexels-photo-6540939.jpeg?auto=compress&cs=tinysrgb&h=750&w=1260",
        shoe_name:"Air Jordan",
        shoe_price:"105.36$",
      },
      {
        shoe_img:"https://images.pexels.com/photos/4233114/pexels-photo-4233114.jpeg?auto=compress&cs=tinysrgb&h=750&w=1260",
        shoe_name:"yeezys 350",
        shoe_price:"37.00$",
      },
    ]
    }
  },
  mounted () {
    axios
      .get('https://raw.githubusercontent.com/Stupidism/goat-sneakers/master/api.json')
      .then(response => (this.data = response))
  },
  methods: {
   getdata: function(){
     console.log(this.data.data.sneakers)
   },
    
  },
  
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Exo+2:wght@900&display=swap');
.c-home{
  position: absolute;
  top: 85px;
  left: 0px;
  width: 100%;
  height: 520px;
}.c-home-background{
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 100%;
  background-position:center;
  filter: opacity(7%);
}.c-home-ulust{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  height: 350px;
  width: 600px;
}
.c-home-ulust-first-sent{
  position: absolute;
  top: 0px;
  left: 0px;
  color:#607d8bba;
  font-size:170px;
  font-family: fantasy;
}.c-home-ulust img{
  position: absolute;
  top: 10px;
  left: 5%;
  height: auto;
  width: 450px;
  transform: rotate(336deg);
}.c-home-ulust-second-sent{
  position: absolute;
  bottom: 0px;
  right: 0px;
  color:#d914228f;
  font-size:170px;
  font-family: fantasy;
}.c-c-home-social-icon{
  position: absolute;
  top: 50%;
  right: 0px;
  transform: translate(0%,-50%);
  height: 300px;
  width: 150px;
}.c-home-social-icon{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  height:auto;
  width: auto;
  display: grid;
}.c-home-social-icon i{
  color: black;
  font-size: 20px;
  margin: 15px 0px 15px 0px;
}.c-c-home-colors{
  position: absolute;
  top: 50%;
  left: 0px;
  transform: translate(0%,-50%);
  height: 300px;
  width: 150px;
}.c-home-colors{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  height:auto;
  width: auto;
  display: grid;
}.c-home-colors div{
  padding:10px;
  border:6px solid white;
  border-radius: 50%;
  margin: 15px 0px 15px 0px;
}.first-color{
  background-color: #e7202c;
}.second-color{
  background-color: #fac048;
}.third-color{
  background-color: green;
}.c-c-after-home{
  position: absolute;
  top: 605px;
  left: 0px;
  width:100%;
  height:3395px;
}.c-c-new-version{
  position: absolute;
  top: 0px;
  left: 0px;
  width:100%;
  height: 500px;
}.c-new-version{
  position: absolute;
  top: 110px;
  left: 50%;
  transform: translate(-50%,0%);
  width:70%;
  height: 425px;
  display:inline-flex;
}.version{
  width: 23%;
  height: 440px;
  margin: 0px 1% 0px 1%;
  cursor: pointer;
}.c-new-version-title{
  position: absolute;
  top: 55px;
  left: 50%;
  transform: translate(-50%,0%);
  height: auto;
  width: 70%;
}.new-version-title{
  margin: 0px 0px 0px 1%;
  font-size: 25px;
  font-family: fantasy;
}.new-version-img{
  width:100%;
  height:380px;
  background-size: cover;
  background-position: center;
}.new-version-info{
  width:100%;
  height: auto;
}.new-version-name{
  margin: 10px 0% 0% 0%;
  font-size: 20px;
  font-family: system-ui;
  color:#d914228f;
}.new-version-price{
  margin: 5px 0% 0% 0%;
  font-size: 15px;
  font-family: monospace;
  color:#607d8bba;
}.shoes-video{
  position: absolute;
  top: 620px;
  left: 0px;
  width:100%;
  height:450px;
}.background-shoes-video{
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 100%;
  background-image:url('https://s3.amazonaws.com/nikeinc/assets/80340/UNCLE_DREW_BW_LAYDOWN__hd_1600.jpg?1529524900');
  background-size:cover;
  background-position:center;
  filter: opacity(15%);
}.shoes-video i{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  color:#d914228f;
  font-size: 45px;
  cursor:pointer;
}.c-c-products{
  position: absolute;
  top: 1125px;
  left: 0px;
  width: 100%;
  height: 1700px;
}.c-c-products-title {
    position: absolute;
    top: 0px;
    left: 50%;
    transform: translate(-50%,0%);
    height: auto;
    width: 70%;
}.c-c-products-title h1 {
    margin: 0px 0px 0px 1%;
    font-size: 25px;
    font-family: fantasy;
}.c-products {
    position: absolute;
    top: 55px;
    left: 50%;
    transform: translate(-50%,0%);
    width: 70%;
    height: 425px;
    display: inline-flex;
    flex-wrap: wrap;
}.product{
    width: 23%;
    height: 287px;
    margin: 0px 1% 20px 1%;
    cursor: pointer;
    background-color: #f0f0f066;
    padding: 10px;
    border-radius: 5px;
}.product-image{
    position: relative;
    top: 0px;
    left: 0px;
    width:100%;
    height:190px;
    background-size:cover;
    transform: rotatey(180deg);
}.c-product-title{
  margin-top: 30px;
  width:100%;
  display: inline-flex;
}.c-product-title h3{
  margin-left: 2px;
  font-size: 20px;
  font-family: system-ui;
  color: #d914228f;
  width: -webkit-fill-available;
}.c-product-title i{
  color: #d914228f;
  font-size:18px;
  cursor: pointer;
  margin:7px;
  filter: drop-shadow(0px 0px 10px #d91422b0);
}.c-product-price{
  margin-left: 2px;
}.c-product-price h4{
  font-size: 15px;
  font-family: monospace;
  color: #607d8bba;
}.c-view-more{
  position: absolute;
  top: 1615px;
  left: 50%;
  transform: translate(-50%,0%);
}.view-more{
  border: 1px solid black;
  background-color: white;
  color: black;
  padding: 10px;
  width: 130px;
  font-size: 18px;
  font-family: fantasy;
}.c-about{
  position: absolute;
  top: 2825px;
  left: 0px;
  width:100%;
  height:350px;
}.background-about{
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 100%;
  background-image:url("https://images.pexels.com/photos/5584997/pexels-photo-5584997.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940");
  background-size: cover;
  background-position: center;
  filter: opacity(15%);
}.c-about h2{
  position: absolute;
  top: 45px;
  left: 50%;
  transform: translate(-50%,0%);
  color:black;
  font-size:30px;
  font-family: fantasy;
}.c-about p{
  position: absolute;
  top: 125px;
  left: 50%;
  transform: translate(-50%,0%);
  color:black;
  font-size:20px;
  font-family: monospace;
  width:50%;
  text-align:center;
}.c-about button{
  position: absolute;
  top: 255px;
  left: 50%;
  transform: translate(-50%,0%);
  border: 1px solid black;
  background-color: transparent;
  color: black;
  padding: 12px;
  width: 170px;
  font-size: 18px;
  font-family: fantasy;
  cursor:pointer;
}.c-markes{
  position: absolute;
  top: 3175px;
  left: 0px;
  width:100%;
  height:210px;
  display:inline-flex;
}.c-markes img{
  margin: 6%;
  width: 8%;
}.markes{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  width:85%;
  height:auto;
}.footer{
  position: absolute;
  top: 4000px;
  left: 0px;
  width:100%;
  height:55px;
  background-color:#d914228f;
}.footer h4{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  font-size:15px;
  font-family: monospace;
  color:white;
}.footer a{
  color:white;
}

</style>
