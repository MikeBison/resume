<template>
  <div class="leftPart">
    <div class="intro">
      <div>
        <h1 v-text="header.title"></h1>
        <h2 v-text="header.smTitle"></h2>
        <template v-for="work in header.content">
          <info-content :label="work.label" :content="work.content"></info-content>
        </template>
      </div>
      <template v-for="item in lineTitle">
        <div>
          <section>
            <info-block :title="item.titleText" :img-src="item.img"></info-block>
            <template v-for="content in item.content">
              <info-content :label="content.label" :content='content.content'></info-content>
            </template>
          </section>
          <section>
          </section>
        </div>
      </template>
    </div>
    <div class="skill">
      <img :src="photo" alt="photo" class='photo'>
      <section class='connection'>
        <template v-for="connect in getConnect">
          <info-block :hideline="true" :title="connect.titleText" :imgSrc="connect.img" :notBold="connect.notBold"></info-block>
        </template>
      </section>
      <section class='contentBlock'>
        <info-block :title="skill.skillList.title"></info-block>
        <template v-for="skill in skillRange">
          <skill-range :label="skill.label" :val="skill.val" :ifDisable="skill.ifDisable"></skill-range>
        </template>
      </section>
      <section class='contentBlock'>
        <info-block :title="skill.github.title"></info-block>
        <info-content :label="skill.github.github.label" :content="skill.github.github.content" :isHref="true"></info-content>
        <info-content :label="skill.github.blog.label" :content="skill.github.blog.content" :isHref="true"></info-content>
      </section>
      <section class='contentBlock'>
        <info-block :title="skill.hobby.title"></info-block>
        <info-content :content="skill.hobby.content"></info-content>
      </section>
      <section class='contentBlock'>
        <info-block :title="skill.character.title"></info-block>
        <info-content :content="skill.character.content"></info-content>
      </section>
    </div>
  </div>
</template>

<script>
import infoBlock from './info.vue';
import infoContent from './infoContent.vue';
import skillRange from './skillRange.vue'
import img from './assets/logo.png';
import photo from './assets/photo.jpg'
import edu from './assets/edu.png'
import skill from './assets/skill.png'
import proj from './assets/proj.png'
import proj_1 from './assets/proj_1.png'
import loc from './assets/loc.png'
import phone from './assets/phone.png'
import email from './assets/email.png'
import home from './assets/home.png'
import birthday from './assets/birthday.png'

