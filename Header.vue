<template>
    <div>
      <header role="banner" class="top-header css-1001">
        <div class="top-header-1 css-1002">
            <router-link to="/main">
              <img title="www.aliguagua.com" src="../img/Aliguagua.png" width="152.75" height="77.25">
            </router-link>
          <ul role="tablist" class="top-header-2 css-2000" >
            <li role="tab" class="tab-1 css-2001">
              <router-link class="tab-link css-3001 tab-link-1 is-active" to="/main">首页</router-link>
            </li>
            <li role="tab" class="tab-1 css-2001">
              <router-link class="tab-link css-3001 tab-link-1 is-active" to="/login">话题</router-link>
            </li>
            <li role="tab" class="tab-1 css-2001">
              <router-link class="tab-link css-3001 tab-link-1 is-active" to="/login">动态</router-link>
            </li>
            <li role="tab" class="tab-1 css-2001">
              <router-link class="tab-link css-3001 tab-link-1 is-active" to="/login">公告</router-link>
            </li>
          </ul>
          <div class="search">
            <el-autocomplete
              v-model="state"
              :fetch-suggestions="querySearchAsync"
              placeholder="请输入内容"
              @select="handleSelect"
            ></el-autocomplete>
            <el-button type="primary" icon="el-icon-search"class="css-4000">搜索</el-button>
          </div>


          <div class="userinfo">
            <div class="proper">
              <el-badge value="12" class="badge-item">
                <i class="el-icon-chat-dot-square">
                  <span style="display: inline-flex; align-items: center;">
                  </span>
                  <div class="proper-c">通知</div>
                </i>
              </el-badge>
            </div>
            <div class="proper">
              <el-badge value="20" class="badge-item">
                <i class="el-icon-user">
                  <span style="display: inline-flex;align-items: center;"></span>
                  <div class="proper-c">私信</div>
                </i>
              </el-badge>
            </div>
            <div class="profile">
              <div class="profile-a">
                <button id="profile-b" aria-haspopup="true" aria-expanded="false" aria-owns="content" type="button"
                        class="profile-c">
                  <router-link to="/login">
                    <img class="profile-d css-1 avatar" src="../img/微信图片_20221103002722.jpg">
                  </router-link>
                </button>
              </div>
              <!--                <span>-->
              <!--                    <router-link to="/login">个人中心</router-link>-->
              <!--                  </span>-->
              <!--              <span class="el-avatar el-avatar&#45;&#45;square" style="hight:50px;width: 50px;line-height: 50px;">-->
              <!--                <img class="img" src="../img/1.jpg">-->
              <!--              </span>-->
            </div>
          </div>
        </div>
      </header>
      <div class="main-story">
        <el-card class="box-card" style="width: 630px;margin: 0px 20px 24px;padding: 18px 20px;">
          <div slot="header" class="clearfix">
            <span class="font">迪士尼在逃公主</span>
            <div class="user-inner">
              <div class="user-inner1">
                <img class="photo1 user-inner2 inner" width="160" src="../img/微信图片_20221103002722.jpg">
              </div>
            </div>
<!--            <span></span>-->
            <el-button style="float: right; padding: 3px 0" type="text">编辑个人资料</el-button>
          </div>
          <el-tabs v-model="activeName" @tab-click="handleClick" class="el-card-body">
            <el-tab-pane label="动态" name="first">
              <div v-for="o in 4" :key="o" class="text item">
                {{'列表内容 ' + o }}
              </div>
            </el-tab-pane>
            <el-tab-pane label="帖子" name="second">
              <div v-for="o in 4" :key="o" class="text item">
                {{'列表内容 ' + o }}
              </div>
            </el-tab-pane>
            <el-tab-pane label="关注" name="third">
              <div v-for="o in 4" :key="o" class="text item">
                {{'列表内容 ' + o }}
              </div>
            </el-tab-pane>
            <el-tab-pane label="浏览记录" name="four">
              <div v-for="o in 4" :key="o" class="text item">
                {{'列表内容 ' + o }}
              </div>
              <div @click="getData">获取数据</div>
            </el-tab-pane>
          </el-tabs>

        </el-card>
      </div>
