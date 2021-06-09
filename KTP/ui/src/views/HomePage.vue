
<template>
  <div>
    <div style="margin: 0 auto">

      <el-menu  class="el-menu-demo"  mode="horizontal" default-active="1" style="width: 100%" router>
        <el-menu-item >
          <img :src="logoUrl"  width="125" alt="no logo"/>
        </el-menu-item>
        <el-menu-item index="1" style="margin-left: 100px" @click="tomain()">首页</el-menu-item>
        <el-menu-item index="2">产品功能</el-menu-item>
        <el-menu-item index="3">机构版</el-menu-item>
        <el-menu-item index="4">渠道合作</el-menu-item>
        <el-menu-item index="5">会员权益</el-menu-item>
        <el-menu-item index="6">帮助中心</el-menu-item>
        <el-menu-item >
          <i class="el-icon-sort" style="color: black;margin-left: 280px" ></i>
          <a href="https://v4.ketangpai.com/" style="margin-left: 0" target="_blank" >切换旧版本</a>
        </el-menu-item >

        <el-menu-item>
          <el-button v-show="login" type="primary" plain @click="logining">登录</el-button>
          <el-button v-show="login" type="primary" @click="registing">注册</el-button>
          <el-button v-show="islogin" type="primary" style="margin-top: 14px" @click="enterclass" size="mini" >进入课堂</el-button>
        </el-menu-item>
      </el-menu>
    </div>
    <el-carousel :interval="3000" arrow="always" height="400px" >
      <el-carousel-item>
        <img src="../assets/homepageimg/float1.png" width="100%" height="400px" alt>
      </el-carousel-item>
      <el-carousel-item >
        <img src="../assets/homepageimg/float2.jpg" width="100%" height="400px" >
      </el-carousel-item>
    </el-carousel>

    <el-container>
        <el-container style="margin-top: 50px">
          <el-header style="text-align: center">
            <span style="font-size: xxx-large">混合教学全过程管理</span>
          </el-header>
          <el-header style="text-align: center;color: #909399">
            <span style="font-size: large">课前、课中、课后、线上、线下、教学情境全过程管理</span>
          </el-header>
        </el-container >
    </el-container >


    <el-container style="text-align: center;background-color: azure">
      <div style="margin: 0 auto;width: 2000px;height: 400px">
        <el-container style="text-align: center;background-color: azure">
          <el-main >
            <el-row :gutter="20" align="center" style="margin-left: 18%">

              <el-col :span="3" style="height: 350px;width: 250px;background-color: aliceblue" >
                <div style="margin-top: 20%">
                  <img src="../assets/homepageimg/img1/text1.png" height="64px" width="64px">
                </div>
                <div style="text-align: center;margin-top: 10%">
                  <span style="font-size: x-large;font-weight: bolder" >作业</span>
                </div>
                <div style="text-align: center;margin-top: 5%">
                  <span style="text-align: center;color: #909399">81种文档格式作业在线展示和批阅，实时查重，精准对比，避免学生抄袭。 自动管理成绩，一键下载作业数据</span>
                </div>
              </el-col>

              <el-col :span="3" style="height: 350px;width: 250px;background-color: aliceblue;margin-left: 5%" >
                <div style="margin-top: 20%">
                  <img src="../assets/homepageimg/img1/text2.png" height="64px" width="64px">
                </div>
                <div style="text-align: center;margin-top: 10%">
                  <span style="font-size: x-large;font-weight: bolder">考试/练习</span>
                </div>
                <div style="text-align: center;margin-top: 5%">
                  <span style="text-align: center;color: #909399">单选、多选、填空、简答等10余种题型。支持题库随机抽题组卷。支持限时考试、选项随机等防作弊模式</span>
                </div>
              </el-col>

              <el-col :span="3" style="height: 350px;width: 250px;background-color: aliceblue;margin-left: 5%" >
                <div style="margin-top: 20%">
                  <img src="../assets/homepageimg/img1/text3.png" height="64px" width="64px">
                </div>
                <div style="text-align: center;margin-top: 10%">
                  <span style="font-size: x-large;font-weight: bolder">课件资料</span>
                </div>
                <div style="text-align: center;margin-top: 5%">
                  <span style="text-align: center;color: #909399">课件、资料、话题、公告等教学内容支撑。在线制作方便快捷，提升备课效率。支持课前发布活动，课中互动，课后巩固</span>
                </div>
              </el-col>

              <el-col :span="3" style="height: 350px;width: 250px;background-color: aliceblue;margin-left: 5%" >
                <div style="margin-top: 20%">
                  <img src="../assets/homepageimg/img1/text4.png" height="64px" width="64px">
                </div>
                <div style="text-align: center;margin-top: 10%">
                  <span style="font-size: x-large;font-weight: bolder">课中互动</span>
                </div>
                <div style="text-align: center;margin-top: 5%">
                  <span style="text-align: center;color: #909399">课件在线讲解、标记疑问 支持发言、开启弹幕、抢答、提问、话题讨论、黑板、画笔标注课堂要点，让课堂更精彩</span>
                </div>
              </el-col>

            </el-row>
          </el-main>
        </el-container>
      </div>
    </el-container>

    <el-container style="text-align: center;background-color: azure">
      <div style="margin: 0 auto;width: 2000px;height: 400px">
      <el-container style="text-align: center;background-color: azure">
        <el-main >
          <el-row :gutter="20" align="center" style="margin-left: 18%">

            <el-col :span="3" style="height: 350px;width: 250px;background-color: aliceblue" >
              <div style="margin-top: 20%">
                <img src="../assets/homepageimg/img1/text5.png" height="64px" width="64px">
              </div>
              <div style="text-align: center;margin-top: 10%">
                <span style="font-size: x-large;font-weight: bolder" >考勤签到</span>
              </div>
              <div style="text-align: center;margin-top: 5%">
                <span style="text-align: center;color: #909399">二维码、数字口令、GPS等5种考勤形式， 精准有效、避免代签 签到数据自动生成，一键导出</span>
              </div>
            </el-col>

            <el-col :span="3" style="height: 350px;width: 250px;background-color: aliceblue;margin-left: 5%" >
              <div style="margin-top: 20%">
                <img src="../assets/homepageimg/img1/text6.png" height="64px" width="64px">
              </div>
              <div style="text-align: center;margin-top: 10%">
                <span style="font-size: x-large;font-weight: bolder">成绩管理</span>
              </div>
              <div style="text-align: center;margin-top: 5%">
                <span style="text-align: center;color: #909399">汇总互动数据、平时成绩、期末成绩 个性化配置成绩权重占比数据报表一键导出下载，课留存，可追溯</span>
              </div>
            </el-col>

            <el-col :span="3" style="height: 350px;width: 250px;background-color: aliceblue;margin-left: 5%" >
              <div style="margin-top: 20%">
                <img src="../assets/homepageimg/img1/text7.png" height="64px" width="64px">
              </div>
              <div style="text-align: center;margin-top: 10%">
                <span style="font-size: x-large;font-weight: bolder">教学数据分析</span>
              </div>
              <div style="text-align: center;margin-top: 5%">
                <span style="text-align: center;color: #909399">全方位教学数据信息化，可视化实时监测教学质量，把控教学进度，学业预警分析，提升教学效果</span>
              </div>
            </el-col>

            <el-col :span="3" style="height: 350px;width: 250px;background-color: aliceblue;margin-left: 5%" >
              <div style="margin-top: 20%">
                <img src="../assets/homepageimg/img1/text8.png" height="64px" width="64px">
              </div>
              <div style="text-align: center;margin-top: 10%">
                <span style="font-size: x-large;font-weight: bolder">直播-云录屏</span>
              </div>
              <div style="text-align: center;margin-top: 5%">
                <span style="text-align: center;color: #909399">满足线上线下混合式教学场景 动画及课件同屏+语音实现轻量级直播 不限人员数量，手机电脑均可参与</span>
              </div>
            </el-col>

          </el-row>
        </el-main>
      </el-container>
      </div>
    </el-container>

    <el-container style="background-color: aliceblue">
      <el-container style="margin-top: 30px">
        <el-header style="text-align: center">
          <span style="font-size: xxx-large">智慧教学平台</span>
        </el-header>
      </el-container >
    </el-container >

    <el-container style="text-align: center;background-color: aliceblue">
      <div style="margin: 0 auto;width: 2000px;height: 400px">
      <el-container style="text-align: center;background-color: aliceblue">
        <el-main >
          <el-row :gutter="20" align="center" style="margin-left: 18%">

            <el-col :span="3" style="height: 350px;width: 250px;background-color: azure" >
              <div style="margin-top: 20%">
                <img src="../assets/homepageimg/img2/text1.png" height="64px" width="64px">
              </div>
              <div style="text-align: center;margin-top: 10%">
                <span style="font-size: x-large;font-weight: bolder" >线下互动课堂</span>
              </div>
              <div style="text-align: center;margin-top: 5%">
                <span style="text-align: center;color: #909399">多种互动教学工具，沉浸式学习体验，精准化学习</span>
              </div>
            </el-col>

            <el-col :span="3" style="height: 350px;width: 250px;background-color: azure;margin-left: 5%" >
              <div style="margin-top: 20%">
                <img src="../assets/homepageimg/img2/text2.png" height="64px" width="64px">
              </div>
              <div style="text-align: center;margin-top: 10%">
                <span style="font-size: x-large;font-weight: bolder">混合教学功能管理</span>
              </div>
              <div style="text-align: center;margin-top: 5%">
                <span style="text-align: center;color: #909399">课前课中课后全过程教学管理，教学数据可视化，可留存，提升教学质量</span>
              </div>
            </el-col>

            <el-col :span="3" style="height: 350px;width: 250px;background-color: azure;margin-left: 5%" >
              <div style="margin-top: 20%">
                <img src="../assets/homepageimg/img2/text3.png" height="64px" width="64px">
              </div>
              <div style="text-align: center;margin-top: 10%">
                <span style="font-size: x-large;font-weight: bolder">在线直播教室</span>
              </div>
              <div style="text-align: center;margin-top: 5%">
                <span style="text-align: center;color: #909399">在线直播教学搭配教学互动，充分还原真实的教学场景，提升教学效果</span>
              </div>
            </el-col>

            <el-col :span="3" style="height: 350px;width: 250px;background-color: azure;margin-left: 5%" >
              <div style="margin-top: 20%">
                <img src="../assets/homepageimg/img2/text4.png" height="64px" width="64px">
              </div>
              <div style="text-align: center;margin-top: 10%">
                <span style="font-size: x-large;font-weight: bolder">在线课堂建设</span>
              </div>
              <div style="text-align: center;margin-top: 5%">
                <span style="text-align: center;color: #909399">在线直播课、精品慕课资源、课程资源体系搭建，沉淀教学资源</span>
              </div>
            </el-col>
          </el-row>
        </el-main>
      </el-container>
      </div>
    </el-container>

    <el-container style="background-color: aliceblue">
      <div style="margin: auto">
        <div>
        <el-button size="large" type="primary" plain >了解详细功能</el-button>
        <el-button type="primary"  >立即体验注册</el-button>
        </div>
      </div>
    </el-container>

    <el-container style="background-color: azure">
      <el-container style="margin-top: 4%">
        <el-header style="text-align: center">
          <span style="font-size: xxx-large">课堂派机构版</span>
        </el-header>
      </el-container >
    </el-container >

