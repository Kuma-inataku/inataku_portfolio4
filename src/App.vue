<template>
  <v-app>
    <!-- <v-navigation-drawer app v-model="drawer" clipped>Navigation Lists</v-navigation-drawer> -->
    <v-app-bar color="#64B5F6" dark app>
    <!-- <v-app-bar color="primary" class="red--text" app> -->
      <!-- <v-app-bar-nav-icon @click="drawer=!drawer"></v-app-bar-nav-icon> -->
      <v-toolbar-title>
        
        <router-link text to="/" class="text-decoration-none">
          <v-img src="./assets/images/good1.png" ></v-img>
          <!-- 邦ログ --><!-- ロゴは委託中 -->
        </router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="d-flex justify-center">
        <!-- <v-btn text to="#about">About</v-btn> -->
        <v-btn text to="/about">About</v-btn>
        <v-btn text to="/contact">Contact</v-btn>
        <v-btn text to="/carendar">Carendar</v-btn>
      </v-toolbar-items>
    </v-app-bar>
      <!-- <div class="sns-image">
        <a href="https://twitter.com/TkTkTkTkTako">
          <img src=".\assets\images\twitter.jpg" width="60px" height="60px"/>
        </a>
        <a href="https://www.instagram.com/kuma_kuma_0121/">
          <img src=".\assets\images\instagram.jpg" alt="" width="60px" height="60px"/>
        </a>
      </div> -->
    <v-main>
    <router-view />
    <Loading v-show="loading"></Loading>
    <Home v-show="!loading"></Home>
    </v-main>
    <v-footer padless color="#64B5F6" dark>
      <v-col class="text-center">
        Copyright© 2020 Japanese Rock Consultant All Rights Reserved.
      </v-col>
    </v-footer>
  </v-app>
</template>

<script>
import Loading from '@/components/Loading'
// import Home from './views/Home'

export default {
  data(){
    return{
      drawer:null,
      loading:true
    }
  },
  watch:{
    //#aboutでaboutコラムへ行く
    // '$route':function(n, o){
    //   if (n.hash.match(/^#/)){
    //     document.getElementById(n.hash.replace(/^#/,'')).scrollIntoView()
    //   }
    //   console.log('new,old',[n.hash, o.hash])
    // }
  },
    mounted() {
      //#aboutでaboutコラムへ行く
      // if(this.$route.hash.match(/^#/)){
      //   document.getElementById(this.$route.hash.replace(/^#/, '')).scrollIntoView()
      // }
    setTimeout(() => {
      this.loading = false;
    }, 1700);
  },
  components: {
    Loading,
    // Home,
  },
};
</script>
<style>
/* .sns-image{
    width: 3.57143rem;
    position: fixed;
    z-index: 9999;
    top: 45vh;
    left: 0;
    right: auto;
} */
.v-application a{
  /* text-decoration: none; */
  font-weight: bold;
  color: #fff;
}
</style>