<template>
  <div class="home">
    <div class="OMS-top">
      <div style="font-size: 60px; margin-bottom: 10px">WMS管理系统</div>
      <div style="font-size: 26px">
        有效控制并跟踪仓库业务的物流和成本管理全过程
      </div>
      <div style="font-size: 26px">实现或完善企业的仓储信息管理</div>
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
            <span v-if="index == 1">产品优势</span>
            <span v-if="index == 2">产品应用价值</span>
            <span v-if="index == 3">产品功能</span>
            <span v-if="index == 4">免费试用</span>
          </el-breadcrumb-item>
        </el-breadcrumb>
      </div>
    </div>
    <div class="OMS-one" id="1">
      <div
        class="OMS-one-content"
        v-for="(item, index) in topList"
        :key="index"
      >
        <div class="OMS-content-png">
          <img :src="item.img" alt="" style="width: 100%" />
        </div>
        <div class="title">{{ item.title }}</div>
      </div>
    </div>
    <div class="OMS-two" id="2">
      <div class="title">产品应用价值</div>
      <div class="OMS-two-content">
        <div
          class="OMS-two-top"
          v-for="(item, index) in worthList"
          :key="index"
        >
          <div class="OMS-two-png">
            <img :src="item.img" alt="" style="width: 100%" />
          </div>
          <div class="OMS-two-title">
            <div
              style="
                width: 7px;
                height: 19px;
                background: #0087ff;
                margin-right: 9px;
              "
            ></div>
            {{ item.title }}
          </div>
          <div class="OMS-two-bottom">
            <div
              style="display: flex; align-items: center"
              v-for="(temp, index) in item.list"
              :key="index"
            >
              <div
                style="
                  width: 10px;
                  height: 2px;
                  background: #333333;
                  margin-right: 8px;
                "
              ></div>
              {{ temp.name }}
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="OMS-three" id="3">
      <div class="title">产品功能</div>
      <div class="OMS-three-count">
        <div
          style="
            display: flex;
            justify-content: space-between;
            width: 100%;
            margin-bottom: 52px;
          "
        >
          <div style="width: 610px">
            <div style="font-size: 20px; margin-bottom: 24px; font-weight: 700">
              基本信息管理系统
            </div>
            <div style="font-size: 16px; color: rgba(51, 51, 51, 1)">
              不仅支持对包括品名、规格、生产厂家、产品批号、生产日期、有效期和箱包装等
              商品基本信息进行设置，而且货位管理功能对所有货位进行编码并存储在系统的数
              据库中，使系统能有效的追踪商品所处位置，也便于操作人员根据货位号迅速定位
              到目标货位在仓库中的物理位置。
            </div>
          </div>
          <div class="OMS-three-png">
            <img
              src="@/assets/images/WMS02/png10.png"
              alt=""
              style="width: 100%"
            />
          </div>
        </div>
        <div
          style="
            display: flex;
            justify-content: space-between;
            width: 100%;
            margin-bottom: 52px;
          "
        >
          <div class="OMS-three-png">
            <img
              src="@/assets/images/WMS02/png11.png"
              alt=""
              style="width: 100%"
            />
          </div>
          <div style="width: 610px">
            <div
              style="
                font-size: 20px;
                margin-bottom: 24px;
                font-weight: 700;
                text-align: right;
              "
            >
              库存管理系统
            </div>
            <div style="font-size: 16px; color: rgba(51, 51, 51, 1)">
              系统支持自动补货，通过自动补货算法，不仅确保了拣选面存货量，也能提高仓储空间利
              用率，降低货位蜂窝化现象出现的概率。系统能够对货位通过深度信息进行逻辑细分和动
              态设置，在不影响自动补货算法的同时，有效的提高了空间利用率和对控制精度。
            </div>
          </div>
        </div>
        <div
          style="
            display: flex;
            justify-content: space-between;
            width: 100%;
            margin-bottom: 52px;
          "
        >
          <div style="width: 610px">
            <div style="font-size: 20px; margin-bottom: 24px; font-weight: 700">
              上架管理和拣选管理
            </div>
            <div style="font-size: 16px; color: rgba(51, 51, 51, 1)">
              系统在自动计算最佳上架货位的基础上，支持人工干预，提供已存放同品种的货位、
              剩余空间，并根据避免存储空间浪费的原则给出建议的上架货位并按优先度排序，
              操作人员可以直接确认或人工调整。
              拣选指令中包含位置信息和最优路径，根据货位布局和确定拣选指导顺序，系统自
              动在RF终端的界面等相关设备中根据任务所涉及的货位给出指导性路径，避免无
              效穿梭和商品找寻，提高了单位时间内的拣选量。
            </div>
          </div>
          <div class="OMS-three-png">
            <img
              src="@/assets/images/WMS02/png12.png"
              alt=""
              style="width: 100%"
            />
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
import { HomeFilled, ArrowRight } from '@element-plus/icons-vue'
const index = ref(1)
const newList = reactive([
  {
    title: '产品优势',
    id: 1,
  },
  {
    title: '产品应用价值',
    id: 2,
  },
  {
    title: '产品功能',
    id: 3,
  },
  {
    title: '免费试用',
    id: 4,
  },
])
const topList = reactive([
  {
    img: new URL('@/assets/images/WMS02/topOne.png', import.meta.url).href,
    title: '数据采集及时、过程精准管理、全自动化智能导向，提高工作效率',
  },
  {
    img: new URL('@/assets/images/WMS02/homeTop.png', import.meta.url).href,
    title: '库位精确定位管理、状态全面监控，充分利用有限仓库空间',
  },
  {
    img: new URL('@/assets/images/WMS02/warehouse.png', import.meta.url).href,
    title: '货品上架和下架，全智能按先进先出自动分配上下架库位，避免人为错误',
  },
  {
    img: new URL('@/assets/images/WMS02/monitoring.png', import.meta.url).href,
    title: '实时掌控库存情况，合理保持和控制企业库存',
  },
  {
    img: new URL('@/assets/images/WMS02/collect.png', import.meta.url).href,
    title: '通过对批次信息的自动采集，实现了对产品生产或销售过程的可追溯性',
  },
])
const worthList = reactive([
  {
    img: new URL('@/assets/images/OMS01/customer.png', import.meta.url).href,
    title: '解决客户管理难题',
    list: [
      { name: '客户管理集成化' },
      { name: '合同执行流程化' },
      { name: '售后服务自动化' },
      { name: '客户统计智能化' },
    ],
  },
  {
    img: new URL('@/assets/images/OMS01/product.png', import.meta.url).href,
    title: '解决产品管理难题',
    list: [
      { name: '产品管理统一化' },
      { name: '数据更新实时化' },
      { name: '品类层次多样化' },
      { name: '产品数据共享化' },
    ],
  },
  {
    img: new URL('@/assets/images/OMS01/bill.png', import.meta.url).href,
    title: '解决账单管理难题',
    list: [
      { name: '账单分类标准化' },
      { name: '变更管理一体化' },
      { name: '执行过程可视化' },
      { name: '账单结算多样化' },
    ],
  },
  {
    img: new URL('@/assets/images/OMS01/after-sales.png', import.meta.url).href,
    title: '解决售后管理难题',
    list: [
      { name: '售后响应实时化' },
      { name: '任务分配自动化' },
      { name: '售后管控科学化' },
      { name: '售后统计精准化' },
    ],
  },
  {
    img: new URL('@/assets/images/OMS01/warehouse.png', import.meta.url).href,
    title: '解决库房管理难题',
    list: [
      { name: '库房管理集成化' },
      { name: '出入库执行流程化' },
      { name: '库房统计精准化' },
      { name: '货品溯源智能化' },
    ],
  },
  {
    img: new URL('@/assets/images/OMS01/procurement.png', import.meta.url).href,
    title: '解决采购管理难题',
    list: [
      { name: '采购执行流程化' },
      { name: '合同执行流程化' },
      { name: '采购更新实时化' },
      { name: '采购数据共享化' },
    ],
  },
])
const functionList = reactive([
  {
    img: new URL('@/assets/images/OMS01/tracking.png', import.meta.url).href,
    title: '跟踪与查询',
    content:
      '系统可实现单次及批量订单，订单管理与库存管理相连接，并且在下订单时有库存预警及提示功能，订单管理同时与客户管理相连接，可查询历史订单情况以及订单的执行情况。',
  },
  {
    img: new URL('@/assets/images/OMS01/tracking.png', import.meta.url).href,
    title: '订单成本分析',
    content:
      '通过各品种的订货量、出库量和返货量的对比，进一步分析产生差异的原因，分析经营中的问题。可及时调整经营策略，减少可控的损失。',
  },
  {
    img: new URL('@/assets/images/OMS01/tracking.png', import.meta.url).href,
    title: '工作流程引擎及配置',
    content:
      '通过对订单的管理和分配，动态掌握订单的进展和完成情况，提升物流过程中的作业效率，从而节省运作时间和作业成本，提高物流企业的市场竞争力。',
  },
  {
    img: new URL('@/assets/images/OMS01/tracking.png', import.meta.url).href,
    title: '销售费用管理',
    content:
      '不少企业都在为销售费用而苦恼。销售费用管理为您建立一套完善的销售费用管理体系，帮您把费用控制到合理范围内。',
  },
  {
    img: new URL('@/assets/images/OMS01/tracking.png', import.meta.url).href,
    title: '订单履约成本有效降低',
    content:
      '通过就近、就全、库存深度、动销等多维度订单路由规则，找到每一个订单最接近收货地点、最低运输成本、最简拆分或捆绑订单的最优订单履约策略，智能拆单，订单履约的物流成本与时间成本等大幅降低。',
  },
])