<!-- 课堂机构版-->
    <el-container style="text-align: center;background-color: azure">
      <div style="margin: 0 auto;width:1500px;height: 620px">
        <el-container style="text-align: center;background-color: azure">
          <el-main >
            <el-row :gutter="20" align="center" style="margin-left: 1%;height: auto;width: auto">

              <el-col :span="3" style="height: 580px;width: 700px;background-color: azure" >
                <div style="margin-top: 2%">
                  <img src="../assets/homepageimg/img3/text.png" height="525px" width="648px">
                </div>
              </el-col>

              <el-col :span="3" style="height: 580px;width: 650px;background-color: azure;margin-left: 50px">
                <div style="text-align: left;margin-left: 0">
                  <img src="../assets/homepageimg/img3/text1.png" width="24px" height="24px" style="margin-top: 10px">
                  <span style="font-size: x-large;font-weight: bolder;margin-left: 10px">精准高效管理教学事务</span>
                </div>
                <div style="text-align: left;margin-top: 10px">
                  <span style="margin-left: 20px;color: #909399">一键对接教务系统，精准高效管理师生教学、课程、课务。</span>
                </div>

                <div style="text-align: left;margin-left: 0;margin-top: 30px">
                  <img src="../assets/homepageimg/img3/text1.png" width="24px" height="24px" style="margin-top: 10px">
                  <span style="font-size: x-large;font-weight: bolder;margin-left: 10px">有效提升教学质量</span>
                </div>
                <div style="text-align: left;margin-top: 10px">
                  <span style="margin-left: 20px;color: #909399">以课堂教学为核心，以产出为导向；实时监控师生、课程、教学活动等教学过程。</span>
                </div>

                <div style="text-align: left;margin-left: 0;margin-top: 30px">
                  <img src="../assets/homepageimg/img3/text1.png" width="24px" height="24px" style="margin-top: 10px">
                  <span style="font-size: x-large;font-weight: bolder;margin-left: 10px">教学资产管理</span>
                </div>
                <div style="text-align: left;margin-top: 10px">
                  <span style="margin-left: 20px;color: #909399">沉淀教学过程资产，促进优质课程、资源、知识图谱建设。</span>
                </div>

                <div style="text-align: left;margin-left: 0;margin-top: 30px">
                  <img src="../assets/homepageimg/img3/text1.png" width="24px" height="24px" style="margin-top: 10px">
                  <span style="font-size: x-large;font-weight: bolder;margin-left: 10px">智慧校园全景定制</span>
                </div>
                <div style="text-align: left;margin-top: 10px">
                  <span style="margin-left: 20px;color: #909399">以学生为中心，以教学为导向，提供校园全景智慧教学解决方案。</span>
                </div>

                <div style="margin: auto;margin-top: 50px;text-align: left">
                  <div style="margin-left: 60px">
                    <el-button type="primary" plain>了解详细功能</el-button>
                    <el-button type="primary" style="margin-left: 10px">申请免费试用</el-button>
                  </div>
                </div>
              </el-col>

            </el-row>
          </el-main>
        </el-container>
      </div>
    </el-container>

