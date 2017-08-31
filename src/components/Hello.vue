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
          <dd v-if="site"><i class="fa fa-home"></i> <a :href="site" target="_blank" >{{ site }}</a></dd>
          <dd v-if="github"><i class="fa fa-github"></i> <a :href="github" target="_blank">{{ github }}</a></dd>
          <dd><svg></svg></dd>
        </div>
        <div class="contact">
          <dt>Job. 应聘岗位</dt>
          <dd>{{ job }}</dd>
        </div>
        <div class="contact">
          <dt>Description. 自我介绍</dt>
          <p class="self-description">我是一个可能有着重度代码强迫症的 Web 攻城狮，生活在二次元与三次元的之间。喜欢钻研技术，有着自己的职业规划</p>
        </div>
      </div>
    </div>

    <div class="right">
      <div class="aera">
        <div class="contact">
          <dt>Info. 个人信息</dt>
          <dd>学校：{{ school }}</dd>
          <dd>学历：{{ diploma }}</dd>
          <dd>专业：{{ major }}</dd>
          <dd>毕业时间：{{ guaduation }}</dd>
        </div>
        <div class="contact">
          <dt>Experience. 工作经历</dt>
          <dd v-for="experience in experiences">{{ experience }}</dd>
        </div>
        <div class="contact">
          <dt>Skill. 专业技能</dt>
          <dd v-for="skill in skills">{{ skill }}</dd>
        </div>
        <div class="contact">
          <dt>Project. 项目经历</dt>
          <dd v-for="project in project">
            <h3>{{ project.name }}</h3>
            <p class="project-description">{{ project.description }}</p>
          </dd>
        </div>
      </div>
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
      job: 'PHP 开发工程师',
      site: 'https://is.daryl.moe',
      github: 'https://github.com/Daryl-L',
      school: '杭州电子科技大学',
      diploma: '工学学士',
      major: '信息安全（保密技术）',
      guaduation: '2016 年 6 月',
      experiences: [
        '杭州安恒信息技术有限公司（2015.8 ~ 2015.12）',
        '杭州边锋网络技术有限公司（2015.12 至今）'
      ],
      skills: [
        '了解 Linux 系统的常用命令，能够做比较简单的运维、代码部署、环境搭建。',
        '熟悉 PHP 语言，熟悉 CodeIgniter、Laravel 等框架，初步了解 Swoole 网络库，了解 PSR 的各项规范，对代码有洁癖，希望能够写出优雅的代码。',
        '了解计算机网络的相关知识，了解 HTTP 协议的相关知识，了解 TCP/IP 协议族相关知识，正在学习网络编程。',
        '了解前端相关知识，使用过 vuejs 框架',
        '熟悉 git 相关命令，并对 git flow 有研究并付诸实践。',
        '了解 Restful API，并参与部门项目前后端分离项目的 API 设计与开发。',
        '了解常见的网络安全知识，有网络安全方面的实践。'
      ],
      project: [
        {
          name: '对 SDK 服务稳定性与性能提升改造（2017.6 ~ 2017.9）',
          description: 'dddddd'
        },
        {
          name: '游戏网站主页及后台（2015.12 ~ 2016.1）'
        },
        {
          name: '投放后台（2016.3 ~ 2016.4）'
        },
        {
          name: 'SDK 数据报表（2016.7 至今）'
        },
        {
          name: '若干微信活动（2016.7 至今）'
        }
      ]
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
    width: 370px;
    padding: 20px 30px 50px 20px;
    margin-left: auto;
  }

  .right {
    position: relative;
    overflow: hidden;
    float: left;
    width: 690px;
    padding: 20px 20px 50px 20px;
  }

  .aera {
    /*width: 670px;*/
    position: relative;
    /*float: left;*/
    /*background: linear-gradient(160deg, #3FD1E1 0%, #44D7CD 100%);*/
    /*background: linear-gradient(160deg, #00AEFF 0%, #3369E7 100%);*/
    /*background: linear-gradient(160deg, #e43a15 0%, #e65245 100%);*/
    background: #fff;
    box-shadow:
      /**rgba(63, 209, 225, 0.35) -2px -2px 20px,
      rgba(63, 209, 225, 0.35) 5px 5px 30px;*/
      0 4px 30px 0 rgba(223,225,230,0.5);
    border-radius: 5px;
    padding: 10px 10px 10px 0;
    color: rgb(71, 81, 90);
  }

  .avatar {
    margin-top: 10px;
    width: 150px;
    height: 150px;
    border-radius: 75px;
  }

  .contact {
    margin-top: 20px;
    /*margin-left: 10px;*/
    text-align: left;
  }

  .contact a {
    color: #08a4e8;
  }

  .contact dt {
    font-size: 25px;
    font-weight: 300;
    border-left: solid 3px #2da8cd;
    /*box-shadow: 1px 0 12px 0 #6190E8;*/
    padding-left: 15px;
    margin-top: 10px;
    /*<!--margin-left: -2px;-->*/
  }

  .contact dd {
    font-size: 16px;
    font-weight: 400;
    -webkit-margin-start: 17px;
    margin-top: 20px;
  }

  .self-description {
    text-indent: 2em;
    margin-left: 10px;
  }

  .project-description {
    margin-left: 10px;
  }

  dd i {
    width: 16px;
  }

  dd h3 {
    font-weight: 400;
  }

  h1 {
    font-weight:200;
    margin-bottom: 50px;
  }
</style>
