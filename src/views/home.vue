<template>
  <div class="pos1" @click="posClick">
    <iframe id="embed1" @click="posClick" :src="url" frameborder="0" class="pc iframe" scrolling="auto"></iframe>
  </div>
  <div class="pos2"  @click="posClick">
    <iframe id="embed2" @click="posClick" :src="url" frameborder="0" class="pc iframe" scrolling="auto"></iframe>
  </div>
  <div class="pos3"  @click="posClick">
    <iframe id="embed3" @click="posClick" :src="url" frameborder="0" class="pc iframe" scrolling="auto"></iframe>
  </div>
  <div class="btn1" @click="posClick"></div>
  <div class="btn2" @click="posClick"></div>
  <div class="btn3"></div>
</template>
<script setup>
import { ref } from 'vue'
import interact from 'interactjs'

const url = ref("https://bobobq.cn:18081/#/")

interact('.btn1')
  .on('tap', function (event) {
    console.log(event)
    event.currentTarget.classList.toggle('switch-bg')
    event.preventDefault()
  })

interact('.btn2')
  .on('tap', function (event) {
    console.log(event)
    event.currentTarget.classList.toggle('switch-bg')
    event.preventDefault()
  })

interact('.btn3')
  .on('tap', function (event) {
    console.log(event)
    event.currentTarget.classList.toggle('switch-bg')
    event.preventDefault()
  })

  
interact('.pos1')
  .on('tap', function (event) {
    event.preventDefault()
  })

interact('.pos2')
  .on('tap', function (event) {
    event.preventDefault()
  })
  
interact('.pos3')
  .on('tap', function (event) {
    event.preventDefault()
  })

function posClick (event) {
  console.log("in")
  event.preventDefault()
}
</script>
<style lang="scss" scoped>
.pos1,.pos2,.pos3 {
  border: 1px solid red;
  position: absolute;
  width:1200px;
  height: 750px;
}
.pos1 {
  top: 50px;
  left:60px;
}
.pos2 {
  top: 50px;
  left:1320px;
}
.pos3 {
  top: 50px;
  left:2580px;
}

.btn1,.btn2,.btn3 {
  border: 1px solid rgb(179, 255, 0);
  position: absolute;
  width:60px;
  height: 60px;
  &:active {
    background-color:aqua;
  }
}
.btn1 {
  top: 850px;
  //left:630px;
  left:300px;
}
.btn2 {
  top: 850px;
  //left:1890px;
  left:500px;
}
.btn3 {
  top: 850px;
  //left:3150px;
  left:700px;
}

.iframe {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  width: 100%;
  height: calc(100%);
  background: #fff;
  overflow-y: hidden;
}

.switch-bg {
  background-color: #f40;
}
</style>
<style>
body {
  width: 3840px;
  height: 1080px;
}
</style>