<!--媒体报道大字-->
    <el-container >
      <el-container style="margin-top: 4%">
        <el-header style="text-align: center">
          <span style="font-size: xxx-large">媒体报道</span>
        </el-header>
      </el-container >
    </el-container >

<!--最后一个走马灯-->
    <el-carousel :interval="4000" type="card" height="350px" style="margin-top: 40px" >

      <el-carousel-item   style="background-color: aliceblue">
        <el-container style="text-align: center">
          <div style="margin: 0 auto;width:1000px;height: 350px">
            <el-container style="text-align: left;background-color: aliceblue">
              <el-main >
                <el-row :gutter="20" align="left" style="margin-left: 1%;height: auto;width: auto" type="flex">
                  <el-col :span="3" style="height: auto;width: 250px;margin-top: 0;margin-left: 0" >
                    <div>
                      <img src="../assets/homepageimg/img4/float4.png" width="240" height="320px">
                    </div>
                  </el-col>
                  <el-col :span="3" style="text-align:left;height: 320px;width: 600px;margin-left: 20px;margin-top: 30px">
                    <div style="width: auto;height: 50px">
                      <span  style="font-size: x-large;font-weight: bolder">课堂派亮相2018中国“互联网+”数字经济峰会</span>
                    </div>
                    <div style="width: auto;height: 100px;margin-top: 50px">
                      <span class="mrinfo">4月12日下午教育分论坛，北京大学软件与微电子学院林院长分享了智慧课堂的建设经验：教学资源呈现多样化、课堂形式丰富、如何把学生从玩手机的屏幕聚焦到课堂互动环节等方面。林院长表示，课堂派在研发过程中，学院的一线教师主动参与，把很多丰富的实际教学经验融入研发当中，使整个智慧课堂的建设更具实用性和前瞻性。</span>
                    </div>

                    <div style="margin: auto;margin-top: 50px;text-align: left">
                      <div style="margin-left: 60px">
                        <el-button  type="primary" style="margin-left: 10px" ><a href="https://edu.qq.com/a/20180719/029331.htm"></a>了解详情</el-button>
                      </div>
                    </div>

                  </el-col>
                </el-row>
              </el-main>
            </el-container>
          </div>
        </el-container>
      </el-carousel-item>

