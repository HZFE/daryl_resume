<template>
  <div id="app">
    <router-view></router-view>

    <footer>
      <p>Theme by <a href="https://github.com/HZFE/daryl_resume">Daryl</a>. Made with ❤️ by <a href="https://is.daryl.moe">Daryl</a>. Thanks to <a href="https://hzfe.org">HZFE</a>.</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style type="less">
  /*@import 'assets/FiraCode-Regular.otf';*/
  @font-face {
    font-family: "Fira Code";
    src: url('assets/FiraCode-Regular.otf');
  }

  html, body {
    /*width: 12ZZ80px;*/
    background: rgb(248, 250, 255);
    margin: 0;
  }
#app {
  font-family: "Fira Code", cursive， Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 40px;
  max-width: 1280px;
  margin-left: auto;
  margin-right: auto;
  width: 1280px;
}

@page {
  size: 10in;
}

  a {
    color: #08a4e8 ;
  }
</style>
