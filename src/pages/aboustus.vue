<template>
  <div class="">
    <div class="top">
      <el-image
        :src="aboutUs"
        style="width: 100%"
        fit="cover"
        class="top-content"
      />
    </div>
    <div style="background: #f2f2f2">
      <div class="new-one">
        <ul class="new-one-left">
          <!-- <a href="#miao"> -->
          <li
            v-for="item in newList"
            :key="item.id"
            :class="index == item.id ? 'active' : ''"
            @click="change(item.id)"
          >
            <a :href="'#' + item.id">{{ item.title }}</a>
          </li>
          <!-- </a> -->
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
            <span v-if="index == 1">公司介绍</span>
            <span v-if="index == 2">发展历程</span>
            <span v-if="index == 3">管理团队</span>
            <span v-if="index == 4">企业文化</span>
          </el-breadcrumb-item>
        </el-breadcrumb>
      </div>
    </div>

    <div class="content">
      <div class="con_title" id="1">公司介绍</div>
      <div class="con_picture">
        山西布莱德瑞克科技有限公司2015年成立于中国太原，公司坐落于山西综改示范区太原学府园区发展路2号联合大厦B座4单元18层。是国内医疗智慧管理领域的领先厂商，
        专注于为医疗机构、政府主管部门和医药企业、金融机构提供医疗智慧管理“软件+大数据+智能化”的全域产品和服务。我们专注骨科医疗器械等线上智能管理系统的开发与
        推广，是致力于解决骨科医疗器械运营过程中所有问题的一家科技创新公司。
        <br /><br /><br /><br />
        2017年与山西国药集团合作，打造了骨科互联网平台——国药骨科智能交易平台（杏林丹心）为国药填补了高值耗材的订单流转系统。2018年投入使用并推广的骨科智能物
        流管理系统为骨科经营提供实际需求与软件结合，打造企业全过程一体化的管理系统。打破各部门各区域之间沟通和协作的壁垒，建立规范、便捷高效的业务流程，实现采购、
        库房、销售、财务等所有环节的无缝隙对接管理，添补国内行业软件的空白。
      </div>
    </div>
    <div
      class="content-one"
      style="display: flex; justify-content: space-around"
    >
      <div>
        <div
          style="font-size: 36px; margin-bottom: 104px; padding-top: 41px"
          :id="'2'"
        >
          发展历程
        </div>
        <div v-for="(item, index) in developmentCourse" :key="index">
          <div style="display: flex; align-items: center">
            <div style="margin-right: 52px">{{ item.title }}</div>
            <div style="font-size: 16px; color: #dda14f">{{ item.time }}</div>
          </div>
          <div
            style="
              width: 55px;
              height: 1px;
              background: #ffffff;
              margin: 50px 0;
            "
            v-if="item.flag"
          ></div>
        </div>
      </div>
      <div style="margin-left: 114px; margin-top: 126px">
        <div
          class="content-one-right"
          v-for="(item, index) in course"
          :key="index"
        >
          <div
            style="
              height: 130px;
              padding-left: 80px;
              background: #fff;
              color: #333333;
              padding-right: 20px;
              padding-top: 14px;
              font-size: 16px;
            "
          >
            {{ item.title }}
          </div>
          <div class="content-one-line"></div>
          <div class="content-one-png">
            <img :src="item.img" alt="" style="width: 19px" />
          </div>
        </div>
      </div>
    </div>
    <div class="content" style="height: 534px">
      <div class="con_title" id="3">公司团队</div>
      <div style="display: flex; justify-content: center">
        <div
          class="content-top"
          :class="index == indexTeam ? 'activeTeam' : ''"
          v-for="(item, index) in team"
          :key="index"
          @click="changeTeam(index)"
        >
          {{ item.name }}
        </div>
      </div>
      <div class="content-details" v-if="indexTeam == 0">
        <div style="font-size: 30px; color: #0a357d">郭爱军</div>
        <div
          style="width: 71px; height: 1px; background: #0a357d; margin: 13px 0"
        ></div>
        <div style="font-size: 18px; padding-bottom: 44px">总经理</div>
        <div class="content-details-bottom">
          2017年11月入职山西布莱德瑞克科技有限公司并出任山西布莱德瑞克科技有限公司执行董事和产品经理职务。中国政法大学
          法学学士。1987年至1991年服役于63军52940部队，从事无线电弱电管理在部队期间荣获3次嘉奖。1996年进入迎泽区政
          府，在迎泽区质量监督局任主任科员，从事流通领域中的产品质量监管，并多年关注供应链上下游的数据溯源追踪，负责辖区
          特种设备的日常监管。2015年指导山西布莱德瑞克科技有限公司开发并上线使用电梯监管平台。2016年为医院医疗器械设立
          电子台账，时时监控医疗器械使用情况。
        </div>
      </div>
    </div>
    <div class="content-two">
      <div>
        <div
          style="font-size: 36px; font-weight: 700; margin-bottom: 37px"
          id="4"
        >
          企业文化
        </div>
        <div
          style="margin-bottom: 48px"
          v-for="(item, index) in culture"
          :key="index"
        >
          <div style="font-size: 24px; color: #0a357d">{{ item.titel }}</div>
          <div style="font-size: 16px; color: #333333">{{ item.subtitle }}</div>
        </div>
      </div>
      <div class="content-bg"></div>
      <div class="content-bg-picture">
        <img src="@/assets/images/sub01f_bg2.png" alt="" style="height: 100%" />
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { HomeFilled, ArrowRight } from '@element-plus/icons-vue'
import aboutUs from '@/assets/images/aboutUs.png'
const newList = reactive([
  {
    title: '公司介绍',
    id: 1,
  },
  {
    title: '发展历程',
    id: 2,
  },
  {
    title: '管理团队',
    id: 3,
  },
  {
    title: '企业文化',
    id: 4,
  },
])
const developmentCourse = reactive([
  {
    title: '发展历程',
    time: '2015-2016',
    flag: true,
  },
  {
    title: '规范调整',
    time: '2017-2018',
    flag: true,
  },
  {
    title: '创新发展',
    time: '2019-至今',
    flag: false,
  },
])
const team = reactive([
  { name: '总经理' },
  { name: '技术团队' },
  { name: '业务团队' },
  { name: '服务团队' },
])
const index = ref(1)
const indexTeam = ref(0)
const culture = reactive([
  {
    titel: '愿景',
    subtitle: '成为国内医疗SPD供应链管理领军企业',
  },
  {
    titel: '使命',
    subtitle: '以“持续推进医疗行业科学化管理”为使命',
  },
  {
    titel: '价值观',
    subtitle: '开放包容、忠诚奉献、团结合作、学习创新',
  },
])
const course = reactive([
  {
    title:
      ' 2015年12月25日响应国家互联网+的号召，法人刘麒与股东梁磊新成立山西布莱德瑞克商务信息咨询有限公司，主要从事软件开发。2016年与太原艾亿时代科技有限公司联合开发杏林丹心平台。',
    img: new URL('@/assets/images/TeamBuilding.png', import.meta.url).href,
  },
  {
    title:
      ' 2017年3月更名为山西布莱德瑞克科技有限公司，杏林丹心商标转入山西布莱德瑞克科技有限公司，同年公司自主研发杏林丹心WMS、OMS系统上线。2017年12月与太原理工大学进行产学研合作开发新产品；并与国药集团山西有限公司器械分公司在双塔东街成立山西第一家“国药骨科器械配送互联网平台”；为多家企业解决物流仓储等问题。',
    img: new URL('@/assets/images/dataList.png', import.meta.url).href,
  },
  {
    title:
      ' 2018年成为国药国药集团山西有限公司“长期战略合作伙伴”，并在运城开设第二家“国药骨科器械配送互联网平台”。2019年与国药山西阳泉医药有限公司搭建阳泉“国药骨科器械配送互联网平台”，为江苏金鹿集团医疗器械有限公司山西的配送公司建立智能仓储物流。2020年成功认定为国家高新技术企业。',
    img: new URL('@/assets/images/userfk.png', import.meta.url).href,
  },
])
const change = (id: number) => {
  index.value = id
}
const changeTeam = (id: number) => {
  indexTeam.value = id
}
</script>