<!--第二张-->
      <el-carousel-item   style="background-color: aliceblue">
        <el-container style="text-align: center">
          <div style="margin: 0 auto;width:1000px;height: 350px">
            <el-container style="text-align: left;background-color: aliceblue">
              <el-main >
                <el-row :gutter="20" align="left" style="margin-left: 1%;height: auto;width: auto" type="flex">
                  <el-col :span="3" style="height: auto;width: 250px;margin-top: 0;margin-left: 0" >
                    <div>
                      <img src="../assets/homepageimg/img4/float6.png" width="240" height="320px">
                    </div>
                  </el-col>
                  <el-col :span="3" style="text-align:left;height: 320px;width: 600px;margin-left: 20px;margin-top: 30px">
                    <div style="width: auto;height: 50px">
                      <span  style="font-size: x-large;font-weight: bolder">新时代新青年 课堂派创始人陈杰宾的创业梦</span>
                    </div>
                    <div style="width: auto;height: 100px;margin-top: 50px">
                      <span style="margin-top: 50px;color: #909399">6月26日，中国共产主义青年团第十八次全国代表大会在人民大会堂开幕。共青团委对福建省驻京团工委点赞，CCTV新闻频道进行了同步报道。分享会上，课堂派创始人陈杰宾作为闽籍创业青年代表，向在京青年创业者分享了课堂派的发展模式以及创业历程。</span>
                    </div>

                    <div style="margin: auto;margin-top: 50px;text-align: left">
                      <div style="margin-left: 60px">
                        <el-button type="primary" style="margin-left: 10px">了解详情</el-button>
                      </div>
                    </div>

                  </el-col>
                </el-row>
              </el-main>
            </el-container>
          </div>
        </el-container>
      </el-carousel-item>

