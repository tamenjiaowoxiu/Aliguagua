<template>
  <div  class="main-1">
    <div class="header-1">
        <header class="header">
          <div class="container">
          <h1>
            <router-link to="/main">
<!--              后面版本再更改图标LOGO3-->
              <img title="www.aliguagua.com" src="../img/Aliguagua.png" width="152.75" height="77.25">
            </router-link>
          </h1>
          <ul class="nav">
            <li class="item">
              <router-link class="top-meta" to="/main" >首页</router-link>
            </li>
            <li class="item">
              <router-link class="top-meta" to="/login">话题</router-link>
              <router-view></router-view>
            </li>
            <li class="item">
              <router-link class="top-meta" to="/content">动态</router-link>
            </li>
          </ul>
            <div class="item search">
              <el-autocomplete
                v-model="state"
                :fetch-suggestions="querySearchAsync"
                placeholder="请输入内容"
                @select="handleSelect"
              ></el-autocomplete>
              <el-button type="primary" icon="el-icon-search">搜索</el-button>
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
                    <router-link to="/user/:name">
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
    </div>
    <div class="story">
      <div class="Top-story">
        <div>
          <div style="opacity: 1">
            <div class="top">
              <div class="top1">
<!--                 <router-link to="/optest">-->
                   <img src="../img/微信图片_20221026233704(1).png" class="photo">
<!--                 </router-link>-->
              </div>
<!--              <div class="top2"></div>-->
            </div>
          </div>
        </div>
      </div>
      <div style="height: 180px"></div>
      <div class="Main-story">
        <div class="Main-story1">
          <div class="box-left" style="box-shadow: rgba(0,0,0,0.12) 0px 2px 4px,rgba(0,0,0,0.04) 0px 0px 6px">
            <div class="box-left1">
              <el-tabs v-model="activeName" type="card" @tab-click="handleClick">
                <el-tab-pane label="推荐" name="first">
                  <div class role="list" v-infinite-scroll="load">
                    <div class="list0">
                      <div class="list1">
                        <h2 class="h2title">
                          <span>
                          为什么蜜雪冰城可以这么便宜？
                        </span>
                        </h2>
                        <div class="list2">
                          <span>
<!--                            <el-skeleton :rows="6" />-->
                            <div class="list2-2">
                          匿名：首先他有一套完整的产业链,蜜雪冰城的饮品在大众的印象中一直都是便宜、价格实惠，但是有不少人也非常好奇为什么蜜雪冰城那么便宜？并不是所有...
                            </div>
                          </span>
                          <div class="action">
                            <span>
                              <el-badge :value="12" class="item">
                                <el-button size="small">点赞</el-button>
                              </el-badge>
                              <el-badge :value="3" class="item">
                                <el-button size="small">回复</el-button>
                              </el-badge>
                              <el-badge :value="1" class="item" type="primary">
                                <el-button size="small">评论</el-button>
                              </el-badge>
<!--                              <el-button type="primary" round>主要按钮</el-button>-->
                            </span>
                          </div>
                        </div>

                      </div>
                    </div>
                    <div class="list0">
<!--                      <el-card class="box-card">-->
                      <h2 class="h2title" >
                        为什么原神这么火？
                      </h2>
                      小鸡脚：原神是米哈游旗下的一款开放世界游戏,《原神》自打公布消息以来就一直争议不断，一直站在风口浪尖上，玩家们自然分成了两派，互相对立，不断...
<!--                      </el-card>-->
                    </div>
                  </div>

                </el-tab-pane>
                <el-tab-pane label="热榜" name="second">该功能还在开发中。。。。</el-tab-pane>
                <el-tab-pane label="关注" name="third">该功能还在开发中。。。。</el-tab-pane>
              </el-tabs>
            </div>
          </div>
        </div>
        <div class="Main-story2">
          <el-card class="box-card">
            <h1>广告联系邱先生：155210xxxx</h1>
            <span>
              <router-link to="/blog">
                <el-button type="primary" icon="el-icon-edit" circle></el-button>
              </router-link>
            </span>
            <router-link to="/advertisement"><h2>贰货 全国4亿年轻人都在用的二手平台交易网站！！</h2></router-link>
            <router-link to="/optest"><h2>原神 点击领取2w原石！！！</h2></router-link>
            <router-link to="/header"><h2>这是测试</h2></router-link>
          </el-card>
        </div>

      </div>

      <el-container>
<!--        <el-aside width="200px"></el-aside>-->
        <el-main>

        </el-main>
        <el-container>



        </el-container>
      </el-container>
    </div>
<!--  <span>{{name}}</span>-->
</div>
</template>

