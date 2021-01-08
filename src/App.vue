<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <div class="container" style="background-color:palevioletred;">
        <div class="pt-4 text-white" style="background-color: palevioletred; text-align: center;">
            <header>
                <h1 class="p-2 font-light" style="font-size: larger; letter-spacing: 0.5rem; font-weight: normal;">{{ name }}</h1>
   
            </header>

        </div>
        <div class="row">
          <div class="col-11">
              <div class="d-flex justify-content-center">
            <div class="card mt-5 " style="width:400px ju">
                <img class="card-img-top" src="./assets/aa.jpg" alt="Card image">

            </div>           
        </div>
          </div>
           <div class="col-1" style="margin-top: 20%" >
              <div class="text-white pb-4" v-if="social_media.facebook !== undefined">
                <a :href="'https://facebook.com/'+social_media.facebook" target="_blank"> <i class="fab fa-facebook-f"></i></a>
              </div> 
              <div class="text-white pb-4" v-if="social_media.instagram !== undefined">
                <a :href="'https://instagram.com/'+social_media.instagram"  target="_blank"><i class="fab fa-instagram"></i></a>
              </div>

              <div class="text-white pb-4" v-if="social_media.snapchat !== undefined">
                <a :href="'https://snapchat.com/'+social_media.snapchat"  target="_blank"><i class="fab fa-snapchat-square"></i></a>
              </div>
              <div class="text-white pb-4" v-if="social_media.twitter !== undefined">
                <a :href="'https://twitter.com/'+social_media.twitter"  target="_blank"><i class="fab fa-twitter-square"></i></a>
              </div>

              <div class="text-white pb-4" v-if="social_media.email !== undefined">
                <a :href="'mailto:'+social_media.email"><i class="fas fa-envelope-square"></i></a>
              </div>
            </div>
        </div>

        <ul class="nav justify-content-center  mt-5 ml-5">
            <li class="nav-item" style="font-size: larger; letter-spacing: 0.5rem; font-weight: normal;">
                <a class="nav-link text-white" href="#"> Home</a>
            </li>
            <li cclass="nav-item" style="font-size: larger; letter-spacing: 0.5rem; font-weight: normal;">
                <a class="nav-link text-white" href="#"> About</a>
            </li>
            <li class="nav-item" style="font-size: larger; letter-spacing: 0.5rem; font-weight: normal;">
                <a class="nav-link text-white" href="#"> Gallery</a>
            </li>
            <li class="nav-item">
                <img class="card-img-top" src="./assets/bb.jpg" alt="Card image">
            </li>
            <li class="nav-item" style="font-size: larger; letter-spacing: 0.5rem; font-weight: normal;">
                <a class="nav-link text-white" href="#"> Contact</a>
            </li>
        </ul>
    </div>
  </div>
</template>

<script>
import axios from "axios"
export default {
  name: 'App',
  data(){
    return {
      name: "",
      social_media: {

      }
    }
  },
  async mounted(){
    const res = await axios.get('https://hirng-x2021.glitch.me/api');
    const { name, social_media } = res.data
    this.name = name;
    this.social_media = social_media
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
a {
  color: white;
}
</style>
