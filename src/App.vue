<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style type="less">
  /*@import 'assets/FiraCode-Regular.otf';*/
  html, body {
    width: 1280px;
    background: rgb(248, 250, 255);
  }
#app {
  font-family: "Fira Code", cursive， Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  /*@media(min-width: 768px) {*/
    margin-top: 40px;
  /*}*/
  min-width: 1080px;
}
</style>