const change = (id: number) => {
  index.value = id
}
</script>
<style lang="scss" scoped>
.OMS-top {
  height: 500px;
  background: url('@/assets/images/WMS02/banner.png');
  background-size: cover;
  color: #ffffff;
  box-sizing: border-box;
  padding-top: 135px;
  padding-left: 291px;
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
.OMS-one {
  height: 492px;
  width: 1440px;
  display: flex;
  align-items: center;
  margin: auto;
  > :last-child {
    margin-right: 0;
  }
  .OMS-one-content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 266px;
    height: 340px;
    background: #ffffff;
    padding: 0 32px;
    box-sizing: border-box;
    margin-right: 27px;
    border: 1px solid #e5e5e5;
    .OMS-content-png {
      width: 120px;
      margin-bottom: 36px;
    }
    .title {
      font-size: 20px;
      margin-bottom: 24px;
    }
    .content {
      font-size: 18px;
    }
  }
}
.OMS-two {
  // width: 1920px;
  height: 410px;
  background: #f0f0f0;
  text-align: center;
  .title {
    font-size: 26px;
    color: #333333;
    padding: 40px 0;
  }
  .OMS-two-content {
    width: 1470px;
    margin: auto;
    display: flex;
    > :last-child {
      margin-right: 0;
    }
    .OMS-two-top {
      width: 160px;
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-right: 84px;
      .OMS-two-png {
        width: 49px;
      }
      .OMS-two-title {
        display: flex;
        align-items: center;
        font-size: 18px;
        margin-top: 37px;
        margin-bottom: 25px;
      }
      .OMS-two-bottom {
        font-size: 14px;
        color: #333333;
      }
    }
  }
}
.OMS-three {
  .title {
    height: 172px;
    line-height: 172px;
    font-size: 26px;
    text-align: center;
  }
  .OMS-three-count {
    width: 1440px;
    margin: auto;
    justify-content: space-between;
    .OMS-three-png {
      width: 503px;
    }
  }
}
</style>
