<template>
  <div>
    <div class="top">
      <img
        src="@/assets/images/introduction/industry.png"
        alt=""
        class="top-content"
      />
      <img
        src="@/assets/images/introduction/banner_circle2.png"
        alt=""
        class="top-animation"
      />
      <img
        src="@/assets/images/introduction/banner_circle2.png"
        alt=""
        class="top-animation-one"
      />
    </div>
    <div style="background: #f2f2f2">
      <div class="new-one">
        <ul class="new-one-left">
          <li
            v-for="item in newList"
            :key="item.id"
            :class="index == item.id ? 'active' : ''"
            @click="change(item.id)"
          >
            <a :href="'#' + item.id">{{ item.title }}</a>
          </li>
        </ul>
        <div
          style="
            height: 90px;
            line-height: 90px;
            margin-left: 17px;
            margin-right: 15px;
          "
        >
          <el-icon><HomeFilled /></el-icon>
        </div>
        <el-breadcrumb :separator-icon="ArrowRight" class="navigation-bar">
          <el-breadcrumb-item>首页</el-breadcrumb-item>
          <el-breadcrumb-item>新闻中心</el-breadcrumb-item>
          <el-breadcrumb-item>
            <span v-if="index == 1">产品背景</span>
            <span v-if="index == 2">SPD供应链运营服务</span>
            <span v-if="index == 3">RFID高值耗材智能柜</span>
            <span v-if="index == 4">流程介绍</span>
          </el-breadcrumb-item>
        </el-breadcrumb>
      </div>
    </div>
    <div class="introduction-one">
      <div class="title" id="1">行业痛点</div>
      <div class="introduction-content">
        <div style="display: flex" class="introduction-content-list">
          <div
            class="introduction-content-top"
            v-for="(item, index) in Industry"
            :key="index"
          >
            <div class="introduction-content-png">
              <img :src="item.img" alt="" />
            </div>
            <div
              style="
                margin-top: 23px;
                margin-bottom: 43px;
                font-size: 24px;
                font-weight: 700;
              "
            >
              {{ item.title }}
            </div>
            <div style="margin: 0 30px; font-size: 16px">
              {{ item.content }}
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="introduction-two">
      <div class="title" id="2">SPD供应链运营服务</div>
      <div class="introduction-two-content">
        是 一 款 为 骨 科 经 营 企 业 提 供 高 效 、 便 捷 的 定 制 化 的 流 程
        管 理 软 件 。 旨 在 帮 助 企 业 规 范 工 作 流 程 ， 高 效 管 理 库 存
        、 财 务 ； 实 现 产 品 注 册 证 和 企 业 许 可 证 的 审 核 ； 序 列 号
        追 溯 和 管 理 ； 避 免 无 证 经 营 和 超 范 围 经 营 。 满 足 药 监 监
        管 需 求 。杏 林 丹 心 是 您 降 低 管 理 成 本 ， 高 效 经 营 的 良 好
        助 手 。
      </div>
    </div>
    <div class="introduction-three">
      <div class="title">九大优势</div>
      <div class="introduction-content" style="display: flex">
        <div class="introduction-content-list">
          <div
            class="introduction-content-top"
            v-for="(item, index) in advantage"
            :key="index"
          >
            <div class="introduction-content-png">
              <img :src="item.img" alt="" />
            </div>
            <div
              style="
                margin-top: 23px;
                margin-bottom: 43px;
                font-size: 24px;
                font-weight: 700;
              "
            >
              {{ item.title }}
            </div>
            <div style="margin: 0 30px; font-size: 16px">
              {{ item.content }}
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="introduction-four"></div>
    <div class="introduction-five" id="3">
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
          <div style="margin-right: 280px; color: #333333; font-size: 24px">
            高值耗材智能柜，可以解决临床科室耗材管控中丢失、漏费等重点难点问题，极大地降低医护人员日常耗材管理的劳动强度，更好地服务于临床一线，提升医疗服务质量和医院整体经济运行效益。
          </div>
          <div style="margin-top: 25px; display: flex; flex-wrap: wrap">
            <div
              class="content-two-right"
              v-for="(item, index) in smartArkList"
              :key="index"
            >
              <img
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
    <div class="introduction-six">
      <div class="title">RFID高值耗材智能柜-流程优点</div>
      <div
        style="display: flex; width: 1440px; margin: auto"
        class="introduction-six-box"
      >
        <div
          class="introduction-six-content"
          v-for="(item, index) in advantagesProcess"
          :key="index"
        >
          <div class="introduction-six-centent">
            <div class="introduction-six-png">
              <img :src="item.img" alt="" />
            </div>
            <div style="font-size: 18px; color: #333333">{{ item.title }}</div>
          </div>
        </div>
      </div>
    </div>
    <div class="introduction-seven" id="4">
      <div class="title">流程介绍</div>
      <div class="introduction-seven-top">
        杏林丹心是帮助医院实现与外部供应商的专业化分工，协同管理的供应链物流管理模式，让医院更好地进行
        内外数据对接，信息传递，提高供应链运营质量。供应链系统互通互联平台，能显著优化物流中心管理主体
        和商业供应模式，解决院内外业务管理问题。在保障日常科室消耗供给的基础上，降低医院管理成本，减轻
        医护人员工作量。有效避免库房耗材积压，降低出错率，提升物资耗材精细化管理水平。
      </div>
      <div class="sequenceNumber">01采购环节</div>
      <div class="sequenceNumber01">
        <img src="@/assets/images/introduction/technological.png" alt="" />
      </div>
      <div class="sequenceNumber">02发货平台</div>
      <div class="sequenceNumber02">
        <div class="sequenceNumber02-content">
          <div style="width: 160px; height: 160px">
            <img
              src="@/assets/images/introduction/process2.png"
              alt=""
              style="width: 100%"
            />
            <div style="text-align: center; margin-top: 30px">扫码出库</div>
          </div>
          <div
            class="sequenceNumber02-bottom"
            v-for="(item, index) in deliveryPlatform"
            :key="index"
          >
            {{ item.name }}
          </div>
        </div>
      </div>
      <div class="sequenceNumber">03配送环节</div>
      <div
        style="
          width: 1010px;
          margin: auto;
          margin-top: 20px;
          margin-bottom: 140px;
        "
      >
        <img
          src="@/assets/images/introduction/distribution.png"
          style="width: 100%"
        />
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { HomeFilled, ArrowRight } from '@element-plus/icons-vue'
import police from '@/assets/images/introduction/police.png'
import barber from '@/assets/images/introduction/barber.png'
import documentation from '@/assets/images/introduction/documentation.png'
import BigData from '@/assets/images/introduction/BigData.png'
import phone from '@/assets/images/introduction/phone.png'
import PersonnelAccess from '@/assets/images/introduction/PersonnelAccess.png'
import scanCode from '@/assets/images/introduction/scanCode.png'
import GSP from '@/assets/images/introduction/GSP.png'
import RightsManagement from '@/assets/images/introduction/RightsManagement.png'
import TheForm from '@/assets/images/introduction/TheForm.png'
import FinancialReconciliation from '@/assets/images/introduction/FinancialReconciliation.png'
import SingleDataAnalysis from '@/assets/images/introduction/SingleDataAnalysis.png'
import perception from '@/assets/images/perception.png'
import subprocesses from '@/assets/images/subprocesses.png'
import monitoring from '@/assets/images/monitoring.png'
import LaborInspection from '@/assets/images/LaborInspection.png'
import processImg from '@/assets/images/introduction/process.png'
import roots from '@/assets/images/introduction/roots.png'
import InventoryApplication from '@/assets/images/introduction/InventoryApplication.png'
import HIS from '@/assets/images/introduction/HIS.png'
import timeData from '@/assets/images/introduction/Real-timeData.png'
const newList = reactive([
  {
    title: '产品背景',
    id: 1,
  },
  {
    title: 'SPD供应链运营服务',
    id: 2,
  },
  {
    title: 'RFID高值耗材智能柜',
    id: 3,
  },
  {
    title: '流程介绍',
    id: 4,
  },
])
const Industry = reactive([
  {
    img: police,
    title: '药监局频繁的“飞行检查”',
    content:
      '根据《药品医疗器械飞行检查办法》《国家食品药品监督管理总局令第14号》第八条，有七种情况的，食品药品监督管理部门可以开展药品医疗器械飞行检查。',
  },
  {
    img: barber,
    title: '缺少专业库管人才',
    content:
      '面对种类繁多的骨科医疗器械，经验丰富、专业的库管都存在出错的情况，何况是行业新人，而新人的培养成本又太过巨大，因此一名专业的库管人才是行业严重的痛点。',
  },
  {
    img: documentation,
    title: '烦恼于繁琐庞大的手抄单据',
    content:
      '由于行业内部所需产品太过繁杂，因此在进行进货、借货、调拨、验货、收货等操作时，会产生繁琐庞大的手抄单据，极大的增加了时间成本，也不可避免的会出现很多错误。',
  },
])
const advantage = reactive([
  {
    img: BigData,
    title: '大数据',
    content:
      '对产品器械的信息进行了数据化管理。将生产厂家多个部门管理的数据进行汇总。如生产部的掌握产品参数、招标部掌握的招标价格、市场宣传部掌握的产品宣传图片操作使用视频。方便物流平台，经销商和医院临床。',
  },
  {
    img: phone,
    title: '手机下单',
    content:
      '器械商城，经销商和医院临床全方位了解产品器械的信息，改变以往需要无数各电话才能了解的信息；界面相关产品的关联，使需求人员下单时无遗漏，为临床手术保驾护航；可随时了解产品器械的物流信息。',
  },
  {
    img: PersonnelAccess,
    title: '专业技术人员',
    content:
      '杏林丹心将产品器械的属性进行专业的分类组配。解决了传统的库房人员需熟悉了解产品才能开展工作的局面。实现了电子化管理，增速人员的工作效率。',
  },
  {
    img: scanCode,
    title: '扫码溯源管理',
    content:
      '对仓库内所有的产品实施条码管理，仓库管理人员出便捷。解脱了出入库手工填写单据抄编号，管理纸质单据的烦恼。',
  },
  {
    img: GSP,
    title: 'GSP合规',
    content:
      '传统模式的管理忽略了国家的法律法规，经常因为疏忽大意被药监局查处，造成不必要的损失。杏林丹心系统从源头到经营过程全过程进行控制，使其行为规范符合国家法律法规。',
  },
  {
    img: RightsManagement,
    title: '权限控制',
    content:
      '杏林丹心的各级权限的控制，使多人多角色的同时操作一款软件，让数据更真实，信息更私密，工作更便捷。',
  },
  {
    img: TheForm,
    title: '单据流转',
    content:
      '杏林丹心的单据是在不同角色不同流程中，同一单据变换不同的用途。当借货还回的产品产生销售，销售单会自动转变为物流平台的采购单，转到生产厂家为订货单，流转回物流平台为入库单。',
  },
  {
    img: FinancialReconciliation,
    title: '账务管理',
    content:
      '杏林丹心一键试发起对账，让使用的人免去了对账的烦恼。对未到账的客户可采取关闭试功能，让经营更安全。',
  },
  {
    img: SingleDataAnalysis,
    title: '数据分析',
    content:
      '杏林丹心为不同的角色提供不同的数据分析。让生产厂家有计划生产，生产的产品适应市场需求；让物流平台的仓储产品无积压，不断货；让经销商和临床医院使用不受限。',
  },
])
const smartArkList = reactive([
  {
    picture: perception,
    content: 'RFID和物联网技术',
  },
  {
    picture: subprocesses,
    content: '借货-消耗-归还-补货流程精细化管理',
  },
  {
    picture: monitoring,
    content: '严格监控丢失、漏费',
  },
  {
    picture: LaborInspection,
    content: '降低劳动强度，提升效率',
  },
])
const advantagesProcess = reactive([
  {
    img: processImg,
    title: '对骨科多品种的植入高值耗材进行精细化管理',
  },
  {
    img: roots,
    title: '通过入库、出库、记录对产品进行溯源管理',
  },
  {
    img: InventoryApplication,
    title: '实时盘点，对耗材进行有效管理',
  },
  {
    img: HIS,
    title: '便捷销售，嵌入医院HIS系统，使销售一键完成',
  },
  {
    img: timeData,
    title: '生产厂家、供应商实时对接数据',
  },
])
const deliveryPlatform = reactive([
  {
    name: '采购管理',
  },
  {
    name: '库存管理',
  },
  {
    name: '盘点管理',
  },
  {
    name: '订单管理',
  },
  {
    name: '账单管理',
  },
])
const index = ref(1)

