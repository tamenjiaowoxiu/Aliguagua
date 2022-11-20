<template>
  <div>
    <h1>欢迎来到博客</h1>
    <div class="Main-story">
      <div class="Main-story1">
        <div class="box-left" style="box-shadow: rgba(0,0,0,0.12) 0px 2px 4px,rgba(0,0,0,0.04) 0px 0px 6px">
          <div class="box-left1">
            <label class="Input-title Input-title1 Input-title2">
              <textarea rows="1" class="Input Input1" placeholder="标题" style="height: 45px"></textarea>
            </label>
            <div class="line1"></div>
            <div class="Input-edit">
<!--              <label class="Input-edit1 css-edit ">-->
<!--                <textarea rows="1" class="Input-1 Input-2" placeholder="正文" style="height: 45px"></textarea>-->
<!--              </label>-->
              <div class="css-edit" contenteditable="true">正文</div>
              <div class="Input-edit1">
<!--                <input multiple type="file" accept="image/webp,image/jpg,image/jpeg,image/png,image/gif" style="display: none;">-->
              </div>
            </div>
            <div class="line1"></div>
            <span class="button">
               <el-button type="success" icon="el-icon-check" circle></el-button>
              <el-button type="danger" icon="el-icon-delete" style="position: relative;left: 40px" circle></el-button>
            </span>
          </div>
        </div>
      </div>
      <div class="Main-story2">
        <el-card class="box-card" style="width: 327px">
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
  </div>


</template>

<script>
export default {
  name: "Blog"
}
</script>

<style scoped>
.button{
  position: relative;
  left: 568px;
}
.Input-edit1{
  outline: none;
  user-select: text;
  white-space: pre-wrap;
  overflow-wrap: break-word;
}
.css-edit{
  color: #303133;
  /*width: 400px;*/

  min-height: 60px;

line-height: 30px;

max-height: 300px;

_height: 60px;

  margin: 0 auto;

padding: 10px;

outline: 0;

/*border: 1px solid #a0b3d6;*/

border-radius: 4px;

font-size: 16px;

  word-wrap: break-word;

  overflow-x: hidden;

  overflow-y: auto;

  _overflow-y: visible;

  -webkit-user-modify: read-write-plaintext-only;
}
.Input-edit{
  margin: 30px 0;
  line-height: 1.6;
  font-size: 16px;
  min-height: 300px;
  padding: 0;
  cursor: text;
  /*padding: 6px 12px;*/
}
.line1{
  box-sizing: border-box;
  margin: 0;
  min-width: 0;
  background-color: #EBEBEB;
  height: 1px;
}
/*.Input-1{*/
/*  -webkit-box-flex: 1;*/
/*  background: transparent;*/
/*  border: none;*/
/*  -ms-flex: 1 1;*/
/*  flex: 1 1;*/
/*  font-family: inherit;*/
/*  font-size: inherit;*/
/*  font-weight: inherit;*/
/*  overflow: hidden;*/
/*  padding: 0;*/
/*  resize: none;*/
/*  outline: 0;*/
/*}*/
/*.Input-2{*/
/*  border: 0;*/
/*  display: block;*/
/*  font-size: 16px;*/
/*  font-synthesis: style;*/
/*  !*font-weight: 600;*!*/
/*  height: 44px;*/
/*  line-height: 1.4;*/
/*  min-height: 44px;*/
/*  width: 100%;*/
/*}*/
.Input1{
  -webkit-box-flex: 1;
  background: transparent;
  border: none;
  -ms-flex: 1 1;
  flex: 1 1;
  font-family: inherit;
  font-size: inherit;
  font-weight: inherit;
  overflow: hidden;
  padding: 0;
  resize: none;
  outline: 0;
}
.Input{
  border: 0;
  display: block;
  font-size: 32px;
  font-synthesis: style;
  font-weight: 600;
  height: 44px;
  line-height: 1.4;
  min-height: 44px;
  width: 100%;
}
.Input-title1{
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  background: #fff;
  border: 1px solid #ebebeb;
  border-radius: 3px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  font-size: 14px;
  height: 34px;
  padding: 4px 10px;
  position: relative;
  -webkit-transition: background .2s,border .2s;
  transition: background .2s,border .2s;
  width: 180px;
}
.Input-title{
  border: 0;
  height: auto;
  margin: 16px 9px;
  padding: 0;
  position: relative;
  width: 100%;
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
  width: 722px;
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
</style>
