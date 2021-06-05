<template>
  <div class="view-home">
    <div class="content-box">
      <nav class="nav flex-between">
        <h1 class="left">我的论文管理组织</h1>
        <div class="right">
          <button type="button" class="el-button el-button--primary" @click="handleEnterPaper">
            <i class="el-icon-plus"></i>
            <span>加入论文管理</span>
          </button>
        </div>
      </nav>
      <div>
        <div class="no-data">
          <p class="text">同学您好,欢迎您进入课堂派论文管理系统</p>
          <p class="des">"目前您还未加入任何论文管理组织，请点击"<font class="blue">"加入论文管理组织"</font>
            ",输入邀请码加入论文评审/答辩组织。"</p>
          <ul class="progress flex-middle">
            <li>加入管理组织</li>
            <span class="line"></span>
            <li>学生上交论文</li>
            <span class="line"></span>
            <li>导师审核</li>
            <span class="line"></span>
            <li>管理人员分配评审/答辩</li>
            <span class="line"></span>
            <li>专家/答辩委员评审</li>
            <span class="line"></span>
            <li>完成论文评审/答辩</li>
            <span class="line"></span>
          </ul>
        </div>
      </div>
      <el-dialog title="加入论文管理组织"
                 :visible="enterPaper"
                 width="20%"
                 :before-close="handleEnterPaper"
                 center
      >
        <el-input v-model="inviteCode" placeholder="请输入组织密钥"></el-input>
        <span slot="footer" class="dialog-footer">
        <el-button @click="handleEnterPaper">取 消</el-button>
        <el-button type="primary" >立即加入</el-button>
      </span>
      </el-dialog>
    </div>

  </div>
</template>

<script>
import store from '../store'
import {mapState,mapMutations,mapActions} from 'vuex'
export default {
  name: 'HelloWorld',

  created() {
    this.addAction(2);
  },
  data(){
    return {
      enterPaper: false,
      inviteCode:'',
    };
  },
  computed:{
    ...mapState(["count"])
  },
  methods:{
    handleEnterPaper() {
      this.enterPaper = this.enterPaper ? false : true;
    },
    ...mapMutations(["add","reduce"]),
    ...mapActions(["addAction","reduceAction"])
  },
  store
}
</script>


<style scoped>
.view-home{
  padding-top: 72px;
}
.nav {
  padding: 24px 0;
}
 .flex-between {
  display: flex;
  align-items: center;
   justify-content: space-between;
}
 .no-data {
  margin-top: 7px;
  padding: 31px 24px;
  background: #f8f9fa;
  border-radius: 8px;
  text-align: left;
}
.text{
  font-size: 20px;
  font-weight: 400;
  color: #111a34;
  line-height: 24px;
  margin-bottom: 26px;
}
.des {
  font-size: 14px;
  font-weight: 400;
  color: #77809a;
  line-height: 24px;
}
.blue {
  color: #4285f4;
}
.progress {
  margin-top: 48px;
  white-space: nowrap;
}
.flex-middle {
  display: flex;
  align-items: center;
}
.line{
   content: "";
   display: block;
   margin: 0 4px;
   width: 40px;
   height: 1px;
   background: #2589e7;
 }
li, ol, ul {
  list-style: none;
}
 li {
  padding: 14px 20px;
  background: #fff;
  border-radius: 24px;
  color: #2589e7;
  font-size: 14px;
  font-weight: 500;
}
.dialog-footer {
  text-align: center;
}
</style>