const change = (id: number) => {
  index.value = id
}
</script>

<style lang="scss" scoped>
.top {
  height: 500px;
  position: relative;
  min-width: 1903px;
  .top-content {
    width: 100%;
  }
  .top-animation {
    position: absolute;
    top: 142px;
    left: 999px;
    width: 251px;
    animation: fadenum 8s infinite;
  }
  .top-animation-one {
    position: absolute;
    top: 105px;
    left: 1328px;
    width: 190px;
    animation: fadenum1 8s infinite;
  }
  @keyframes fadenum {
    100% {
      transform: rotate(360deg);
    }
  }
  @keyframes fadenum1 {
    100% {
      transform: rotate(-360deg);
    }
  }
}
.new-one {
  display: flex;
  height: 90px;
  width: 1440px;
  margin: auto;

  .navigation-bar {
    line-height: 90px;
  }
  .active {
    border-bottom: 2px solid #0087ff;
  }
  .new-one-left {
    display: flex;
    height: 90px;
    width: 70%;
    border-right: 1px solid #d6d6d6;
    line-height: 90px;

    li {
      display: flex;
      align-items: center;
      margin-right: 71px;

      a {
        text-decoration: none;
        color: #333;
      }
    }
  }
}
.introduction-one {
  .title {
    height: 150px;
    width: 100%;
    line-height: 150px;
    text-align: center;
    font-size: 36px;
  }
  .introduction-content {
    width: 1440px;
    margin: auto;
    .introduction-content-top {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 450px;
      height: 420px;
      border: 1px solid #d5d5d5;
      margin-right: 45px;
    }
    .introduction-content-png {
      width: 134px;
      height: 134px;
      img {
        width: 100%;
      }
    }
    .introduction-content-list {
      display: flex;
      > :last-child {
        margin-right: 0;
      }
    }
  }
}
.introduction-two {
  height: 500px;
  width: 100%;
  margin-top: 60px;
  background: url('@/assets/images/introduction/banner_detail.png');
  background-size: cover;
  text-align: center;
  .title {
    box-sizing: border-box;
    padding: 60px 0;
    font-size: 36px;
    color: #ffffff;
  }
  .introduction-two-content {
    width: 815px;
    margin-left: 277px;
    font-size: 24px;
    color: #ffffff;
    text-align: left;
  }
}
.introduction-three {
  .title {
    height: 150px;
    width: 100%;
    line-height: 150px;
    text-align: center;
    font-size: 36px;
  }
  .introduction-content {
    width: 1440px;
    margin: auto;
    .introduction-content-top {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 450px;
      height: 420px;
      border: 1px solid #d5d5d5;
      margin-right: 42px;
      margin-bottom: 50px;
    }
    .introduction-content-png {
      width: 134px;
      height: 134px;
      img {
        width: 100%;
      }
    }
    .introduction-content-list {
      display: flex;
      flex-wrap: wrap;
      > :nth-child(3n) {
        margin-right: 0;
      }
    }
  }
}
.introduction-four {
  height: 500px;
  background: url('@/assets/images/introduction/fourBG.png');
  background-size: cover;
}
.introduction-five {
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
.introduction-six {
  height: 540px;
  width: 100%;
  background: #ededed;
  color: #ffffff;
  .title {
    box-sizing: border-box;
    padding-top: 60px;
    margin-bottom: 93px;
    text-align: center;
    font-size: 36px;
    color: #333333;
  }
  .introduction-six-content {
    display: flex;
    justify-content: center;
    margin-right: 160px;
    .introduction-six-centent {
      flex-direction: column;
      justify-content: center;
      align-items: center;
      display: flex;
      height: 256px;
    }
    .introduction-six-box {
      display: flex;
      width: 1440px;
      margin: auto;
      > :last-child {
        margin-right: 0;
      }
    }
    .introduction-six-png {
      height: 160px;
      width: 160px;
      margin-bottom: 30px;
      img {
        width: 100%;
      }
    }
  }
}
.introduction-seven {
  color: #333333;
  .title {
    height: 154px;
    width: 100%;
    line-height: 154px;
    text-align: center;
    font-size: 36px;
  }
  .introduction-seven-top {
    width: 1317px;
    font-size: 24px;
    margin: auto;
    font-size: 24px;
  }
  .sequenceNumber {
    padding-left: 8%;
    font-size: 28px;
    color: #333333;
    margin-top: 66px;
  }
  .sequenceNumber01 {
    width: 1259px;
    height: 335px;
    margin: auto;
    padding-top: 60px;
    img {
      width: 100%;
    }
  }
  .sequenceNumber02 {
    width: 100%;
    min-width: 1440px;
    height: 342px;
    background: #ededed;
    margin-top: 29px;
    .sequenceNumber02-content {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 1440px;
      height: 100%;
      margin: auto;
    }
    .sequenceNumber02-bottom {
      width: 95px;
      height: 95px;
      line-height: 95px;
      text-align: center;
      font-size: 20px;
      background: #b4d5f1;
      // opacity: 0.24;
      border-radius: 50%;
      // font-weight: 700;
      color: #333333;
    }
  }
}
</style>
