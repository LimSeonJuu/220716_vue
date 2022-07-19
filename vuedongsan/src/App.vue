<template>
  <div id="app">
      <h1>YBM 잉글루</h1>

      <ul class="nav">
          <li v-for="menus in nav" :key="menus"><a href="#">{{ menus }}</a></li>
      </ul>

      <Modal @closeModal="open = false" :roomdata="roomdata" :idx="idx" :open="open"></Modal>

      <Card @openModal="open = true; idx = $event" :roomInfo="roomdata[i]" v-for="(roomInfo, i) in roomdata" :key="roomInfo"></Card>

      
  </div>
</template>

<script>

import onerooms from './assets/oneroom.js';
import discount from './discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  data() {
      return {
          idx : 0,
          open : false,
          nav : ['YBM 잉글루', '수학의 달인', '오시는 길'],
          roomdata : onerooms,
      }
  },
  components: {
    Discount : discount,
    Modal : Modal,
    Card : Card,
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
body{margin:0}
.nav {
  padding:15px;border-radius:5px;background:darkslateblue;list-style:none
}
.nav>li{display:inline-block;text-decoration:none;}
.nav>li>a{display:inline-block;padding:10px;color:white;text-decoration:none}

.black-bg {
  position:fixed;top:0;bottom:0;width:100%;height:100%;padding:20px;background:rgba(0, 0, 0, 0.5);box-sizing:border-box;
}
.white-bg {
  width:100%;padding:20px;border-radius:8px;background:white;box-sizing:border-box;
}

.room_img{width:500px}

.discount{padding:10px;margin:10px;background:#eee}
</style>