<!--      <div class="story">-->
<!--        <div class="Top-story">-->
<!--          <div>-->
<!--            <div style="opacity: 1">-->
<!--              <div class="top">-->
<!--                <div class="top1">-->
<!--                  &lt;!&ndash;                 <router-link to="/optest">&ndash;&gt;-->
<!--                  <img src="../img/未命名的设计 - 副本.png" class="photo">-->
<!--                  &lt;!&ndash;                 </router-link>&ndash;&gt;-->
<!--                </div>-->
<!--                &lt;!&ndash;              <div class="top2"></div>&ndash;&gt;-->
<!--              </div>-->
<!--            </div>-->
<!--          </div>-->
<!--        </div>-->
<!--        <div style="height: 180px"></div>-->
<!--        <div class="Main-story">-->
<!--          <div class="Main-story1">-->
<!--            <div class="box-left" style="box-shadow: rgba(0,0,0,0.12) 0px 2px 4px,rgba(0,0,0,0.04) 0px 0px 6px">-->
<!--              <div class="box-left1">-->
<!--                <el-tabs v-model="activeName" type="card" @tab-click="handleClick">-->
<!--                  <el-tab-pane label="推荐" name="first">-->
<!--                    <div class role="list" v-infinite-scroll="load">-->
<!--                      <div class="list0">-->
<!--                        <div class="list1">-->
<!--                          <h2 class="h2title">-->
<!--                          <span>-->
<!--                          为什么蜜雪冰城可以这么便宜？-->
<!--                        </span>-->
<!--                          </h2>-->
<!--                          <div class="list2">-->
<!--                          <span>-->
<!--                            <div class="list2-2">-->
<!--                          匿名：首先他有一套完整的产业链,蜜雪冰城的饮品在大众的印象中一直都是便宜、价格实惠，但是有不少人也非常好奇为什么蜜雪冰城那么便宜？并不是所有...-->
<!--                            </div>-->
<!--                          </span>-->
<!--                            <div class="action">-->
<!--                            <span>-->
<!--                              <el-badge :value="12" class="item">-->
<!--                                <el-button size="small">点赞</el-button>-->
<!--                              </el-badge>-->
<!--                              <el-badge :value="3" class="item">-->
<!--                                <el-button size="small">回复</el-button>-->
<!--                              </el-badge>-->
<!--                              <el-badge :value="1" class="item" type="primary">-->
<!--                                <el-button size="small">评论</el-button>-->
<!--                              </el-badge>-->
<!--                              &lt;!&ndash;                              <el-button type="primary" round>主要按钮</el-button>&ndash;&gt;-->
<!--                            </span>-->
<!--                            </div>-->
<!--                          </div>-->

<!--                        </div>-->
<!--                      </div>-->
<!--                      <div class="list0">-->
<!--                        &lt;!&ndash;                      <el-card class="box-card">&ndash;&gt;-->
<!--                        <h2 class="h2title">-->
<!--                          为什么原神这么火？-->
<!--                        </h2>-->
<!--                        小鸡脚：原神是米哈游旗下的一款开放世界游戏,《原神》自打公布消息以来就一直争议不断，一直站在风口浪尖上，玩家们自然分成了两派，互相对立，不断...-->
<!--                        &lt;!&ndash;                      </el-card>&ndash;&gt;-->
<!--                      </div>-->
<!--                    </div>-->

<!--                  </el-tab-pane>-->
<!--                  <el-tab-pane label="热榜" name="second">热榜</el-tab-pane>-->
<!--                  <el-tab-pane label="关注" name="third">关注</el-tab-pane>-->
<!--                </el-tabs>-->
<!--              </div>-->
<!--            </div>-->
<!--          </div>-->
<!--          <div class="Main-story2">-->
<!--            <el-card class="box-card">-->
<!--              <h1>广告联系邱先生：155210xxxx</h1>-->
<!--              <router-link to="/advertisement"><h2>贰货 全国4亿年轻人都在用的二手平台交易网站！！</h2></router-link>-->
<!--              <router-link to="/optest"><h2>原神 点击领取2w原石！！！</h2></router-link>-->
<!--              <router-link to="/header"><h2>这是测试</h2></router-link>-->
<!--            </el-card>-->
<!--          </div>-->

<!--        </div>-->
<!--    </div>-->
    </div>
</template>

<script>
export default {
  name: "Header",
  methods :{
    getData() {
      this.$axios.get("http://127.0.0.1:4523/m1/1905009-0-default/user/1/follower")
    }
  }
}

</script>

<style scoped>
.el-card-body{
  padding: 13px;
  margin-top: -57px;
}
.font{
  position: absolute;
  width: 98px;
  height: 22px;
  top: 195px;
  left: 419px;
  font-family: Noto Sans SC;
  font-size: 14px;
  font-weight: 700;
  line-height: 22px;
  letter-spacing: 0px;
  text-align: left;
}
.photo1{
  position: absolute;
  top: 108px;
  left: 228px;
  box-sizing: border-box;

  /*background: url(微信图片_20221103002722);*/
  border: 1px solid rgb(0, 0, 0);
  box-shadow: 4px 4px 4px rgba(0, 0, 0, 0.25);;
}
.main-story{
  margin: 97px 158px;
  padding: 80px 16px;
}
.box-card{
  width: 569px;
}
.text {
  font-size: 14px;
}

