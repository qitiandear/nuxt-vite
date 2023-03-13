<template>
  <div class="home">
    <div class="OMS-top">
      <div style="font-size: 60px; margin-bottom: 10px">OMS管理系统</div>
      <div style="font-size: 26px">
        定位于为处于供应链上游的供应商和下游的买方
      </div>
      <div style="font-size: 26px">通过对订单的管理和控制</div>
      <div style="font-size: 26px">合理安排运送计划、有效降低库存</div>
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
        <div class="content">{{ item.content }}</div>
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
      <div class="OMS-three-big">
        <div
          class="OMS-three-count"
          v-for="(item, index) in functionList"
          :key="index"
        >
          <div style="margin-right: 30px">
            <img :src="item.img" alt="" width="56px" />
          </div>
          <div>
            <div class="OMS-three-top">{{ item.title }}</div>
            <div class="OMS-three-bottom">{{ item.content }}</div>
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
import supply from '@/assets/images/OMS01/supply.png'
import { HomeFilled, ArrowRight } from '@element-plus/icons-vue'
import processImg from '@/assets/images/OMS01/process.png'
import platform from '@/assets/images/OMS01/platform.png'
import customer from '@/assets/images/OMS01/customer.png'
import product from '@/assets/images/OMS01/product.png'
import bill from '@/assets/images/OMS01/bill.png'
import afterSales from '@/assets/images/OMS01/after-sales.png'
import warehouse from '@/assets/images/OMS01/warehouse.png'
import procurement from '@/assets/images/OMS01/procurement.png'
import tracking from '@/assets/images/OMS01/tracking.png'
import ProfeatIcon5 from '@/assets/images/OMS01/Profeat-icon5.png'
import ProfeatIcon4 from '@/assets/images/OMS01/Profeat-icon4.png'
import ProfeatIcon3 from '@/assets/images/OMS01/Profeat-icon3.png'
import ProfeatIcon2 from '@/assets/images/OMS01/Profeat-icon2.png'
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
    img: supply,
    title: '供应链全过程的透明化',
    content: '减少中间环节，减少库存，减少供需信息不准确',
  },
  {
    img: processImg,
    title: '协作式作业流程与管理模式',
    content:
      '满足供应链上下游买家、卖家的不同角度需求，创立协作式的供应链作业流程与管理模式',
  },
  {
    img: platform,
    title: '标准的接口，易于扩充',
    content: '数据和系统安全性好，准确、及时、便利，标准的接口，易于扩充',
  },
])
const worthList = reactive([
  {
    img: customer,
    title: '解决客户管理难题',
    list: [
      { name: '客户管理集成化' },
      { name: '合同执行流程化' },
      { name: '售后服务自动化' },
      { name: '客户统计智能化' },
    ],
  },
  {
    img: product,
    title: '解决产品管理难题',
    list: [
      { name: '产品管理统一化' },
      { name: '数据更新实时化' },
      { name: '品类层次多样化' },
      { name: '产品数据共享化' },
    ],
  },
  {
    img: bill,
    title: '解决账单管理难题',
    list: [
      { name: '账单分类标准化' },
      { name: '变更管理一体化' },
      { name: '执行过程可视化' },
      { name: '账单结算多样化' },
    ],
  },
  {
    img: afterSales,
    title: '解决售后管理难题',
    list: [
      { name: '售后响应实时化' },
      { name: '任务分配自动化' },
      { name: '售后管控科学化' },
      { name: '售后统计精准化' },
    ],
  },
  {
    img: warehouse,
    title: '解决库房管理难题',
    list: [
      { name: '库房管理集成化' },
      { name: '出入库执行流程化' },
      { name: '库房统计精准化' },
      { name: '货品溯源智能化' },
    ],
  },
  {
    img: procurement,
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
    img: tracking,
    title: '跟踪与查询',
    content:
      '系统可实现单次及批量订单，订单管理与库存管理相连接，并且在下订单时有库存预警及提示功能，订单管理同时与客户管理相连接，可查询历史订单情况以及订单的执行情况。',
  },
  {
    img: ProfeatIcon5,
    title: '订单成本分析',
    content:
      '通过各品种的订货量、出库量和返货量的对比，进一步分析产生差异的原因，分析经营中的问题。可及时调整经营策略，减少可控的损失。',
  },
  {
    img: ProfeatIcon4,
    title: '工作流程引擎及配置',
    content:
      '通过对订单的管理和分配，动态掌握订单的进展和完成情况，提升物流过程中的作业效率，从而节省运作时间和作业成本，提高物流企业的市场竞争力。',
  },
  {
    img: ProfeatIcon3,
    title: '销售费用管理',
    content:
      '不少企业都在为销售费用而苦恼。销售费用管理为您建立一套完善的销售费用管理体系，帮您把费用控制到合理范围内。',
  },
  {
    img: ProfeatIcon2,
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
  background: url('@/assets/images/OMS01/topbg.png');
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
    width: 420px;
    height: 340px;
    background: #ffffff;
    padding: 0 48px;
    box-sizing: border-box;
    margin-right: 90px;

    &:hover {
      box-shadow: 0px 0px 13px 0px rgba(0, 8, 56, 0.14);
    }
    .OMS-content-png {
      width: 119px;
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
  .OMS-three-big {
    display: flex;
    width: 1440px;
    margin: auto;
    flex-wrap: wrap;
    .OMS-three-count {
      display: flex;
      width: 442px;
      height: 162px;
      margin-block: 63px;
      margin-right: 35px;
      .OMS-three-top {
        font-size: 26px;
        margin-bottom: 16px;
        color: rgba(51, 51, 51, 1);
      }
      .OMS-three-bottom {
        font-size: 16px;
        color: #333333;
      }
    }
  }
}
</style>
