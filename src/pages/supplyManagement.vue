<template>
  <div>
    <div class="OMS-top">
      <div style="font-size: 60px; margin-bottom: 10px">智能采购管理系统</div>
      <div style="font-size: 26px">
        有效的为企业提供进出库的便捷方式，并且可以通过
      </div>
      <div style="font-size: 26px">平常的系统录入可以进行直观的展示。</div>
    </div>
    <navigationBar @change="change" />
    <div
      id="1"
      style="margin: 98px 278px; display: flex; justify-content: space-between"
    >
      <div class="OMS-one" v-for="item in list" :key="item.id">
        <img :src="item.pic" alt="" class="OMS-image" />
        <div>{{ item.title }}</div>
        <div>{{ item.name }}</div>
      </div>
    </div>
    <productValue id="2" />
    <div id="3" style="margin-top: 70px">
      <div style="font-size: 26px; color: #333333; text-align: center">
        产品功能
      </div>
      <div class="oms-two">
        <div class="oms-two-box" v-for="item in productList" :key="item.id">
          <img :src="item.pic" alt="" class="oms-two-img" />
          <div style="font-size: 24px; margin-top: 40px; margin-bottom: 37px">
            {{ item.title }}
          </div>
          <div style="font-size: 18px; line-height: 39px; text-align: left">
            {{ item.describe }}
          </div>
        </div>
      </div>
    </div>
    <div style="width: 1440px; margin: auto; margin-bottom: 188px" id="4">
      <img
        src="@/assets/images/OMS01/bottompng.png"
        alt=""
        style="width: 100%"
      />
    </div>
  </div>
</template>
<script setup lang="ts">
const list = reactive([
  {
    id: 1,
    pic: new URL('@/assets/images/procurement/one.png', import.meta.url).href,
    title: '数字化',
    name: 'Digital',
  },
  {
    id: 2,
    pic: new URL('@/assets/images/procurement/two.png', import.meta.url).href,
    title: '智能化',
    name: 'Intelligent',
  },
  {
    id: 3,
    pic: new URL('@/assets/images/procurement/three.png', import.meta.url).href,
    title: '云端',
    name: 'Cloud',
  },
  {
    id: 4,
    pic: new URL('@/assets/images/procurement/four.png', import.meta.url).href,
    title: '专业化',
    name: 'Professional',
  },
  {
    id: 5,
    pic: new URL('@/assets/images/procurement/five.png', import.meta.url).href,
    title: '网络化',
    name: 'Networking',
  },
])
const productList = reactive([
  {
    id: 1,
    pic: new URL('@/assets/images/procurement/productOne.png', import.meta.url)
      .href,
    title: '供应商全生命周期管理系统',
    describe: `优质的长期的供应商是能够直接影响采购成
          本及企业采购战略落地的。而供应商管理的
          终极路径是建立企业自己的供应商私域流量
          池。公域和私域双空间联通，构建组织专属
          的供应商资源池，实现供应商资源不以人员
          离职而流失，实现供应商全生命周期管理。
          最大程度保护企业生态数据资产。`,
  },
  {
    id: 2,
    pic: new URL('@/assets/images/procurement/productTwo.png', import.meta.url)
      .href,
    title: '需求智能分发引擎',
    describe: `支持多种需求类型管理，标准型、金额型、
          数量型、框架型、自采型……以计划驱动执
          行，通过智能分发引擎，帮助企业建立虚拟
          的采购共享中心，把需求高效分发，直接抵
          达最小组织单位，让适合的人解决适合的事，
          大大提升运营效率。`,
  },
  {
    id: 3,
    pic: new URL(
      '@/assets/images/procurement/productThree.png',
      import.meta.url
    ).href,
    title: '智能对账系统',
    describe: `根据企业管理诉求、业务对账周期，灵活预
          设自动对账规则；自动按时生成清晰的对账
          单据、对账明细，自动核验对账单信息，并
          提供对账结果。可以与ERP和OA深度连接，
          数据同步，帮助财务人员快速高效完成对账
          审核，智能合规，灵活清晰，大大节省人工
          时间，降低出错率。`,
  },
  {
    id: 4,
    pic: new URL('@/assets/images/procurement/productFour.png', import.meta.url)
      .href,
    title: 'BI数据报表支持模块',
    describe: `采购全维度BI数据可视化应用，一键简单使
          用，无需任何技术经验；让采购业务人员及
          管理人员也能轻松实现海量数据可视化分析。
          轻松构建自助式的BI分析平台，真实洞察业
          务背后的趋势，灵活的选择操作，图表、报
          表一键生成，大幅降低分析难度，支撑业务
          决策。`,
  },
  {
    id: 5,
    pic: new URL('@/assets/images/procurement/productFive.png', import.meta.url)
      .href,
    title: '战略采购寻源系统',
    describe: `严格准入的海量供应商，千余种采购品类，
           选择多才能遇见“最好的”独家的BOM式
          询价，让众多供应商的报价有依据，比价有
          道理；多种竞价模式，实时查看供应商报价
          走向，最大化降低采购成本；让企业采购战
          略找到最优的落地路径。`,
  },
  {
    id: 6,
    pic: new URL('@/assets/images/procurement/productSix.png', import.meta.url)
      .href,
    title: '库存管理系统',
    describe: `采供双方实时掌握备库情况和消耗记录，动
          态反映欠交欠料情况，对应FCST需求；预
          设补发预警机制，缺货提醒自动触发；实现
          企业和供应商之间的物流信息协同，建立敏
          捷高效的物流配送体系，物流节点状态可视
          化，进度实时追踪；实时有效管控库存，提
          升工作效率和准确性，降低企业成本。`,
  },
])
const index = ref<number>()
const change = (id: number) => {
  index.value = id
}
</script>
<style lang="scss" scoped>
.OMS-top {
  height: 500px;
  background: url('@/assets/images/procurement/banner-icon.png');
  background-size: cover;
  color: #ffffff;
  box-sizing: border-box;
  padding-top: 135px;
  padding-left: 291px;
}
.OMS-one {
  font-size: 28px;
  color: #333333;
  width: 212px;
  text-align: center;
  .OMS-image {
    width: 100%;
    margin-bottom: 40px;
  }
}
.oms-two {
  margin: 50px 240px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  // > :nth-child(3n) {
  //   margin-right: 0 !important;
  // }
  .oms-two-box {
    width: 374px;
    height: 454px;
    background: #ffffff;
    border: 1px solid #e3e3e3;
    // background-color: aqua;
    text-align: center;
    padding: 42px 33px;
    // margin-right: 45px;
    margin-block: 40px;
    .oms-two-img {
      width: 95px;
    }
  }
}
</style>
