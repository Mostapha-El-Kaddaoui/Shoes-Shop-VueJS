<template>
  <div id="app">
    <div class="c-nav-bar">
        <div class="nav-bar">
            <div class="c-logo"><img src="nike-logo.png"></div>
            <div class="c-funav">
                <ul dir="rtl" class="ul">
                    <router-link to="/">Home</router-link>
                    <router-link to="/">Products</router-link>
                    <router-link to="/">Contact</router-link>
                    <router-link to="/">Help</router-link>
                </ul>
            </div>
            <div class="c-iconav">
             <div>
                <i class="fas fa-shopping-cart"></i>
                <i class="far fa-heart"></i>
             </div>
            </div>
        </div>
    </div>
  </div>
</template>
<style>
@import url('https://fonts.googleapis.com/css2?family=Exo+2:wght@700&display=swap');
.c-nav-bar{
    position: absolute;
    top:0px;
    left:0px;
    width:100%;
    height:85px;
}.nav-bar{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    width:90%;
    height: 50px;
}.c-logo{
    position: absolute;
    top: 0px;
    left: 0px;
    width:10%;
    height:100%;
}.c-funav{
    position: absolute;
    top: 50%;
    left: 46%;
    transform: translate(-50%,-50%);
    width:75%;
    height:100%;
}.c-iconav{
    position: absolute;
    top: 0px;
    right: 0px;
    width:15%;
    height:100%;
}.c-logo img{
    position: absolute;
    top: 50%;
    left: 0%;
    transform: translate(0%,-50%);
    width: 70px;
    cursor:pointer;
}
.c-funav ul{
    position: absolute;
    top: 50%;
    left: 0px;
    transform: translate(0%,-50%);
}
.c-funav ul a{
    color:rgb(77, 67, 67);
    font-family: fantasy;
    font-size:15px;
    text-decoration:none;
    margin-right:30px;
    cursor:pointer;
}.c-iconav div{
    position: absolute;
    top: 50%;
    right: 0%;
    transform: translate(0%,-50%);
}.c-iconav div i {
    color:black;
    font-size: 20px;
    margin-right:10px;
    cursor:pointer;
}
</style>