<script>
export default {
  // props:['name'],
  name: "Main",
  data() {
    // blogs:[
    //   {title: '为什么原神这么火'},
    //   {blog: '因为'}
    // ];
    return {
      activeName: 'first',
      restaurants: [],
      state: '',
      timeout:  null
    };
  },
  methods: {
    load(){
      this.count += 2;
    },

    loadAll() {
      return [
        { "value": "原神为什么这么火", "address": "长宁区新渔路144号" },
        { "value": "抽纳西妲还是雷神", "address": "上海市长宁区淞虹路661号" },
        { "value": "新旺角茶餐厅", "address": "上海市普陀区真北路988号创邑金沙谷6号楼113" },
        { "value": "泷千家(天山西路店)", "address": "天山西路438号" },
        { "value": "胖仙女纸杯蛋糕（上海凌空店）", "address": "上海市长宁区金钟路968号1幢18号楼一层商铺18-101" },
        { "value": "贡茶", "address": "上海市长宁区金钟路633号" },
        { "value": "豪大大香鸡排超级奶爸", "address": "上海市嘉定区曹安公路曹安路1685号" },
        { "value": "茶芝兰（奶茶，手抓饼）", "address": "上海市普陀区同普路1435号" },
        { "value": "十二泷町", "address": "上海市北翟路1444弄81号B幢-107" },
        { "value": "星移浓缩咖啡", "address": "上海市嘉定区新郁路817号" },
        { "value": "阿姨奶茶/豪大大", "address": "嘉定区曹安路1611号" },
        { "value": "新麦甜四季甜品炸鸡", "address": "嘉定区曹安公路2383弄55号" },
        { "value": "Monica摩托主题咖啡店", "address": "嘉定区江桥镇曹安公路2409号1F，2383弄62号1F" },
        { "value": "浮生若茶（凌空soho店）", "address": "上海长宁区金钟路968号9号楼地下一层" },
        { "value": "NONO JUICE  鲜榨果汁", "address": "上海市长宁区天山西路119号" },
        { "value": "CoCo都可(北新泾店）", "address": "上海市长宁区仙霞西路" },
        { "value": "南拳妈妈龙虾盖浇饭", "address": "普陀区金沙江路1699号鑫乐惠美食广场A13" }
      ];
    },
    querySearchAsync(queryString, cb) {
      var restaurants = this.restaurants;
      var results = queryString ? restaurants.filter(this.createStateFilter(queryString)) : restaurants;

      clearTimeout(this.timeout);
      this.timeout = setTimeout(() => {
        cb(results);
      }, 3000 * Math.random());
    },
    createStateFilter(queryString) {
      return (state) => {
        return (state.value.toLowerCase().indexOf(queryString.toLowerCase()) === 0);
      };
    },
    handleSelect(item) {
      console.log(item);
    },
    handleClick(tab, event) {
      console.log(tab, event);
    }
  },
  mounted() {
    this.restaurants = this.loadAll();
  }
}
</script>
<style>
.badge-item{
  margin-top: -5px;
  margin-right: 36px;
}
.profile-a{
  margin-left: 6px;
}
.proper-c{
  box-sizing: border-box;
  margin: 0;
  min-width: 0;
  font-size: 12px;
  line-height: 14px;
  color: #8cc4fd !important;
  opacity: 0.75;
  -webkit-transition-property: color;
  transition-property: color;
  -webkit-transition-duration: 0.25s;
  transition-duration: 0.25s;
  -webkit-transition-timing-function: ease-in;
  transition-timing-function: ease-in;
}
.proper i{
  display: block;
  font-size: 27px;
  cursor: pointer;
  margin-bottom: 1px;
  color: #8cc4fd;
  transition: color .15s linear;
}
.proper{
  position: relative;
  display: inline-block;
}
.header{
  height: 80px;
  background-color: #fff;
  color: #fff;
  top: 0;
  left: 0;
  width: 100%;
  line-height: 80px;
  z-index: 100;
  position: relative;
}
.header .nav{
  float: left;
  height: 100%;
  line-height: 80px;
  background: transparent;
  padding: 0;
  margin: 0;
}
#menu1 {
  display: inline-block;
  padding-top: 50px;
}
/*img {*/

/*  position: absolute;*/

/*  left: 50px;*/

/*  top: 55px*/

/*}*/
.header .container{
  height: 100%;
  box-sizing: border-box;
  border-bottom: 1px solid #dcdfe6;
}
.header .item search{
  cursor: default;
}
.header h1{
  margin: 0;
  float: left;
  font-size: 32px;
  font-weight: 400;
}
h1{
  display: block;
  font-size: 2em;
  margin-block-start: 0.67em;
  margin-block-end: 0.67em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
  font-weight: bold;
}
.header-1{
  /*background-color: antiquewhite;*/
  position: fixed;
  width: 100%;
  left: 0;
  top: 0;
  z-index: 1500;
}
.header .item{
  margin: 0;
  float: left;
  list-style: none;
  position: relative;
  cursor: pointer;
  padding-left: 10px;
  padding-right: 9px;
}
.header .top-meta{
  transition-timing-function: ease-in;
}

.header .item a{
  text-decoration: none;
  color: #1989fa;
  opacity: .5;
  display: block;
  padding: 0 24px;
}
.img{
  vertical-align:top;
}
.header .nav-item a. router-link-active, .header .nav-item a:hover {
  opacity: 1;
}
/*.header .item a.router-link-exact-active router-link-active{*/
/*  opacity: 1;*/
/*}*/

