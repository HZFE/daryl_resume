<template>
  <div class="container">
    <div class="left">
      <div class="aera">
        <img v-if="avatar" v-bind:src="avatar" alt="" class="avatar">
        <h1>{{ name }}的简历</h1>
        <div class="contact">
          <dt>Contact. 联系方式</dt>
          <dd v-if="phoneNumber"><i class="fa fa-phone"></i> {{ phoneNumber }}</dd>
          <dd v-if="email"><i class="fa fa-envelope"></i> {{ email }}</dd>
          <dd v-if="qq"><i class="fa fa-qq"></i> {{ qq }}</dd>
          <dd v-if="wechat"><i class="fa fa-wechat"></i> {{ wechat }}</dd>
        </div>
        <div class="contact">
          <dt>Job. 应聘岗位</dt>
          <dd>{{ job }}</dd>
        </div>
        <div class="contact">
          <dt>Description. 自我介绍</dt>
        </div>
      </div>
    </div>

    <div class="right">
      <div class="aera">3333</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      avatar: 'https://o90cnn3g2.qnssl.com/WechatIMG19.jpeg',
      name: '梁翰雷',
      phoneNumber: '15958154647',
      email: 'daryl.moe@outlook.com',
      qq: '286065910',
      wechat: 'Daryl-L',
      job: 'PHP 开发工程师'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  /*@import "../../semantic/dist/semantic.min.css";*/
  @import '../../node_modules/font-awesome/css/font-awesome.css';
  .container {
    overflow: hidden;
    position: relative;
    /*background: #bff7ff;*/
    /*@media(min-width: 768px) {*/
      width: 90%;
    /*}*/
    margin-left: auto;
    margin-right: auto;
    /*box-shadow: #7cfff3 0 0 20px;*/
    border-radius: 5px;
  }

  .left {
    position: relative;
    overflow: hidden;
    float: left;
    width: 380px;
    padding: 30px 30px 50px 0;
    margin-left: auto;
  }

  .right {
    position: relative;
    overflow: hidden;
    float: left;
    width: 700px;
    padding: 30px 20px 50px 10px;
  }

  .aera {
    /*width: 670px;*/
    position: relative;
    /*float: left;*/
    background: linear-gradient(160deg, #3FD1E1 0%, #44D7CD 100%);
    /*background: linear-gradient(160deg, #3369E7 0%, #00AEFF 100%);*/
    box-shadow: rgba(102, 102, 102, 0.25) 5px 5px 30px;
    border-radius: 5px;
    padding: 10px;
    color: #fff;
  }

  .avatar {
    margin-top: 10px;
    width: 150px;
    height: 150px;
    border-radius: 75px;
  }

  .contact {
    margin-top: 20px;
    margin-left: 10px;
    text-align: left;
  }

  .contact dt {
    font-size: 20px;
    font-weight: 300;
    border-left: solid 2px #fff;
    padding-left: 15px;
    margin-top: 10px;
  }

  .contact dd {
    font-size: 16px;
    font-weight: 300;
    -webkit-margin-start: 10px;
    margin-top: 10px;
  }

  dd i {
    width: 16px;
  }

  h1 {
    font-weight:200;
  }
</style>