<style lang="scss" scoped>
.top {
  height: 500px;
  overflow: hidden;

  // width: 1889px;
  .top-content {
    height: 100%;
  }
}

.new-one {
  display: flex;
  height: 90px;
  width: 1440px;
  margin: auto;

  .navigation-bar {
    line-height: 90px;
    // margin-left: 48px;
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

    // margin-left: 240px;
    li {
      display: flex;
      align-items: center;
      margin-right: 71px;
    }
  }
}

.content {
  width: 100%;
  height: 509px;
  box-sizing: border-box;
  color: #333333;

  .con_title {
    text-align: center;
    font-size: 36px;
    margin-top: 60px;
    margin-bottom: 30px;
  }

  .con_picture {
    height: 340px;
    width: 1440px;
    background: url('@/assets/images/usbg.png');
    background-size: cover;
    margin: auto;
    box-sizing: border-box;
    padding-top: 58px;
    padding-left: 72px;
    padding-right: 72px;
    font-size: 16px;
  }

  .content-top {
    width: 184px;
    height: 53px;
    line-height: 53px;
    text-align: center;
    margin-right: 51px;
    background: #ffffff;
    border: 1px solid #e2e2e2;
    border-radius: 27px;

    > :last-child {
      margin-right: 0;
    }
  }

  .activeTeam {
    background: #ededed;
  }

  .content-details {
    height: 401px;
    width: 1440px;
    // background-color: red;
    color: #333333;
    // details.png
    margin: auto;
    background: url('@/assets/images/details.png');
    background-size: cover;
    padding-top: 87px;
    padding-left: 71px;
    box-sizing: border-box;

    .content-details-bottom {
      width: 968px;
      border-top: 1px solid #b0b0b0;
      padding-top: 25px;
    }
  }
}

.content-one {
  // height: 660px;
  height: 660px;
  width: 100%;
  color: #ffffff;
  font-size: 24px;
  background: url('@/assets/images/ustowbg.png');
  background-size: cover;

  .content-one-right {
    position: relative;
    width: 965px;

    // display: flex;
    .content-one-left {
      position: absolute;
      right: 0;
    }
  }

  .content-one-line {
    width: 673px;
    height: 1px;
    background: #e2e2e2;
    padding-left: 22px;
  }

  .content-one-png {
    position: absolute;
    left: -30px;
    top: 28px;
    width: 59px;
    height: 59px;
    background: #fff;
    border-radius: 50%;
    line-height: 59px;
    text-align: center;
    box-shadow: 0px 27px 40px 0px rgba(10, 53, 125, 0.35);
  }
}

.content-two {
  display: flex;
  justify-content: space-between;
  position: relative;
  width: 1440px;
  height: 506px;
  margin: auto;
  box-sizing: border-box;
  padding-top: 60px;

  .content-bg {
    width: 842px;
    height: 446px;
    background: url('@/assets/images/sub01f_bg.png');
    background-size: cover;
  }

  .content-bg-picture {
    position: absolute;
    bottom: 0px;
    height: 113px;
    width: 1440px;
    z-index: -10;
    overflow: hidden;
  }
}
</style>
