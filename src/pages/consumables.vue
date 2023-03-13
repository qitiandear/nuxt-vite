<template>
  <div class="home">
    <div class="OMS-top">
      <div style="font-size: 60px; margin-bottom: 10px">耗材销售及统计系统</div>
      <div style="font-size: 26px">
        具备强大报表与集成查询功能，所有功能在用户需要使<br />用的地方自然体现，并可根据需要自行设计单据和报表<br />的打印格式。
      </div>
    </div>
    <navigationBar @change="change" />
    <div class="consumables-content" id="1">
      <div class="consumables-one" v-for="item in list" :key="item.id">
        <img :src="item.pic" alt="" style="width: 100%" />
        <div
          style="
            font-size: 26px;
            font-family: FZLanTingHei-DB-GBK;
            color: #333333;
            margin-top: 39px;
          "
        >
          {{ item.title }}
        </div>
      </div>
    </div>
    <productValue id="2" />
    <div id="3">
      <div
        style="
          font-size: 26px;
          color: #333333;
          margin: 70px auto;
          text-align: center;
        "
      >
        产品功能
      </div>
      <div class="consumables-product-one">
        <div
          class="consumables-product"
          v-for="item in functionList"
          :key="item.id"
        >
          <img :src="item.pic" alt="" style="height: 100%" />
          <div style="font-size: 22px; color: #333333; margin-left: 20px">
            {{ item.title }}
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
    pic: new URL('@/assets/images/consumables/ad-crm6.png', import.meta.url)
      .href,
    title: '精细化管理',
  },
  {
    id: 2,
    pic: new URL('@/assets/images/consumables/ad-crm7.png', import.meta.url)
      .href,
    title: '大数据管控',
  },
  {
    id: 3,
    pic: new URL('@/assets/images/consumables/ad-crm8.png', import.meta.url)
      .href,
    title: '可视化报表',
  },
])
const functionList = reactive([
  {
    id: 1,
    pic: new URL('@/assets/images/consumables/fpic1.png', import.meta.url).href,
    title: '国家标准分类',
  },
  {
    id: 2,
    pic: new URL('@/assets/images/consumables/fpic2.png', import.meta.url).href,
    title: '国家标准分类',
  },
  {
    id: 3,
    pic: new URL('@/assets/images/consumables/fpic3.png', import.meta.url).href,
    title: '国家标准分类',
  },
  {
    id: 4,
    pic: new URL('@/assets/images/consumables/fpic4.png', import.meta.url).href,
    title: '国家标准分类',
  },
  {
    id: 5,
    pic: new URL('@/assets/images/consumables/fpic5.png', import.meta.url).href,
    title: '国家标准分类',
  },
  {
    id: 6,
    pic: new URL('@/assets/images/consumables/fpic6.png', import.meta.url).href,
    title: '国家标准分类',
  },
  {
    id: 7,
    pic: new URL('@/assets/images/consumables/fpic7.png', import.meta.url).href,
    title: '国家标准分类',
  },
  {
    id: 8,
    pic: new URL('@/assets/images/consumables/fpic8.png', import.meta.url).href,
    title: '国家标准分类',
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
  background: url('@/assets/images/consumables/banner.png');
  background-size: cover;
  color: #ffffff;
  box-sizing: border-box;
  padding-top: 135px;
  padding-left: 291px;
}

.consumables-content {
  display: flex;
  justify-content: space-between;
  margin: 106px 260px 67px 260px;
  .consumables-one {
    width: 403px;
    text-align: center;
  }
}

.consumables-product-one {
  display: flex;
  flex-wrap: wrap;
  margin: 70px 262px 20px 262px;
  .consumables-product {
    display: flex;
    align-items: center;
    width: 25%;
    height: 60px;
    margin-bottom: 73px;
  }
}
</style>
