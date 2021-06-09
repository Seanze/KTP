<template>
  <div>
    <div class="logo" >
      <img src="../assets/homepageimg/logo.png" width="125" alt="no logo" @click="ToMain">
    </div>
    <el-container style="position: absolute ;right: 0px;left:0px;">
      <div style="margin: 0 auto">
        <el-main>
          <el-row>
            <el-col>
              <div style="margin-top: 200px">
                <img src="../assets/enterpage/img1.png" width="690px" height="540px">
              </div>
            </el-col>
            <el-col >
              <div>
                <el-form class="login-container" ref="user" :model="user" label-width="80px">
                  <h1 style="position: relative; left: 0px;font-family: cursive;">账号登录</h1>
                  <el-form-item label="账号:" class="input-box">
                    <el-input type="text" v-model="user.username" placeholder="请输入您的学号/工号" label-width="80px"></el-input>
                  </el-form-item>
                  <el-form-item label="密码:" class="input-box">
                    <el-input type="password" v-model="user.password"  placeholder="密码"></el-input>
                  </el-form-item>
                  <el-checkbox v-model="checked" style="position: relative;left:0px; top: 0.9375rem;">下次自动登录</el-checkbox>
                  <el-link :underline="false" style="position: relative;left:100px;top: 0.9375rem;">忘记密码？</el-link>
                  <el-form-item>
                    <el-button type="primary" style="width: 360px; position: relative; left: -50px; top: 2.625rem;" @click="readyLogin">登录</el-button>
                  </el-form-item>
                  <p style="position: relative;left: 50px;top: 45px; color: #CAC6C6;">还没有账号？</p>
                  <router-link to="/register">
                    <el-button type="text" style="position: relative; left: 165px; top: 0px;font-size: 13px;">去注册</el-button>
                  </router-link>
                </el-form>
              </div>
            </el-col>
          </el-row>
        </el-main>
      </div>
    </el-container>
  </div>
</template>

<script>
import {mapActions} from "vuex";

export default {
  name: "Login",
  data(){
    return {
      user:{
        username:"13983289821",
        password:"123456"
      }
    }
  },
  methods:{
    readyLogin(){
      if (/^\d{11}$/.test(this.user.username)&&this.user.password.length>0){
        this.loginAction(this.user);
      }else {
        this.$message.error("请输入登录信息");
      }
    },
    ToMain() {
      this.$router.push({
        path: '/'
      })
    },

    ...mapActions(["loginAction"])
  }
}
</script>

<style scoped>
.login-container {
  border-radius: 15px;
  background-clip: padding-box;
  margin: auto auto;
  width: 415px;
  padding: 35px 35px 15px 35px;
  background: #fff;
  border: 1px solid #eaeaea;
  box-shadow: 0 0 25px #cac6c6;
  position: relative;
  left: 300px;
  bottom: 520px;
}

.input-box {
  margin-bottom: 24px;
  height: 45px;
  position: relative;
  left: -30px;
  top: 0.625rem;
}
.logo{
  padding-top: 150px;
  padding-left: 100px;
}

</style>
