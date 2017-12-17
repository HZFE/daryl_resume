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
          <dd v-if="segmentfault">
            <svg t="1504190695153" class="icon" style="" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="496" xmlns:xlink="http://www.w3.org/1999/xlink" width="16" height="16"><path d="M169.916413 740.41627c33.172517 30.046317 80.854493 57.014528 126.47246 57.014528 33.172517 0 70.485331-14.514575 70.485331-53.91084 0-43.532469-50.79692-50.78771-107.809401-75.674517-64.269769-27.994588-118.179586-62.193481-118.179586-144.096862 0-106.771769 86.043678-152.378479 192.815447-152.378479 58.052161 0 120.255875 13.483082 164.822906 42.502l0 12.434194-41.464367 81.904405c-29.020964-21.765723-68.420299-36.276205-111.960954-36.276205-38.352493 0-62.193481 15.538905-62.193481 45.604664 0 39.380916 45.616944 47.682999 102.630449 69.449745 78.779228 30.067806 126.461203 63.240323 126.461203 147.198503 0 109.87648-86.034469 157.576875-200.061478 157.576875-72.570829 0-130.62299-19.706831-185.560206-61.164035L126.374734 818.167075 169.916413 740.41627z" p-id="497"></path><path d="M638.40441 890.697995c0-10.514471 2.084475-296.641117 3.128247-395.519102-28.364001 1.043772-57.854663 1.043772-66.23861 1.043772l1.043772-106.241696c8.42488 0 36.83186 0 64.152089 1.043772 0-4.212952-2.084475-91.518367-2.084475-94.668103 0-118.858038 69.409836-163.05361 159.882384-163.05361 38.918381 0 78.877465 6.319939 118.881574 23.151279l0 15.767102-30.53341 84.154655c-16.811898-9.469676-35.749202-14.724353-52.599985-14.724353-29.447682 0-48.38601 14.724353-48.38601 70.473051 0 18.936281 1.083681 74.686003 1.083681 78.899978 31.53625-1.043772 91.518367-1.043772 99.903338-1.043772l-1.043772 106.241696c-8.426927 0-68.367087 0-99.943246-1.043772 2.12643 98.877985 2.12643 385.004631 2.12643 395.519102L638.40441 890.697995z" p-id="498"></path></svg>
            <a :href="segmentfault" target="_blank">{{ segmentfault }}</a>
          </dd>
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
          <dd>学历：{{ education }}</dd>
          <dd>学位：{{ degree }}</dd>
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
                <a v-if="project.src" class="project-src" :href="project.src" target="_blank"><i class="fa fa-link"></i>源代码</a>
                <a v-if="project.demo" :href="project.demo" class="project-src" target="_blank"><i class="fa fa-link"></i>Demo</a>
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
import info from '@/information.json'

export default {
  name: 'hello',
  data () {
    return info
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
