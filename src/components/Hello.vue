<template>
  <div class="container">
    <div class="left">
      <div class="area">
        <img v-if="avatar" v-bind:src="avatar" alt="" class="avatar">
        <h1>{{ name }}的简历</h1>
        <dl class="contact">
          <dt>Contact. 联系方式</dt>
          <dd v-if="phoneNumber"><i class="fa fa-phone"></i> {{ phoneNumber }}</dd>
          <dd v-if="email"><i class="fa fa-envelope"></i> {{ email }}</dd>
          <dd v-if="qq"><i class="fa fa-qq"></i> {{ qq }}</dd>
          <dd v-if="wechat"><i class="fa fa-wechat"></i> {{ wechat }}</dd>
          <dd v-if="site"><i class="fa fa-home"></i> <a :href="site" target="_blank" >{{ site }}</a></dd>
          <dd v-if="github"><i class="fa fa-github"></i> <a :href="github" target="_blank">{{ github }}</a></dd>
        </dl>
        <dl v-if="job" class="contact">
          <dt>Job. 应聘岗位</dt>
          <dd>{{ job }}</dd>
        </dl>
        <dl v-if="description" class="contact">
          <dt>Description. 自我介绍</dt>
          <dd>
            <p class="self-description">{{ description }}</p>
          </dd>
        </dl>
        <dl v-if="hobby" class="contact">
          <dt>Hobby. 特长爱好</dt>
          <dd>{{ hobby }}</dd>
        </dl>
      </div>
    </div>

    <div class="right">
      <div class="area">
        <dl class="contact">
          <dt>Info. 个人信息</dt>
          <dd>学校：{{ school }}</dd>
          <dd>学历：{{ diploma }}</dd>
          <dd>专业：{{ major }}</dd>
          <dd>毕业时间：{{ guaduation }}</dd>
        </dl>
        <dl v-if="experiences" class="contact">
          <dt>Experience. 工作经历</dt>
          <dd v-for="experience in experiences">{{ experience }}</dd>
        </dl>
        <dl v-if="skills" class="contact">
          <dt>Skill. 专业技能</dt>
          <dd v-for="skill in skills" class="project">
            <div>
              <div class="circle"></div>
              <h3>{{ skill.title }}</h3>
              <p v-for="item in skill.items" class="project-description">{{ item }}</p>
            </div>
          </dd>
        </dl>
        <dl v-if="projects" class="contact">
          <dt>Project. 项目经历</dt>
          <dd v-for="project in projects" class="project">
            <div>
              <div class="circle"></div>
              <h3>
                <span>{{ project.name }}</span>
                <a v-if="project.src" class="project-src" :href="project.src"><i class="fa fa-link"></i>源代码</a>
              </h3>
              <p class="project-description">{{ project.description }}</p>
            </div>
          </dd>
        </dl>
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
      description: '我是一个可能有着重度代码强迫症的 Web 攻城狮，生活在二次元与三次元的之间。喜欢钻研技术，有着自己的职业规划',
      hobby: '围棋、网球、滑雪、动漫',
      school: '杭州电子科技大学',
      diploma: '工学学士',
      major: '信息安全（保密技术）',
      guaduation: '2016 年 6 月',
      experiences: [
        '杭州安恒信息技术有限公司（2015.8 ~ 2015.12）',
        '杭州边锋网络技术有限公司（2015.12 至今）'
      ],
      skills: [
        {
          title: 'PHP',
          items: [
            '熟悉 PHP 语法，了解 PSR 各项规范。',
            '熟悉 CodeIgniter、Laravel 的框架，对 Laravel 的源码有一些研究。',
            '初步了解 Swoole 及其使用。',
            '了解 PHPUnit，并在实际项目中使用 PHPUnit 编写单元测试。',
            '了解 Redis、Memcache 的使用。'
          ]
        },
        {
          title: 'Linux',
          items: [
            '了解 Linux 常用命令，能够做简单的运维、代码部署、环境搭建。',
            '了解 Nginx + PHP 的配置。'
          ]
        },
        {
          title: '前端',
          items: [
            '了解前端相关知识，能与前端配合开发。',
            '使用过 vue.js 框架。'
          ]
        },
        {
          title: '其它',
          items: [
            '了解计算机网络相关知识，了解 HTTP 协议相关知识，初步了解 TCP/IP 相关知识。',
            '熟悉 git 相关命令，在实际项目中实践过 git flow。',
            '了解网络安全方面知识，了解常见的攻击手段，对网络安全有实践。'
          ]
        }
//        '了解 Linux 系统的常用命令，能够做比较简单的运维、代码部署、环境搭建。',
//        '熟悉 PHP 语言，熟悉 CodeIgniter、Laravel 等框架，初步了解 Swoole 网络库，了解 PSR 的各项规范，对代码有洁癖，希望能够写出优雅的代码。',
//        '了解 PHPUnit，并在实际项目中使用编写单元测试。',
//        '了解计算机网络的相关知识，了解 HTTP 协议的相关知识，了解 TCP/IP 协议族相关知识，正在学习网络编程。',
//        '了解前端相关知识，使用过 vuejs 框架',
//        '熟悉 git 相关命令，并对 git flow 有研究并付诸实践。',
//        '了解 Restful API，并参与部门项目前后端分离项目的 API 设计与开发。',
//        '了解常见的网络安全知识，有网络安全方面的实践。'
      ],
      projects: [
        {
          name: '基于 Swoole 的 PHP 框架（个人项目）',
          description: '业余的个人项目，编写的基于 Swoole 的 PHP 框架的开发。因为 zan 是依赖 zan 扩展的，起初的目的是和 zan 一样使用 yield 实现一套异步非阻塞的框架，基于 Swoole 的，用在前面的项目改进上。现在依然还在开发中，模仿了 Laravel 的部分实现。',
          src: 'https://github.com/Daryl-L/Tetsuwan'
        },
        {
          name: 'Resume（个人项目）',
          description: '使用 vue.js 开发的简历模板，还算不丑的界面，可以通过 json 文件生成简历的内容。',
          src: 'https://github.com/HZFE/daryl_resume'
        },
        {
          name: '对 SDK 服务稳定性与性能提升改造',
          description: '在工作之余，分析部门的 SDK 服务，发现了性能可以改进的方向。使用了有赞开源的 zan 框架，对代码进行改造。通过堆栈式协程，将原本同步阻塞的 API 调用，改写为异步非阻塞的 API 调用，极大地提升了程序的性能。自测结果单机由 150QPS 增至 2000QPS。'
        },
        {
          name: '游戏官网及后台',
          description: '公司各款游戏的官网，包括登录、注册、文章发布等功能。后经过改造，开发了统一的后台，可以配置多款游戏。前台根据 Laravel 的模板，对数据接口进行封装，前端可以通过调用封装好的接口实现模块化开发，省去繁琐的套页面工作，节省了大量的时间。'
        },
        {
          name: 'SDK 数据报表',
          description: '配合本部门开发的sdk使用的数据报表。统计 sdk 中所有的数据，对玩家的访问量、留存等进行统计。统计每日流水、金额，并交由财务进行统计以分配收入。其中还有对数据预警的功能。整个系统使用了前后端分离的设计，我负责后端提供代码，是返回的接口尽可能地向 RESTful  d接近。'
        },
        {
          name: '若干微信活动',
          description: '负责开发运营的活动需求，有抽奖活动、预约活动以及兑换活动等。在兑换活动和抽奖活动中使用到了 Redis 来确保奖品数量的正确，并且为抽奖活动编写了模板，做到皮肤、奖品、活动可配置。'
        },
        {
          name: 'SDK 开发者后台',
          description: '为开发者接入 SDK 的配置后台。使用前后端分离的方式开发，我负责部分模块，参与设计 API 的结构。根据公司统一认证的流程，进行一些修改，独自设计了整个登录的流程，以适应前后端分离的结构。对负责的模块的代码编写单元测试，并且对团队成员负责的模块进行单元测试的编写。'
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import '../../node_modules/font-awesome/css/font-awesome.css';
  .container {
    overflow: hidden;
    position: relative;
    margin-left: auto;
    margin-right: auto;
    border-radius: 5px;
  }

  .left {
    position: relative;
    overflow: hidden;
    float: left;
    width: 370px;
    padding: 20px 30px 50px 20px;
    margin-left: 68px;
  }

  .right {
    position: relative;
    overflow: hidden;
    float: left;
    width: 670px;
    padding: 20px 20px 50px 20px;
  }

  .area {
    position: relative;
    background: #fff;
    box-shadow: 0 4px 30px 0 rgba(223,225,230,0.5);
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
    text-align: left;
  }

  .contact a {
    color: #08a4e8;
  }

  .contact dt {
    font-size: 25px;
    font-weight: 300;
    border-left: solid 3px #2da8cd;
    padding-left: 15px;
    margin-top: 10px;
    color: #0396FF;
  }

  .contact dd {
    font-size: 16px;
    font-weight: 400;
    -webkit-margin-start: 17px;
    -webkit-margin-end: 17px;
    margin-top: 20px;
  }

  .self-description {
    text-indent: 2em;
    margin-left: 10px;
  }

  .project-description {
    padding-left: 15px;
  }

  dd i {
    width: 16px;
  }

  dd h3 {
    font-weight: 800;
    @media print {
      font-weight: 400;
    }
    color: #000;
    padding-left: 10px;
    top: -5px;
    margin: 0;
    position: relative;
  }

  h1 {
    font-weight:200;
    margin-bottom: 50px;
    color: #000;
  }

  .project {
    position: relative;
    /*border-bottom: dotted 1px #97ABFF;*/
    border-left: solid 2px #97ABFF;
  }

  .project div {
    position: relative;
    /*top*/
  }

  .circle {
    position: absolute;
    /*top: 10px;*/
    left: -8px;
    float: left;
    width: 14px;
    height: 14px;
    background-color: #97ABFF;
    border-radius: 15px;
  }

  .project-src {
    position: relative;
    border: 1px solid #08a4e8;
    border-radius: 5px;
    font-size: 14px;
    padding: 1px 5px;
    text-decoration: none;
    margin-bottom: 2px;
  }
</style>
