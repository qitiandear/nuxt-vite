<template>
  <div class="OMS-two">
    <div class="title">产品应用价值</div>
    <div class="OMS-two-content">
      <div class="OMS-two-top" v-for="(item, index) in worthList" :key="index">
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
</template>

<script setup lang="ts">
import customer from '@/assets/images/OMS01/customer.png'
import product from '@/assets/images/OMS01/product.png'
import bill from '@/assets/images/OMS01/bill.png'
import afterSales from '@/assets/images/OMS01/after-sales.png'
import warehouse from '@/assets/images/OMS01/warehouse.png'
import procurement from '@/assets/images/OMS01/procurement.png'

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
</script>
<style lang="scss" scoped>
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
</style>
