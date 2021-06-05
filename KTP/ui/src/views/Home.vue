<template>
  <div class="home">
    <div class="head">
      <div class="logo-box">
        <img src="../assets/logo.png" width="106px" height="28px"/>
      </div>
      <div style="width: 50%">
        <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
          <el-menu-item style="margin-left: 55%" index="1">我的课堂</el-menu-item>
          <el-menu-item style="margin-left: 10%" index="2">论文管理</el-menu-item>
        </el-menu>
      </div>
      <div class="action">
        <img src="../assets/switch.png" width="15px" height="15px" style="margin-right: 5px"/>
        <div style="color:#7f7f7f;margin-right: 15px;cursor: default">试用旧版</div>
        <PersonTool/>
      </div>
    </div>
    <div class="content">
      <ClassPage v-if="activeIndex === '1'"/>
      <HelloWorld msg="论文管理" v-if="activeIndex === '2'"/>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import ClassPage from "@/components/ClassPage";
import {mapActions} from "vuex";
import PersonTool from "@/components/PersonTool";

export default {
  name: 'Home',
  components: {
    HelloWorld,
    ClassPage,
    PersonTool,
  },
  data() {
    return {
      activeIndex: '1',
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      this.activeIndex = key;
    },
    ...mapActions(["logoutAction"])
  }

}
</script>
<style>
.home {
  display: flex;
  flex-direction: column;
}

.head {
  width: 100%;
  /*border-bottom: solid 1px #e6e6e6;*/
  display: flex;
  flex-direction: row;
  align-items: center;
  padding-top: 10px;
}

.logo-box {
  width: 10%;
  border-bottom: solid 1px #e6e6e6;
  padding: 14px 5px 14px 80px;
}

.action {
  width: 40%;
  border-bottom: solid 1px #e6e6e6;
  padding: 10px 80px 10px 0;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: flex-end
}

.content {
  margin: 0 75px;
  /*background: #2d2d2d;*/
}
</style>