<!-- 第三张-->
      <el-carousel-item   style="background-color: aliceblue">
        <el-container style="text-align: center">
          <div style="margin: 0 auto;width:1000px;height: 350px">
            <el-container style="text-align: left;background-color: aliceblue">
              <el-main >
                <el-row :gutter="20" align="left" style="margin-left: 1%;height: auto;width: auto" type="flex">
                  <el-col :span="3" style="height: auto;width: 250px;margin-top: 0;margin-left: 0" >
                    <div>
                      <img src="../assets/homepageimg/img4/float2.png" width="240" height="320px">
                    </div>
                  </el-col>
                  <el-col :span="3" style="text-align:left;height: 320px;width: 600px;margin-left: 20px;margin-top: 30px">
                    <div style="width: auto;height: 50px">
                      <span  style="font-size: x-large;font-weight: bolder">【新浪新闻】课堂派云管理颠覆高校传统实习模式</span>
                    </div>
                    <div style="width: auto;height: 100px;margin-top: 50px">
                      <span style="margin-top: 50px;color: #909399">用课堂派最大的好处就是在学习的过程中，随时跟老师进行沟通和分享，无论从知识和情感层面都需要倾诉，而课堂派不仅提供跟老师同学交流的机会，还能够获得别人的指导和鼓励，让整个学习过程更加轻松。</span>
                    </div>

                    <div style="margin: auto;margin-top: 50px;text-align: left">
                      <div style="margin-left: 60px">
                        <el-button type="primary" style="margin-left: 10px">了解详情</el-button>
                      </div>
                    </div>

                  </el-col>
                </el-row>
              </el-main>
            </el-container>
          </div>
        </el-container>
      </el-carousel-item>

