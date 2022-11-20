<template>
<div>
  <div class="login1">

  </div>


  <main role="main">
    <div class="css-login">
      <div class="css-login2">
        <el-form ref="loginForm" :model="form" :rules="rules" label-width="80px" class="login-box" style="background-color: white">
          <h3 class="login-title">欢迎登录</h3>
          <el-form-item label="账号" prop="username">
            <el-input type="text" placeholder="请输入账号" v-model="form.username"/>
          </el-form-item>
          <el-form-item label="密码" prop="password">
            <el-input type="password" placeholder="请输入密码" v-model="form.password"/>
          </el-form-item>
          <el-form-item>
            <div v-if="">
              <el-button type="primary" v-on:click="onSubmit('loginForm')">登录</el-button>
            </div>
          </el-form-item>
        </el-form>

    <el-dialog title="温馨提示" :visible.sync="dialogVisiable" width="30%" :before-close="handleClose">
      <span>请输入账号和密码</span>
      <span slot="footer" class="dialog-footer">
          <el-button type="primary" @click="dialogVisible = false">确定</el-button>
        </span>
    </el-dialog>
      </div>
    </div>
  </main>
</div>
</template>

<script>
export default {
  name: "Login",
  data(){
    return{
      info:{
        username:null,
        password:null,
      },
      form:{
        username:'',
        password:''
      },
      //表单验证，需要在 el-form-item 元素中增加prop属性
      rules:{
        username:[
          {required:true,message:"账号不可为空",trigger:"blur"},
          {min: 3, max: 10, message: "长度在3到10之间哦！",trigger: "blur"}
        ],
        password:[
          {required:true,message:"密码不可为空",tigger:"blur"},
          {min: 6, max: 15, message: "长度在6到15之间哦！",trigger: "blur"}
        ]
      },
      type:'1',

      //对话框显示和隐藏
      dialogVisible:false
    }
  },
  methods:{
    markData:function (){
      this.axios({
        method: 'get',
        url:"http://localhost:8080/static/mock/data.json"
      }).then(response => {
        this.info = response.data
      },
      error=>{
        console.log("请求失败")
      })
    },
    handleClose:function (){
      console.log("Handle Close,空函数");
    },
    // dialogVisiable:function (){
    //   console.log("Handle Close,空函数");
    // },
    onSubmit(formName){
      //为表单绑定验证功能
      this.$refs[formName].validate(async valid=>{
        if(!valid) return ;
        const result = await this.$http.post('/user/login',this.form);
        if(result.status !== 200)return console.log("登录失败");
        console.log("登录成功");
        // console.log(result.status);
        // console.log(result.data.data.token);
        // console.log(result);
        sessionStorage.setItem('token',result.data.data.token);
        // this.$router.push('/user/'+this.form.username);
        this.$router.push('/main');
          this.$notify({
            title:'登录成功',
            message:'欢迎您！',
            type:'success'
          });
      });
    }
  }
}
</script>

<style lang="scss" scoped>
.css-login2{
  //background-color: white;
}
//.login1{
//  position: fixed;
//  top: 0;
//  right: 0;
//  left: 0;
//  z-index: 101;
//  display: none;
//  height: 2px;
//  pointer-events: none;
//  background: #056DE8;
//  -webkit-transform: translateX(-100%);
//  -ms-transform: translateX(-100%);
//  transform: translateX(-100%);
//}
//.css-login1{
//  /* 03 */
//  position: absolute;
//  width: 1028px;
//  height: 771px;
//  top: 215px;
//  left: 98px;
//
//
//  background: url("https://s2.loli.net/2022/11/07/K5NHdT6i7UIo4Gy.jpg");
//}
//.css-login{
//  /* 编组 3 */
//  position: absolute;
//  width: 1402px;
//  height: 771px;
//  top: 215px;
//  left: 98px;
//
//
//}
.css-login2{
  -webkit-box-flex: 1;
  -ms-flex: 1 1;
  flex: 1 1;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  border-radius: 2px;
  min-height: 688px;
  height: calc(100% - 42px);
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}
.css-login {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  background-image: url("../img/未命名的设计.png");
  background-repeat: no-repeat;
  //background-color: #b8e5f8;
  background-size: cover;
  width: 100%;
  height: 100vh;
  overflow: auto;
  //z-index: -8;
}
.login-box{
  //border:1px solid #DCDFE6;
  box-shadow: #303133;
  margin-top: 90px;
  width: 350px;
  //margin:180px auto;
  padding: 35px 35px 15px 35px;
  border-radius: 5px;
  -webkit-border-radius: 5px;
  -moz-border-radius: 5px;
  box-shadow: 30px 40px 100px rgba(0, 0, 0, 0.25);
}
.login-title{
  text-align:center;
  margin: 0 auto 40px auto;
  color: #303133;
}
</style>