.item {
  margin-bottom: 18px;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}
.clearfix:after {
  clear: both
}

.box-card {
  width: 480px;
}
body, button, p, pre{
  margin: 0;
}
html{
  scroll-padding-top: calc(52px + 2em);
  scroll-padding-bottom: 56px;
}
body{
  font-family: -apple-system,BlinkMacSystemFont,Helvetica Neue,PingFang SC,Microsoft YaHei,Source Han Sans SC,Noto Sans CJK SC,WenQuanYi Micro Hei,sans-serif;
  font-size: 15px;
  color: #121212;
}
body{
  -webkit-tap-highlight-color: rgba(18,18,18,0);
}
body{

}
.css-4000{
  margin-left: 27px;
}
.badge-item{
  margin-top: 10px;
}
.search{
  box-sizing: border-box;
  margin: 0;
  /*margin-left: -247px;*/
  min-width: 0;
  -webkit-flex: 1;
  -ms-flex: 1;
  flex: 1;
  -webkit-box-pack: center;
  -webkit-justify-content: center;
  -ms-flex-pack: center;
  justify-content: center;
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
}
.css-1001{
  background-color: #FFFFFF;
  -webkit-transition-property: background-color,box-shadow;
  transition-property: background-color,box-shadow;
  -webkit-transition-duration: 0.25s;
  transition-duration: 0.25s;
  -webkit-transition-timing-function: ease-in;
  transition-timing-function: ease-in;
}
.top-header{
  top:0;
  background-clip: content-box;
  position: fixed;
  width: 100%;
  z-index: 100;
  min-width: 1000px;
  overflow: hidden;
  background: #fff;
  -webkit-box-shadow: 0 1px 3px rgb(18 18 18 / 10%);
  box-shadow: 0 1px 3px rgb(18 18 18 / 10%);
}

.top-header-1{
  position: relative;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  width: 1000px;
  height: 52px;
  padding: 0 16px;
  margin: 0 auto;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-transition: -webkit-transform .3s;
  transition: -webkit-transform .3s;
  transition: transform .3s;
  transition: transform .3s,-webkit-transform .3s;
}
.css-1002{
  width: auto;
  max-width: 1156px;
  min-width: 1000px;
  padding-left: 16px;
  padding-right: 100px;
}

.top-header-2{
  border-bottom: none;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-negative: 0;
  flex-shrink: 0;
  margin: 0 16px;
}

.css-2000{
  margin-left: -17px;
  margin-right: 15px;
}

.tab-1{
  padding: 0 14px;
  display: inline-block;
}
.css-2001{
  padding-left: 15px;
  padding-right: 15px;
}

.css-3001 .tab-link-1 .is-active{
  color: #121212;
}
.css-3001 .is-active:after{
  background-color: #056DE8 !important;
}
a:hover,a:active{
  color: #151313;
}
/*a:link,a:visited{*/
/*  color: #151313;*/
/*  font-size: 13px;*/
/*  text-decoration: none;*/
/*}*/
.tab-link-1.is-active:after{
  position: absolute;
  right: 0;
  bottom: -1px;
  left: 0;
  height: 3px;
  background: #056de8;
  content: "";
}
/*@media screen and (min-width: 320px) and (max-width: 1156px){*/

/*  .site-bg-dl {*/
/*    position: fixed;*/
/*    height: 100%;*/
/*    width: 100%;*/
/*    z-index: 0;*/
/*    !*background-image: url(bjxzfwzx/images/bj1.png);*!*/
/*    background-size: cover;*/
/*    background-repeat: no-repeat;*/
/*    background-attachment: fixed;*/
/*    background-size:100% 100%;*/
/*    -moz-background-size:100% 100%;*/
/*  }*/
/*}*/
.css-3001{
  /*color: undefined !important;*/
  -webkit-transition-property: color;
  transition-property: color;
  -webkit-transition-duration: 0.25s;
  transition-duration: 0.25s;
  -webkit-transition-timing-function: ease-in;
  transition-timing-function: ease-in;
}

.css-3001.is-active:hover{
  opacity: 1;
}
.tab-link-1.is-active{
  font-weight: 600;
  font-synthesis: style;
}
.tab-link-1{
  position: relative;
  display: inline-block;
  padding: 14px 0;
  font-size: 16px;
  line-height: 22px;
  color: #121212;
  text-align: center;
}
a{
  text-decoration: none;
}
.tab-link .is-active{
  color: #444;
}
.tab-link{
  color: #9da5b6;
}
</style>