let data = {
  title : "前端工程师",
  msg : '2010.9-2014.7 太原理工大学现代科技 热能与动力工程',
  img,
  photo,
  skill:{
    skillList:{
      title:"技能列表"
    },
    github:{
      title:"github与blog",
      github:{
        label: "github:",
        content: "github.com/MikeBison"
      },
      blog:{
        label: "blog:",
        content: "mikebison.github.io"
      }
    },
    hobby:{
      title:"兴趣爱好",
      content:"前端技术,电子设备,摇滚乐,游戏"
    },
    character: {
      title:"性格",
      content:"可以站在他人的角度考虑问题,乐于助人,性格温和,很少与人争执"
    }
  },
  skillRange:[{
    label:"html",
    val: 80,
    ifDisable: "disabled"
  },{
    label:"css",
    val: 90,
    ifDisable: "disabled"
  },{
    label:"javascript",
    val: 85,
    ifDisable: "disabled"
  },{
    label:"sass",
    val: 60,
    ifDisable: "disabled"
  }],
  getConnect:[
    {
      img:loc,
      titleText: "上海市浦东新区",
      notBold: true,
    },
    {
      img:phone,
      titleText: "1861658193",
      notBold: true,
    },
    {
      img:email,
      titleText: "jingxing8193@gmail.com",
      notBold: true,
    },
    {
      img:home,
      titleText: "山西省太原市",
      notBold: true,
    },
    {
      img:birthday,
      titleText: "1991.01.14",
      notBold: true,
    },
  ],
  header: {
    title:"个人简历",
    smTitle:"Web前端工程师",
    content:[
      {
        label:"姓名:",
        content:"荆鑫"
      },
      {
        label:"工作经历",
        content:""
      },
      {
        label:"",
        content:"2014.7-2015.7 国电清新股份有限公司"
      },
      {
        label:"",
        content:"2016.1-至今 波汇科技股份有限公司"
      }
    ]
  },
  lineTitle: [
    {
      titleText:"教育经历",
      img:edu,
      content:[
      {
        label:"太原理工大学现代科技 本科",
        content:" 2010-2014"
      }
      ]
    },
    {
      titleText:"主要技能",
      img:skill,
      content:[
      {
        label:"",
        content:"能够熟练前端三剑客html,css,javascript.工作中主要使用jquery工具库,熟悉vue.js的使用,能够使用ajax与后台进行数据交换,熟悉webpack,了解python语法,使用gobee搭建过服务器,用express写过简单的后台demo,能够使用sass,熟悉小程序的编写,实践过移动端微信宣传页面的制作,能够独立完成前端项目."
      }
      ]
    },
    {
      titleText:"项目经历",
      img:proj,
      content:[
      {
        label:"MaxView监控平台:",
        content:"我在这个项目中主要负责新功能的添加和老功能的维护工作,这是一个部署在内网的应用于电力,海缆,隧道的监控平台,用来监控各种环境下的温度,湿度,风力,地理位置以及实时视频监控,属于物联网,大数据范畴."
      },
      {
        label:"MaxPower资源管理系统:",
        content:"该项目是由我独立完成前端部分,目前应用在杭州电力大有实业丰潭路分公司,该系统主要提供了该公司员工工作分配,记录,资料整理功能."
      },
      {
        label:"诗贝艾尔微信营销页面:",
        content:"该项目是与朋友俩个人接的兼职项目，是诗贝艾尔公司用于新春宣传的营销抽奖页面，最终由于接头问题项目没有上线。源码存储在码云。"
      }
      ]
    },
    {
      titleText:"项目心得",
      img:proj_1,
      label:"",
      content:[
      {
        label:"",
        content:"在波汇科技就职这一年,养成了独立解决问题的能力,同时培养出了写代码之前先深思熟虑的习惯,争取用最简洁易懂的方式写出效率最高的代码,在MaxView平台的维护过程中,我觉得使用jquery和zepto这类工具库写出的代码很容易显得没有章法,造成维护困难,所以针对公司的项目自己封装了一些组件,解决了公司大型项目代码难懂难维护的问题,新来的同事可以用更少的时间上手(详见MaxPower源码)."
      },
      {
        label:"",
        content:"一直没有放弃新技术的学习,对面现今流行的框架都做过了解.入职波汇前曾学过angular1,下班利用空余时间学习了node.js,python,sass,zepto,以及移动端css布局,曾用node.js的express框架写过简单的后台demo,所以自认为对后台也有一定的了解,公司项目使用c#写的后台,也能简单的查找后台问题原因."},
      {
        label:"",
        content:"由于公司只有自己一个前端,没有引到导致自己学的很乱,很杂.希望能够找到一个前端团队,完善自己的职业规划."}
      ]
    },
  ],
}
export default {
  name: 'app',
  data () {
    return data
  },
  components: {
    infoBlock,infoContent,skillRange
  },
  methods: {
    popAlert: function(){
      alert(this.msg);
    }
  },
  computed: {
    msgArr (){
      return this.msg.split(" ");
    }
  }
}
</script>

<style lang='less'>
.leftPart{
  overflow: hidden;
}
.intro{
  h1{
    font-size: 48px;
  }
  h2{
    font-size: 36px;
  }
  h1,h2{
    color: #096189;
    text-indent: 10px;
    margin-bottom: 10px;
  }
  width: 61.8%;
  padding: 40px 20px 40px 40px;
  float: left;
}
.skill{
  .photo{
    height: 280px;
    margin-left: 77px;
    margin-bottom: 20px;
  }
  .info-block{
    margin-bottom: 20px;
    img{
      width: 30px;
      height: 30px;
    }
    h5{
      line-height: 30px;
    }
  }
  .info-block:first-child{
    margin-top: 10px;
  }
  width: 38.2%;
  float: left;
  height: 1280px;
  background-color: #ebecee;
  padding: 40px 40px 40px 20px;
}
.contentBlock{
  .skillRange,.info-content{
    margin-left: 20px;
  }
  margin-bottom: 40px
}
</style>
