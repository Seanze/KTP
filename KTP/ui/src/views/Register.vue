<template>
  <div>
    <div class="logo" >
      <img src="../assets/homepageimg/logo.png" width="125" alt="no logo" @click="ToMain">
    </div>
    <el-container style="position: absolute ;right: 0px;left:0px; " >
      <div style="margin: 0 auto">
        <el-main>
          <el-row>
            <el-col>
              <div style="margin-top: 200px">
                <img src="../assets/enterpage/img1.png" width="690px" height="540px">
              </div>
            </el-col>
            <el-col >
              <div style="bottom:630px;left:300px;width: 450px; height: 735px; margin-left: 35%;background:#FFFFFF; border-radius: 10px; position: relative;box-shadow: 0 0 25px #cac6c6;">
                <h1 style="height: 50px; font-size: 35px; line-height: 90px;font-family: cursive;position: relative;left: 130px">注册账号</h1>
                <el-form ref="user" :model="user" :rules="rules" style="margin-left: 20px; margin-right: 20px;">
                  <el-form-item prop="username">
                    <el-input v-model="user.username" placeholder="请输入电话"></el-input>
                  </el-form-item>
                  <el-form-item prop="password">
                    <el-input type="password" v-model="user.password" placeholder="请输入密码"></el-input>
                  </el-form-item>
                  <el-form-item prop="password">
                    <el-input type="password" v-model="user.rePassword" placeholder="请重新输入密码"></el-input>
                  </el-form-item>
                  <div class="el-form-item margin-bottom el-form-item--feedback">
                    <div class="el-form-item__content">
                      <p class="font-bold font16">选择身份</p>
                      <div class="role-box">
                        <div class="item flex-align":class="{active:role==='teacher'}"  @click="changeRole('teacher')">
                          <img src="../assets/register/teacher.svg" class="icon">
                          <span class="name">老师/助教</span>
                        </div>
                        <div class="item flex-align ":class="{active: role==='student'}" @click="changeRole('student')">
                          <img src="../assets/register/student.svg" class="icon">
                          <span class="name">学生</span>
                        </div>
                      </div>
                    </div>
                  </div>
                  <el-form-item prop="name">
                    <el-input v-model="user.name" placeholder="请输入姓名"></el-input>
                  </el-form-item>
                  <el-form-item prop="school">
                    <el-input v-model="user.school" placeholder="请输入学校"></el-input>
                  </el-form-item>
                  <el-form-item v-if="role==='student'" prop="tsid">
                    <el-input v-model="user.number" placeholder="我的学号/工号"></el-input>
                  </el-form-item>
                  <el-form-item prop="identyInput">
                    <el-input
                        v-model="user.identyInput"
                        placeholder="验证码"
                        style="width:220px;float:left"
                    ></el-input>
                    <div class="code" @click="refreshCode">
                      <s-identify :identifyCode="identifyCode"></s-identify>
                    </div>
                  </el-form-item>
                  <el-form-item>
                    <el-button type="primary" @click="register" style="width: 385px">注册</el-button>
                  </el-form-item>
                  <div style="width: 100px;height: 30px; margin-left: 280px; font-size: 13px;color: #CAC6C6;">
                    已有账号?
                  </div>
                  <router-link to='/login'>
                    <a style="width: 50px; float: right; font-size: 13px;position: relative;left: 5px;top: -30px;"> 去登录</a>
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
import store from "../store"
import SIdentify from "@/components/identify";
import {mapActions, mapState} from "vuex";
export default {
  name: "Register",
  data(){
    var newReg1 = (rule, value, callback) => {
      if (value != this.identifyCode) {
        callback(new Error("验证码错误"));
      } else {
        callback(); //必须要有回调，要不然表单无法提交
      }
    };
    return{
      user: {
        username:"",
        password:"",
        rePassword:"",
        name:"",
        school: "",
        number:"",
      },
      role: 'teacher',
      identifyCodes: "1234567890",
      identifyCode: "",
      rules: {
        username: [
          { required: true, message: "电话不能为空", trigger: "blur" },
          {
            pattern:/^\d{11}$/,
            message:"",
            trigger:"blur"
          }
        ],
        name: [
          {
            required: true,
            message: "姓名不能为空",
            trigger: "blur"
          },
          {
            pattern: /^[\u4E00-\u9FA5\uf900-\ufa2d·s]{2,20}$/,
            message: "姓名需为中文姓名",
            trigger: "change"
          }
        ],
        password: [
          { required: true, message: "密码不能为空", trigger: "blur" },
          // {
          //    pattern:/^(?![A-Za-z]+$)(?![A-Z0-9]+$)(?![a-z0-9]+$)(?![a-z\W_!@#$%^&*`~()-+=]+$)(?![A-Z\W_!@#$%^&*`~()-+=+$)(?![0-9\W_!@#$%^&*`~()-+=]+$)[a-zA-Z0-9\W_!@#$%^&*`~()-+=]{8,16}$/,
          //    message:"密码需8-16位(包含大小写字母、特殊符号、数字中的任意三项)",
          //   trigger:"blur"
          // }
        ],
        school: [
          { required: true, message: "学校不能为空", trigger: "blur" }
        ],
        identyInput: [
          {
            required: true,
            message: "验证码不能为空",
            trigger: "blur"
          },
          { validator: newReg1, trigger: "blur" }
        ]
      }
    }
  },
  store,
  components: {SIdentify},
  computed:{
    ...mapState([]),
  },
  methods:{
    changeRole(role){
      this.role = role;
    },
    ToMain() {
      this.$router.push({
        path: '/'
      })
    },

    register(){
      if(this.user.password !=this.user.rePassword){
        this.$message.error("请两次密码输入相同")
      }else
      if (/^\d{11}$/.test(this.user.username)
          &&this.user.password.length>0
          &&this.user.password === this.user.rePassword
          &&this.user.name.length>0
          &&this.user.school.length>0
          &&(this.role!=="student"||this.user.number.length>0)
      ){
        this.registerAction(this.user);
      }else {
        this.$message.error("请输入正确信息");
      }

    },
    ...mapActions(["registerAction"]),

    randomNum(min, max) {
      return Math.floor(Math.random() * (max - min) + min);
    },
    refreshCode() {
      this.identifyCode = "";
      this.makeCode(this.identifyCodes, 4);
    },
    makeCode(o, l) {
      for (let i = 0; i < l; i++) {
        this.identifyCode += this.identifyCodes[
            this.randomNum(0, this.identifyCodes.length)
            ];
      }
      console.log(this.identifyCode);
    },
  },


}

</script>

<style scoped>
.role-box{
  display: flex;
  justify-content: space-between;
}
.role-box .active {
  border: 1px solid #4285f4;
}
.logo{
  padding-top: 150px;
  padding-left: 100px;
}
.flex-align {
  display: flex;
  align-items: center;
}

.role-box .item {
  width: 172px;
  padding: 8px 16px;
}
.role-box .item .name {
  font-size: 14px;
  font-family: MicrosoftYaHei;
  text-align: center;
  color: #3c4043;
  line-height: 24px;
  letter-spacing: 1px;
}
.font-bold {
  font-weight: 700;
}

.font16 {
  font-size: 16px;
}
.code {
  width: 157px;
  height: 46px;
  float: right;
}
</style>