li{
  display: list-item;
  text-align: -webkit-match-parent;
}
body,html{
  margin: 0;
  padding: 0;
  height: 100%;
  font-family: Helvetica Neue,Helvetica,PingFang SC,Hiragino Sans GB,Microsoft YaHei,SimSun,sans-serif;
  font-weight: 400;
  -webkit-font-smoothing: antialiased;
  -webkit-tap-highlight-color: transparent;
}
body. main, html. main {
  overflow: hidden;
}
.box-left{
  -webkit-box-shadow: 0 1px 3px rgb(18 18 18 / 10%);
  box-shadow: 0 1px 3px rgb(18 18 18 / 10%);
}
div{
  display: block;
}
#menu{
  position: relative;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: start;
  -ms-flex-align: start;
  align-items: flex-start;
  width: 1000px;
  padding: 0 16px;
  margin: 10px auto;
}
.top1{
  box-sizing: border-box;
  margin: 0;
  min-width: 0;
  height: 200px;
  background-color: #af1f0c;
}
.photo{
  box-sizing: border-box;
  margin: 0;
  min-width: 0;
  max-width: 100%;
  height: auto;
  max-width: 1366px;
  margin: 0 auto;
  display: block;
  object-fit: cover;
  width: 100%;
  height: 100%;
}
.top{
  margin-top: 80px;
  box-sizing: border-box;
  /*margin: 0;*/
  min-width: 0;
  width: 100%;
  position: absolute;
  z-index: -1;
}
.top2{
  box-sizing: border-box;
  margin: 0;
  min-width: 0;
  height: 48px;
  background-color: #FF7550;
}
.Main-story{
  position: relative;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: start;
  -ms-flex-align: start;
  align-items: flex-start;
  width: 1000px;
  padding: 81px 16px;
  margin: -20px auto;
}
.Main-story1{
  -ms-flex-negative: 0;
  flex-shrink: 0;
  margin-right: 10px;
  margin-bottom: 0;
  width: 630px;
}
.box-left1{
  margin-bottom: 10px;
  background: #fff;
  overflow: hidden;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 3px rgb(18 18 18 / 10%);
  box-shadow: 0 1px 3px rgb(18 18 18 / 10%);
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}
/*.story{*/
/*  background-color: #909399;*/
/*  background-position: bottom;*/
/*}*/
.list0{
  margin-bottom: 0;
  -webkit-box-shadow: none;
  box-shadow: none;
  border-bottom: 1px solid #f0f2f7;
  padding: 20px;
}
.h2title{
  line-height: 1.6;
}
.el-tabs__header is-top {
  padding: 0;
  position: relative;
  margin: 0 0 -14px;
}
.list2{
  line-height: 1.67;
}
.list2-2{
  margin-top: 9px;
  margin-bottom: -4px;
  overflow: hidden;
  max-height: 100px;
}

.css-1{
  box-sizing: border-box;
  margin: 0;
  min-width: 0;
  max-width: 100%;
  height: auto;
  background-color: #FFFFFF;
  width: 43px;
  height: 43px;
  border-radius: 2px;
}
.avatar{
  background: #fff;
  border-radius: 2px;
}
.profile-c{
  display: inline-block;
  padding: 0 16px;
  font-size: 21px;
  line-height: 43px;
  text-align: center;
  cursor: pointer;
  background: none;
  border: 0px solid;
  border-radius: 3px;
}
.profile-d{
  vertical-align: top;
}
.Main-story2{
  max-width: 296px;
  /*-webkit-align-self: normal;*/
  -ms-flex-item-align: normal;
  align-self: normal;
}
.text {
  font-size: 14px;
}


.box-card {
/*黄金分割率*/
  width: 394px;
}
.action{
  clear: both;
  margin: 23px -4px -2px;
  background: white;
}
.item{
  margin-top: 10px;
  margin-right: 40px;
}
.userinfo{
  -ms-flex-negative: 0;
  flex-shrink: 0;
  -webkit-box-pack: end;
  -ms-flex-pack: end;
  justify-content: flex-end;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  margin-left: 10px;
  width: 380px;
}

/*第二版顶层及背景图片设置*/
/*照片为未命名设计*/
/*.top1{*/
/*  box-sizing: border-box;*/
/*  margin: 0;*/
/*  min-width: 0;*/
/*  height: 263px;*/
/*  background-color: #af1f0c;*/
/*}*/
/*.photo{*/
/*  box-sizing: border-box;*/
/*  margin: 0;*/
/*  min-width: 0;*/
/*  max-width: 100%;*/
/*  height: auto;*/
/*  max-width: 1366px;*/
/*  margin: 0 auto;*/
/*  display: block;*/
/*  object-fit: cover;*/
/*  width: 71%;*/
/*  height: 100%;*/
/*}*/
/*.top{*/
/*  margin-top: 53px;*/
/*  box-sizing: border-box;*/
/*  !*margin: 0;*!*/
/*  min-width: 0;*/
/*  width: 100%;*/
/*  position: absolute;*/
/*  z-index: -1;*/
/*}*/
</style>


