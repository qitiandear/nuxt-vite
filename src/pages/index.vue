<template>
  <div class="content-box">
    <carousel />
    <div class="content-box-one">
      <div class="title">
        <div>智能SPD供应链+物联网平台</div>
        <div>移动端操作系统</div>
        <div class="subTitle">
          杏林丹心APP，按照医生、护士、供应商、配送人员的线下功能，完全展示日常工作的场景。
        </div>
      </div>
      <div class="content-box-bottom">
        <div>
          <div
            class="content-box-bottom-list"
            v-for="(item, index) in performanceData"
            :key="index"
          >
            <el-image
              style="width: 36px; margin-right: 30px"
              :src="item.picture"
              fit="contain"
            />
            <div v-html="item.data"></div>
          </div>
        </div>
        <div class="downloadBox">
          <div style="margin-top: 10px">扫描下方二维码</div>
          <div>下载杏林丹心APP</div>
          <div style="margin-top: 20px">支持Android、iOS</div>
          <el-image class="download" :src="downloadUrl" alt="" />
        </div>
      </div>
    </div>
    <div class="content-box-two"></div>
    <div class="content-two">
      <div class="content-two-top">
        <div>智能SPD供应链+物联网平台</div>
        <div>智能高值耗材智能柜</div>
      </div>
      <div
        style="display: flex; align-items: center; width: 1660px; margin: auto"
      >
        <img
          src="@/assets/images/ProductPictures.png"
          alt=""
          class="Product-pictures"
        />
        <div>
          <div
            style="
              margin-right: 280px;
              color: #333333;
              font-size: 24px;
              text-indent: 2em;
            "
          >
            医用高值耗材智能柜，是我公司依据多年配送经验，将不同类别的高值
            耗材在医院、供应商实际配送中的需求，精心打造的一款产品。更好地服务
            于临床一线，提升医疗服务质量和医院整体经济运行效益。
          </div>
          <div style="margin-top: 25px; display: flex; flex-wrap: wrap">
            <div
              class="content-two-right"
              v-for="(item, index) in smartArkList"
              :key="index"
            >
              <el-image
                :src="item.picture"
                alt=""
                style="
                  width: 86px;
                  margin-right: 37px;
                  margin-left: 23px;
                  color: #333333;
                "
              />
              <div>{{ item.content }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="content-three">
      <div class="title">
        <div style="font-size: 36px; color: #333333">我们的服务对象</div>
        <div style="font-size: 16px; color: #999999">
          服务于大型骨科器械物流配送（生产厂家、发货平台、客户），将生产、仓存、配送、技术服务利用互联网+的思维整合起来
        </div>
      </div>
      <div class="content-three-bg">
        <div class="content-three-center">
          <!-- <img src="@/assets/images/arrow.png" alt=""> -->
        </div>
        <dl style="padding-top: 90px; padding-left: 380px">
          <dt style="font-size: 36px; margin-bottom: 47px">生产厂家</dt>
          <dd class="content-three-left">帮助厂家组建专业的跟台团队</dd>
          <dd class="content-three-left">销售数据的准确统计</dd>
          <dd class="content-three-left">
            将患者的使用情况反馈回厂家，促进改进生产
          </dd>
        </dl>
      </div>
    </div>
    <div class="content-four" style="margin-top: 62px">
      <div class="title">
        <div style="font-size: 36px; color: #333333">骨科行业高效解决方案</div>
        <div style="font-size: 16px; color: #999999">
          杏 林 丹 心 是 您 降 低 管 理 成 本 ， 高 效 经 营 的 良 好 助 手
        </div>
      </div>
      <div class="content-four-bg">
        <el-tabs
          tab-position="left"
          style="height: 730px; width: 1134px; margin: auto; padding-top: 130px"
        >
          <el-tab-pane label="查找">
            <div class="headline">
              <div style="font-size: 34px; margin-top: 21px">按图索骥</div>
              <div style="font-size: 22px; margin-top: 36px">
                杏林丹心深挖行业痛点，深知作为一个行业新人，在加入骨科医疗器械行业从事工作伊始，需要极其漫长的时间进行学习、了解，极大的增加了工作时间成本，对企业来说，这也是需要付出的不必要的成本。杏林丹心推出“按图索骥”功能让任何一个新人在不太熟悉业务的情况下，依然使工作有条不紊的进行。<br /><br /><br /><br />极大的减少了新人工作的时间成本，也为企业减少了不必要的损失。
              </div>
              <div style="font-size: 22px; margin-top: 118px">
                解决方案关键词：
              </div>
              <div style="display: flex; margin-top: 30px">
                <div class="headlineList">按图索骥</div>
                <div class="headlineList">降级成本</div>
                <div class="headlineList">提升效率</div>
              </div>
            </div>
          </el-tab-pane>
          <el-tab-pane label="出库难、出库慢">
            <div class="headline">出库难、出库慢</div>
          </el-tab-pane>
          <el-tab-pane label="补货繁琐">
            <div class="headline">补货繁琐</div>
          </el-tab-pane>
          <el-tab-pane label="散件出库繁琐">
            <div class="headline">散件出库繁琐</div>
          </el-tab-pane>
          <el-tab-pane label="产品溯源">
            <div class="headline">产品溯源</div>
          </el-tab-pane>
          <el-tab-pane label="销售汇总">
            <div class="headline">销售汇总</div>
          </el-tab-pane>
        </el-tabs>
      </div>
    </div>
    <div class="content-five" style="margin-top: 62px">
      <div class="title">
        <div style="font-size: 36px; color: #333333">
          100+ 客户信任的骨科医疗器械SPD
        </div>
        <div style="font-size: 16px; color: #999999">
          帮 助 企 业 规 范 工 作 流 程 ， 高 效 管 理 库 存 、 财 务 ； 实 现
          产 品 注 册 证 和 企 业 许 可 证 的 审核 ； <br />序 列 号 追 溯 和 管
          理 ； 避 免 无 证 经 营 和 超 范 围 经 营 ，满 足 药 监 监 管 需 求 。
        </div>
      </div>
      <div class="content-five-bottom">
        <img
          src="@/assets/images/jl-l.png"
          alt=""
          class="content-five-picture"
        />
        <img
          src="@/assets/images/xr-l.png"
          alt=""
          class="content-five-picture"
        />
        <img
          src="@/assets/images/zaht-l.png"
          alt=""
          class="content-five-picture"
        />
      </div>
    </div>
    <div class="content-six" style="margin-top: 62px">
      <div class="title">最新动态</div>
      <el-tabs
        v-model="activeName"
        style="width: 1160px; margin: auto; padding-top: 32px"
      >
        <el-tab-pane label="公司新闻" name="first">
          <div style="display: flex; flex-wrap: wrap">
            <div
              class="content-six-content"
              v-for="(item, index) in list"
              :key="index"
            >
              <div style="display: flex">
                <div style="font-size: 30px; margin-right: 40px">
                  {{ item.time }} <br /><span
                    style="font-size: 18px; color: #999999"
                    >{{ item.year }}</span
                  >
                </div>
                <div style="font-size: 18px; font-weight: 700">
                  {{ item.title }}
                </div>
              </div>
              <div style="display: flex; align-items: center">
                <div
                  style="
                    width: 56px;
                    height: 1px;
                    background: #999999;
                    margin-right: 72px;
                  "
                ></div>
                <div style="font-size: 14px; color: #333333">
                  {{ item.content }}
                </div>
              </div>
            </div>
          </div>
        </el-tab-pane>
        <el-tab-pane label="行业动态" name="second">行业动态</el-tab-pane>
        <el-tab-pane label="政策法规" name="third">政策法规</el-tab-pane>
      </el-tabs>
    </div>
    <el-backtop target=".content-box" :bottom="100" style="width: 94px">
      <div
        style="
           {
            height: 100%;
            width: 100%;
            background-color: #f2f5f6;
            box-shadow: 0 0 6px rgba(0, 0, 0, 0.12);
            text-align: center;
            line-height: 40px;
            color: #1989fa;
          }
        "
      >
        返回顶部
      </div>
    </el-backtop>
  </div>
</template>
<script setup lang="ts">
const activeName = ref('first')
const list = reactive([
  {
    time: '06·01',
    year: '2022',
    title: '食药监局、国家卫计委发布《医疗器械临床试验机构条件和备案管理办法》',
    content:
      '为贯彻落实中共中央办公厅和国务院办公厅印发的《关于深化审评审批制度改革鼓励药品医疗...',
  },
  {
    time: '06·01',
    year: '2022',
    title: '食药监局、国家卫计委发布《医疗器械临床试验机构条件和备案管理办法》',
    content:
      '为贯彻落实中共中央办公厅和国务院办公厅印发的《关于深化审评审批制度改革鼓励药品医疗...',
  },
  {
    time: '06·01',
    year: '2022',
    title: '食药监局、国家卫计委发布《医疗器械临床试验机构条件和备案管理办法》',
    content:
      '为贯彻落实中共中央办公厅和国务院办公厅印发的《关于深化审评审批制度改革鼓励药品医疗...',
  },
  {
    time: '06·01',
    year: '2022',
    title: '食药监局、国家卫计委发布《医疗器械临床试验机构条件和备案管理办法》',
    content:
      '为贯彻落实中共中央办公厅和国务院办公厅印发的《关于深化审评审批制度改革鼓励药品医疗...',
  },
])
const performanceData = reactive([
  {
    picture: new URL('@/assets/images/mobileData.png', import.meta.url).href,
    data: '移动端下单<br/>查看汇总数据',
  },
  {
    picture: new URL('@/assets/images/roleData.png', import.meta.url).href,
    data: '为不同角色提供<br/>专业数据分析',
  },
  {
    picture: new URL('@/assets/images/associated.png', import.meta.url).href,
    data: '相关产品进行关联<br/>下单数据无遗漏',
  },
  {
    picture: new URL('@/assets/images/documents.png', import.meta.url).href,
    data: '不同单据在<br/>不同角色、流程中<br/>变换不同用途',
  },
])
const smartArkList = reactive([
  {
    picture: new URL('@/assets/images/perception.png', import.meta.url).href,
    content: '智能物联网技术',
  },
  {
    picture: new URL('@/assets/images/subprocesses.png', import.meta.url).href,
    content: '借货-消耗-归还-补货流程精细化管理',
  },
  {
    picture: new URL('@/assets/images/monitoring.png', import.meta.url).href,
    content: '严格监控丢失、漏费',
  },
  {
    picture: new URL('@/assets/images/LaborInspection.png', import.meta.url)
      .href,
    content: '降低劳动强度，提升效率',
  },
])
const downloadUrl = ref(
  new URL('@/assets/images/download.png', import.meta.url).href
)
</script>

<style lang="scss" scoped>
.content-box {
  // height: 100vh;
  // overflow-x: hidden;
  .content-box-one {
    position: relative;
    height: 600px;
    margin-top: 52px;
    background: url('../assets/images/phoneBackground.png');
    background-size: cover;

    .title {
      position: absolute;
      font-size: 36px;
      font-family: FZLanTingHei-DB-GBK;
      color: #333333;
      left: 60%;
      margin-top: 73px;
    }

    .subTitle {
      width: 500px;
      font-size: 16px;
      margin: 20px 0;
    }

    .content-box-bottom {
      display: flex;
      position: absolute;
      left: 60%;
      flex-wrap: wrap;
      // width: 100%;
      margin-top: 270px;
      width: 650px;

      .content-box-bottom-list {
        display: flex;
        width: 240px;
        font-size: 18px;
        margin-bottom: 20px;
        margin-right: 60px;
        color: #333333;
      }
    }

    .downloadBox {
      text-align: center;

      .download {
        width: 160px;
        height: 160px;
        margin-top: 20px;
      }
    }
  }

  .content-box-two {
    position: relative;
    height: 600px;
    // margin-top: 60px;
    background: url('../assets/images/contentBG2.png');
    background-size: cover;
    margin-top: 60px;

    .content-box-left {
      position: absolute;
      top: 92px;
      left: 330px;
      font-size: 42px;
      color: #333333;
    }

    .content-box-right {
      position: absolute;
      top: 72px;
      left: 1281px;
      color: #333333;

      .content-box-right1 {
        display: flex;
        align-items: center;
        margin-bottom: 40px;
      }
    }
  }

  .content-two {
    margin-top: 73px;

    .content-two-top {
      font-size: 42px;
      color: #333333;
      text-align: center;
    }

    .Product-pictures {
      margin: 41px 82px 109px 0px;
      width: 608px;
    }

    .content-two-right {
      width: 440px;
      height: 140px;
      margin-right: 37px;
      margin-top: 40px;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      border: 1px solid #d5d5d5;
    }
  }

  .content-three {
    position: relative;
    margin-top: 60px;

    .title {
      text-align: center;
    }

    .content-three-bg {
      height: 360px;
      background: url('../assets/images/contentBG3.png');
      background-size: cover;
      margin-top: 47px;
      color: #fff;

      .content-three-center {
        position: absolute;
        height: 135px;
        width: 79px;
        background: url('../assets/images/arrow.png') no-repeat;
        background-size: auto 100%;
        left: 50%;
        top: 50%;
        transform: translate(50%, 2%);
      }
    }

    .content-three-left {
      margin-left: 0;
      font-size: 18px;

      &::before {
        content: '';
        display: inline-block;
        width: 8px;
        height: 8px;
        background-color: #fff;
        border-radius: 50%;
        margin-right: 6px;
      }
    }
  }

  .content-four {
    color: #fff;

    .title {
      text-align: center;
    }

    .content-four-bg {
      height: 907px;
      background: url('../assets/images/contentBG4.png');
      background-size: cover;
      margin-top: 47px;
      color: #fff;

      .headline {
        margin-left: 77px;
      }

      .headlineList {
        width: 160px;
        height: 40px;
        background: #3c528b;
        line-height: 40px;
        text-align: center;
        margin-right: 30px;
      }

      ::v-deep(.el-tabs--left .el-tabs__item.is-left) {
        color: #fff;
      }

      ::v-deep(.el-tabs__item.is-active) {
        color: #409eff !important;
      }

      ::v-deep(.el-tabs--left .el-tabs__item.is-left) {
        margin-bottom: 49px;
        font-size: 22px;
      }
    }
  }

  .content-five {
    .title {
      margin-left: 320px;
    }

    .content-five-bottom {
      display: flex;
      justify-content: space-around;
      margin-top: 76px;
    }

    .content-five-picture {
      height: 88px;
    }
  }

  .content-six {
    height: 670px;
    background: #f6f6f6;
    margin-top: 96px;
    background: url('../assets/images/sixBG.png');
    background-size: cover;

    .title {
      text-align: center;
      font-size: 40px;
      color: #333333;
      font-weight: bold;
      padding-top: 60px;
    }

    .content-six-content {
      box-sizing: border-box;
      width: 560px;
      height: 194px;
      opacity: 0.63;
      background: #fff;
      margin-right: 20px;
      margin-bottom: 20px;
      padding: 42px 66px;
    }

    ::v-deep(.el-tabs__nav-wrap::after) {
      background-color: #f6f6f6;
    }
  }
}
</style>
