<template>
  <div class="hello">
    <div class="night">
      <div class="shooting_star"></div>
      <div class="shooting_star"></div>
      <div class="shooting_star"></div>
    </div>
    <div class="resume_fixed">
    <Row>
      <Col span="24" class="resume_word">个 人 简 历</Col>
    </Row>
    <div class="resume_bar">
          <div class="bar_column" @click="clickPot('resume_introduce')" id="bar_resume_introduce">
            <Icon type="md-contact" size="24"/>
            <div href="#resume_introduce" title="个人介绍">个人介绍</div>
          </div>
          <div class="bar_column" @click="clickPot('resume_forjob')" id="bar_resume_forjob">
            <Icon type="ios-planet" size="24"/>
            <div href="#resume_forjob" title="求职意向">求职意向</div>
          </div>
          <div class="bar_column" @click="clickPot('resume_skill')" id="bar_resume_skill">
            <Icon type="logo-html5" size="24"/>
            <div href="#resume_skill" title="技能特长">技能特长</div>
          </div>
          <div class="bar_column" @click="clickPot('resume_experience')" id="bar_resume_experience">
            <Icon type="ios-list-box" size="24"/>
            <div href="#resume_experience" title="工作经历">工作经历</div>
          </div>
          <div class="bar_column" @click="clickPot('resume_education')" id="bar_resume_education">
            <Icon type="md-school" size="24"/>
            <div href="#resume_education" title="项目经验">项目经验</div>
          </div>
          <div class="bar_column" @click="clickPot('resume_judge')" id="bar_resume_judge">
            <Icon type="ios-color-palette" size="24"/>
            <div href="#resume_judge" title="自我评价">自我评价</div>
          </div>
      </div>
    </div>
    <div class="whole_content" id="scrollContent">
      <div class="content_box">
        <div id="resume_introduce" class="resume_box">
          <div class="resume_part_title">个人介绍</div>
          <div class="resume_part_value">
            <Row class="resume_part_row">
              <Col span="8">
                <span>姓名：</span>
                <span>杜晴</span>
              </Col>
              <Col span="8">
                <span>性别：</span>
                <span>女</span>
              </Col>
              <Col span="8">
                <span>民族：</span>
                <span>汉族</span>
              </Col>
          </Row>
          <Row class="resume_part_row">
              <Col span="8">
                <span>电话：</span>
                <span>18516580626</span>
              </Col>
              <Col span="8">
                <span>邮箱：</span>
                <span>1310650332@qq.com</span>
              </Col>
              <Col span="8">
                <span>学历：</span>
                <span>本科</span>
              </Col>
          </Row>
          </div>
          <div>

          </div>
        </div>
        <div id="resume_forjob" class="resume_box">
          <div class="resume_part_title">求职意向</div>
          <div class="resume_part_value">
            <Row class="resume_part_row">
              <Col span="8">
                <span>职位：</span>
                <span>web前端开发</span>
              </Col>
              <Col span="8">
                <span>坐标：</span>
                <span>上海</span>
              </Col>
              <Col span="8">
                <span>到岗时间：</span>
                <span>随时</span>
              </Col>
          </Row>
          </div>
        </div>
        <div id="resume_skill" class="resume_box">
          <div class="resume_part_title">技能特长</div>
          <div class="resume_part_value">
            <div class="resume_part_row" v-for="item in skillData">{{item.value}}</div>
          </div>
        </div>
        <div id="resume_experience" class="resume_box">
          <div class="resume_part_title">工作经历</div>
          <div class="resume_part_value">
            <Table :columns="columns1" :data="data1" class="resume_part_table"></Table>
          </div>
        </div>
        <div id="resume_education" class="resume_box">
          <div class="resume_part_title">项目经验</div>
          <div class="resume_part_value">
            <Row class="resume_part_row" v-for="(item,index) in experienceData" :key="index">
              <Col span="24">
                <div class="resume_part_rowCon">{{item.title}}</div>
                <div v-for="val in item.dataList" class="resume_part_rowBox">
                  <div class="resume_part_rowCon">{{val.title}}</div>
                  <div class="resume_part_rowCon_val" v-for="(lala,index) in val.newvalue">{{lala}}</div>
                </div>
              </Col>
          </Row>
          </div>
        </div>
        <div id="resume_judge" class="resume_box">
          <div class="resume_part_title">自我评价</div>
          <div class="resume_part_value">
            <div class="resume_part_row resume_part_rowCon">* 热爱前端开发这份工作，平时除了完成公司的项目开发，也一直关注前端技术的更新，乐于学习和吸收一些新的知识。</div>
            <div class="resume_part_row resume_part_rowCon">* 代码的整洁度很好，能够使用注释等标注，便于与团队成员的合作。能够服从领导安排，抗压能力很强</div>
            <div class="resume_part_row resume_part_rowCon">* 性格开朗，注重团队合作，能够很快的融入团队;自己的学习能力比较强，能够 很快的上手新的框架等。</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      skillData : [
        {"value":"1.精通HTML+CSS,将静态页面高度还原，并且灵活使用css中的动画效果以及HTML5中新特性，优化网页性能"},{
          "value":"2.熟练使用Bootstrap样式完成页面布局，达到页面的响应式效果,精通移动端布局，使用flexible 布局完成适配和百分比布局等"
        },{
          "value":"3.精通JavaScript ,完成页面当中事件的绑定、动画效果、图片预加载等效果"
        },{
          "value":"4.精通jQuery框架，熟练使用jQuery中Ajax完成页面无刷数据请求，熟练使用 jQuery封装动画等，使用jQuery中封装的函数快速开发，缩短开发周期"
        },{
          "value":"5.使用vue+element开发项目"
        },{
          "value":"6.了解微信网页开发，调取接口，获取用户授权完成信息的收集等功能"
        }
      ],  //技能特长数据
      columns1: [
          {
              title: '入职时间',
              key: 'start'
          },
          {
              title: '离职时间',
              key: 'end'
          },
          {
              title: '单位名称',
              key: 'name'
          },
          {
              title: '职位',
              key: 'work'
          }
      ],
      data1: [
          {
              start: '2016.8',
              end: '2017.10',
              name: '上海融云科技有限公司',
              work: 'web前端工程师'
          },
          {
              start: '2017.11',
              end: '至今',
              name: '中软华腾科技服务有限公司',
              work: 'web前端工程师'
          },
      ],
      experienceData :[
        {"title":"一、中国太平后台管理页面(团队开发项目)","dataList":[
        {"title":"项目描述:","value":"中国太平后台后台管理系统一期项目,主要特点是页面简洁,一定要让 页面可复用性强和大量的数据逻辑"},
        {"title":"技术概述:","value":"1. 使用HTML/CSS完成静态页面的展示|2. 布局主要用table和datatables的布局方式|3.使用jQuery完成页面中的点击事件，需要使用Ajax完成数据的 传送以及页 面的跳转等|4.网站的维护和更新等。参与二期系统的升级，负责所有的静态的页面的呈 现，用vue.js来做部分前后端分离"}
        ]},
        {"title":"二、富卫保险核保系统(团队开发项目)","dataList":[
        {"title":"项目描述:","value":"保险核保系统的一期项目，页面简约时尚，逻辑判断较多，页面的复用性强"},
        {"title":"技术概述:","value":"1.用flex布局实现响应式布局，媒体查询适用不同屏幕的样式|2.HTML/CSS完成静态页面，实现一些走马灯效果|3.使用JQ完成事件绑定，字符串拼接来做数据渲染，ajax请求数据，根据保单 号来进行投保人、被保人、受益人之间的数据串联"}
        ]},
        {"title":"三、富卫保险(团队开发项目)","dataList":[
        {"title":"项目描述:","value":"保险核保系统的二期项目、统一工作台和影像系统"},
        {"title":"技术概述:","value":"1.用vue+element实现整体的布局|2.使用axios请求后台接口处理返回数据并把处理后的数据提交给后台|3.修改webpack打包之后可以更改请求后台的地址，便于在不同的环境上发布|4.自定义组件、自定义内部指令(Vue.directive)|5.组件间的数据共享"}
        ]}
      ],
      changeColor : [],   
    }
  },
  created(){
    this.experience();
  },
  methods:{
    experience(){
      for(var i in this.experienceData){
        for(var j in this.experienceData[i].dataList){
          console.log(this.experienceData[i].dataList[j].value.split("|"))
          // this.experienceData[i].dataList[1].value = this.experienceData[i].dataList[1].value.split("|")
          var haha = this.experienceData[i].dataList[j].value.split("|")
          var wala = [];
          for(var k in haha){
            wala.push(haha[k])
            this.$set(this.experienceData[i].dataList[j],"newvalue",wala)
          }
        }
      }
      console.log(this.experienceData)
    },
    clickPot(id){
      var haha = document.getElementById(id);
      var content = document.getElementById("scrollContent");
      var barContent = document.getElementById("bar_"+id);
      content.scrollTop = haha.offsetTop;
      var colorBar = document.getElementsByTagName("div");
      for(var i in colorBar){
        if(colorBar[i].className == "bar_column"){
        colorBar[i].style.color = "orange";
        colorBar[i].style.textShadow = "none";
        }
      }
      barContent.style.color = "#f97b1f";
      barContent.style.textShadow = "2px 2px 5px rgba(255,255,255,1)"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