<!--第四张-->
      <el-carousel-item   style="background-color: aliceblue">
        <el-container style="text-align: center">
          <div style="margin: 0 auto;width:1000px;height: 350px">
            <el-container style="text-align: left;background-color: aliceblue">
              <el-main >
                <el-row :gutter="20" align="left" style="margin-left: 1%;height: auto;width: auto" type="flex">
                <el-col :span="3" style="height: auto;width: 250px;margin-top: 0;margin-left: 0" >
                  <div>
                    <img src="../assets/homepageimg/img4/float5.png" width="240" height="320px">
                  </div>
                </el-col>
                <el-col :span="3" style="text-align:left;height: 320px;width: 400px;margin-left: 20px;margin-top: 30px">
                  <div style="width: auto;height: 50px">
                    <span  style="font-size: x-large;font-weight: bolder">助力智慧课堂：课堂派成为腾讯微校生态战略伙伴</span>
                  </div>
                  <div style="width: auto;height: 100px;margin-top: 50px">
                    <span style="margin-top: 50px;color: #909399">用课堂派最大的好处就是在学习的过程中，随时跟老师进行沟通和分享，无论从知识和情感层面都需要倾诉，而课堂派不仅提供跟老师同学交流的机会，还能够获得别人的指导和鼓励，让整个学习过程更加轻松。</span>
                  </div>

                  <div style="margin: auto;margin-top: 50px;text-align: left">
                    <div style="margin-left: 60px">
                      <el-button type="primary" style="margin-left: 10px">了解详情</el-button>
                    </div>
                  </div>

                </el-col>
              </el-row>
            </el-main>
          </el-container>
        </div>
        </el-container>
      </el-carousel-item>

<!--第五张-->
      <el-carousel-item   style="background-color: aliceblue">
        <el-container style="text-align: center">
          <div style="margin: 0 auto;width:1000px;height: 350px">
            <el-container style="text-align: left;background-color: aliceblue">
              <el-main >
                <el-row :gutter="20" align="left" style="  margin-left: 1%;height: auto;width: auto" type="flex">
                  <el-col :span="3" style="height: auto;width: 250px;margin-top: 0;margin-left: 0" >
                    <div>
                      <img src="../assets/homepageimg/img4/float4.png" width="240" height="320px">
                    </div>
                  </el-col>
                  <el-col :span="3" style="text-align:left;height: 320px;width: 600px;margin-left: 20px;margin-top: 30px">
                    <div style="width: auto;height: 50px">
                      <span  style="font-size: x-large;font-weight: bolder">【华北电力大学】“互联网+”让教育发现每一个学生</span>
                    </div>
                    <div style="width: auto;height: 100px;margin-top: 50px">
                      <span style="margin-top: 50px;color: #909399">“课堂上教师要及时了解学生对内容的掌握程度，课下学生也希望教师能对自己的学习困难进行及时的指导。”在以前，这些实现起来比较困难的事情，“课堂派”可以让这一切变得轻而易举。</span>
                    </div>

                    <div style="margin: auto;margin-top: 50px;text-align: left">
                      <div style="margin-left: 60px">
                        <el-button type="primary" style="margin-left: 10px">了解详情</el-button>
                      </div>
                    </div>

                  </el-col>
                </el-row>
              </el-main>
            </el-container>
          </div>
        </el-container>
      </el-carousel-item>
    </el-carousel>

    <el-container >
      <el-container style="margin-top: 1%">
        <el-header style="text-align: center">
          <span style="font-size: xxx-large;color: dodgerblue">10000+</span>
          <span style="font-size: xxx-large">所学校的师生正在使用课堂派</span>
        </el-header>
      </el-container >
    </el-container >

    <el-container >
      <div style="margin: 0 auto">
      <el-container style="margin-top: 0;text-align: center">
        <img src="../assets/homepageimg/text.png" align="center">
      </el-container >
      </div>
    </el-container >

<!--联系课堂派-->
    <el-container style="text-align: center">
      <div :style="divimg" style="margin: 0 auto;width:100%;height: 400px" >
        <el-container style="margin-top: 1%;margin: 0 auto;width: 500px;height: 100%">
          <div style="margin: 0 auto;margin-top: 80px">
            <span style="font-size: 60px;color: beige">欢迎使用课堂派</span>
            <div style="margin-top: 40px">
              <span style="font-size: 30px;color: beige">精彩教学，从这里开启</span>
            </div>
            <div style="margin-top: 40px">
              <el-button type="primary">联系课堂派</el-button>
              <el-button type="primary" plain>免费注册</el-button>
            </div>
          </div>
        </el-container >
      </div>
    </el-container >

