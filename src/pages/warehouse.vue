<template>
  <div class="home">
    <div class="warehouse-top">
      <div style="font-size: 60px; margin-bottom: 10px">智能仓储管理系统</div>
      <div>能够按照运作的业务规则和运算法则，对信息、资源、</div>
      <div>行为、存货和分销运作进行更完美地管理，提高效率</div>
    </div>
    <navigationBar @change="change" />
    <div class="warehouse-one" id="1">
      <div class="warehouse-one-flex">
        <div class="warehouse-one-box" v-for="item in list" :key="item.id">
          <img
            :src="item.pic"
            alt=""
            style="float: left; margin-right: 33px; width: 54px"
          />
          <div
            style="
              color: #333333;
              font-size: 24px;
              display: inline-block;
              float: left;
              width: 345px;
              margin-bottom: 10px;
            "
          >
            {{ item.title }}
          </div>
          <div>{{ item.describe }}</div>
        </div>
      </div>
    </div>
    <productValue id="2" />
    <div class="OMS-three" id="3">
      <!-- <div class="title">产品功能</div> -->
      <div class="OMS-three-count">
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
              src="@/assets/images/warehouse/ddos.png"
              alt=""
              style="width: 100%"
            />
          </div>
          <div style="width: 610px">
            <div style="font-size: 20px; margin-bottom: 24px; font-weight: 700">
              总体架构
            </div>
            <div
              style="
                font-size: 16px;
                color: rgba(51, 51, 51, 1);
                margin-bottom: 44px;
              "
            >
              自动化仓储系统分为WMS系统和WCS系统，我们将WMS和WCS进行
              了整合，实现了WMS和WCS的无缝对接。
            </div>
            <div style="font-size: 16px; color: rgba(51, 51, 51, 1)">
              同时使WMS在智能管理衍生到了设备层，为WMS的智能管理、智能运
              行提供了更多的信息。
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
              WMS仓储管理系统
            </div>
            <div
              style="
                font-size: 16px;
                color: rgba(51, 51, 51, 1);
                margin-bottom: 44px;
              "
            >
              WMS仓储管理系统综合了入库管理、出库管理、物料对应、库存盘点、
              虚仓管理、库存统计等诸多功能，有效控制并跟踪仓库的物流。
            </div>
            <div style="font-size: 16px; color: rgba(51, 51, 51, 1)">
              实现完善的企业仓储信息管理，并可以与EPR、MRP、WCS等多种软
              件系统对接，更好地提高企业管理的深度和广度
            </div>
          </div>
          <div class="OMS-three-png">
            <img
              src="@/assets/images/warehouse/cn2.png"
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
              src="@/assets/images/warehouse/business.png"
              alt=""
              style="width: 100%"
            />
          </div>
          <div style="width: 610px">
            <div style="font-size: 20px; margin-bottom: 24px; font-weight: 700">
              WCS仓储管理系统
            </div>
            <div
              style="
                font-size: 16px;
                color: rgba(51, 51, 51, 1);
                margin-bottom: 44px;
              "
            >
              介于WMS系统和智能硬件系统之间的一层管理控制系统，可以协调各种
              设备如智能货柜、堆垛机、穿梭车等设备之间的运行
            </div>
            <div style="font-size: 16px; color: rgba(51, 51, 51, 1)">
              通过任务引擎和消息引擎，优化分解任务、分析执行路径，为上层系统
              的调度指令提供执行保障和优化，实现对各种设备系统接口的集成、统
              一调度和监控。
            </div>
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
const index = ref<number>()
const list = reactive([
  {
    id: 1,
    pic: new URL('@/assets/images/warehouse/entrepot.png', import.meta.url)
      .href,
    title: '精细化管理',
    describe:
      ' 以库位管理，波次作业策略，拣货 路径优化等智能作业为支撑，结合商品码、箱 码、托盘码、库码四码合一的管理标准实现管 理精细化。以库位管理，波次作业策略，拣货 路径优化等智能作业为支撑，结合商品码、箱 码、托盘码、库码四码合一的管理标准实现管 理精细化。',
  },
  {
    id: 2,
    pic: new URL('@/assets/images/warehouse/customer.png', import.meta.url)
      .href,
    title: '智能波次',
    describe:
      ' 系统可依据不同的订单结构和订单 量进行排序，快速创建波次分配出库，便于用 户根据分析结果选择最佳的作业流程。',
  },
  {
    id: 3,
    pic: new URL('@/assets/images/warehouse/goods.png', import.meta.url).href,
    title: '快速补拣',
    describe:
      ' 拣货库存出现异常时，系统根据补 拣策略，快速推荐最优储位完成拣货，从提高 订单满足率，同时自动调整异常库存。',
  },
  {
    id: 4,
    pic: new URL('@/assets/images/warehouse/process.png', import.meta.url).href,
    title: '流程规则',
    describe:
      ' 为适配不同行业和作业场景， C-WMS配置多种策略:上架、周转、波次、 拣货。',
  },
  {
    id: 5,
    pic: new URL('@/assets/images/warehouse/docking.png', import.meta.url).href,
    title: '三方对接',
    describe:
      ' 外接硬件设备、三方平台、标准接 口实现系统数据互联互通；还可根据客户具体 业务需求进行定制开发，保证系统的专属性， 唯一性。',
  },
])

const change = (id: number) => {
  index.value = id
}
</script>

<style lang="scss" scoped>
.warehouse-top {
  height: 500px;
  background: url('@/assets/images/warehouse/top.png');
  background-size: cover;
  color: #ffffff;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: 26px;
}
.warehouse-one {
  margin: 70px 0;
  .warehouse-one-flex {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    > :nth-child(1) {
      margin-right: 50px;
    }
    > :nth-child(2) {
      margin-right: 50px;
    }
    > :nth-child(4) {
      margin-right: 50px;
    }
  }
  .warehouse-one-box {
    padding: 32px;
    width: 440px;
    height: 240px;
    background: #ffffff;
    border: 1px solid #e3e3e3;
    font-size: 18px;
    line-height: 34px;
    margin-bottom: 35px;
  }
}
.OMS-three {
  margin: 70px 240px;
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
      width: 421px;
    }
  }
}
</style>