<!--二维码-->
    <el-container style="text-align: center">
      <div style="margin: 0 auto;background-color: #303133;width: 100%;height: 250px">

        <el-container style="margin-top: 0;height: 250px;margin: 0 auto;width: 1600px">
          <div style="margin: 0 auto;width: 600px">
            <div style="text-align: left;margin-top: 60px">
              <img src="../assets/homepageimg/logo2.png">
            </div>
            <div style="text-align: left;margin-top: 40px">
              <span style="color: beige;margin-left: 0">关于我们</span>
              <span style="color: beige;margin-left: 50px">服务条款</span>
              <span style="color: beige;margin-left: 50px">产品动态</span>
              <span style="color: beige;margin-left: 50px">浏览器下载</span>
            </div>
          </div>
          <el-main style="width: 700px;margin-left: 280px;height: auto">
            <el-row :gutter="20" align="center" style="margin-left: 1%;height: 200px;width: 600px">

              <el-col :span="3" style="height: 150px;width: 150px;text-align: left;margin-top: 50px" >
                <div>
                  <span style="color: beige;size: 20px">联系我们</span>
                </div>
                <div>
                  <span style="color: #909399;font-size: 10px">(工作日09:30～18:30)</span>
                </div>
                <div style="margin-top: 10px">
                  <i class="el-icon-phone" style="color: beige"></i>
                  <span style="color: beige;font-size: 13px">010-57748642</span>
                </div>
                <div style="margin-top: 10px">
                  <i class="el-icon-message" style="color: beige"></i>
                  <span style="color: beige;font-size: 12px">hi@ketangpai.com</span>
                </div>
              </el-col>

              <el-col :span="3" style="height: 150px;width: 140px;margin-top: 30px;margin-left: 10px" >
                <div >
                  <img src="../assets/homepageimg/man.png" height="120px" width="120px">
                </div>
                <div style="margin-top: 10px">
                  <span style="color: beige; font-size: 15px">课堂派客服-堂堂</span>
                </div>
              </el-col>

              <el-col :span="3" style="height: 150px;width: 140px;margin-top: 30px;margin-left: 10px" >
                <div >
                  <img src="../assets/homepageimg/woman.png" height="120px" width="120px">
                </div>
                <div style="margin-top: 10px">
                  <span style="color: beige; font-size: 15px">课堂派客服-派派</span>
                </div>
              </el-col>

              <el-col :span="3" style="height: 150px;width: 140px;margin-top: 30px;margin-left: 10px" >
                <div >
                  <img src="../assets/homepageimg/calss.png" height="120px" width="120px">
                </div>
                <div style="margin-top: 10px">
                  <span style="color: beige; font-size: 15px">扫码开启移动教学</span>
                </div>
              </el-col>

            </el-row>
          </el-main>
        </el-container>
      </div>
    </el-container>

    <el-footer style="background-color: black;height: 50px;text-align: center">
      <span style="color: beige;margin-left: 0;font-size: 5px">Copyright © 2014 ketangpai.com All Rights Reserved. 京ICP备14023276号-4</span>
      <span style="color: beige;margin-left: 50px;font-size: 5px">教APP备1101923号</span>
      <span style="color: beige;margin-left: 50px;font-size: 5px">京公网安备 11011402010566号</span>
    </el-footer>

  </div>
</template>



<script>
export default {
  name: "Home",
  data() {
    return {
      success: true,
      logoUrl: require('../assets/homepageimg/logo.png'),
      islogin: false,
      login: true,
    };
  },
  methods: {

    tomain() {
      this.$router.push({
        path: '/'
      })
    },
    logining(){

      this.$router.push({
        path: '/login'
      });
    },
    registing(){

      this.$router.push({
        path: '/register'
      });
    },
    enterclass(){
      this.$prompt('请输入邮箱', '提示', {
        confirmButtonText: '登录',
        cancelButtonText: '注册',
        inputPattern: /[\w!#$%&'*+/=?^_`{|}~-]+(?:\.[\w!#$%&'*+/=?^_`{|}~-]+)*@(?:[\w](?:[\w-]*[\w])?\.)+[\w](?:[\w-]*[\w])?/,
        inputErrorMessage: '邮箱格式不正确'
      }).then(({ value }) => {
        this.$message({
          type: 'success',
          message: '你的邮箱是: ' + value
        });
      }).catch(() => {
        this.$message({
          type: 'info',
          message: '取消登录'
        });
      });
    }
  },

}



</script>

<style scoped>
.mrinfo {
  height: 100px;
  margin-top: 40px;
  margin-bottom: 40px;
  font-size: 16px;
  line-height: 25px;
  overflow: hidden;
  position: relative;
}
</style>
